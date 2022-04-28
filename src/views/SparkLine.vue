<template>
  <div class="sparkline-graph">
    <div class="chart-wrapper" data-wrapper>
      <span id="date">28/4/2022</span>
      <div class="chart-info">
        <div class="float-left">
        <div class="market-price"><p data-total>6.92</p>Ξ </div>
        <div class="current-price"><i class="fa-solid fa-caret-up"></i> 1.24Ξ (.18%)</div>
        </div>
        <div class="right-info">
          <p>PROFIT</p>
          <p>3.59Ξ</p>
        </div>
      </div>
      <figure data-chart></figure>
      <div class="control-btns">
        <span @click="changeDuration('day', $event)">1D</span>
        <span @click="changeDuration('week', $event)">1W</span>
        <span @click="changeDuration('onemonth', $event)">1M</span>
        <span @click="changeDuration('threemonth', $event)">3M</span>
        <span class="active" @click="changeDuration('oneyear', $event)">1Y</span>
      </div>
    </div>
  </div>
</template>
<script>
import api from '../API/data.json';
export default {
  name: "app",
  data() {
    return {
      dimensions: {
        width: (window.innerWidth - 50),
        height: 300,
        marginTop: 80
      }
    };
  },
  methods: {
    changeDuration: function(duration,e) {
        document.querySelectorAll('figure svg').forEach(function(svgElement){
          svgElement.remove();
        });
        document.querySelectorAll('.control-btns span').forEach(function(item){
          item.classList.remove('active');
        });
        e.target.classList.add('active');
        var data = api[duration].historicals;
        const sortedData = this.sortData(data);
        window.draw(sortedData);
    },
  sortData: function(data) {
      return data
        .map((d) => {
          return {
            ...d,
            date: new Date(d.begins_at),
          };
        })
        .sort((a, b) => d3.ascending(a.begins_at, b.begins_at));
    },
  },
  mounted() {
    const xAccessor = (d) => d.date;
    const yAccessor = (d) => d.high_price;

    const formatDate = d3.timeFormat("%Y-%m-%d %H:%M");

    const getText = (data, d) => {
      return `${formatDate(d)}`;
    };

     window.draw = (data) => {
      const wrapper = d3.select("[data-wrapper]");
      const svg = wrapper
        .select("[data-chart]")
        .append("svg")
        .attr("width", this.dimensions.width)
        .attr("height", this.dimensions.height)
        .attr("viewBox", `0 0 ${this.dimensions.width} ${this.dimensions.height}`);

      const xDomain = d3.extent(data, xAccessor);
      const yDomain = [0, d3.max(data, yAccessor)];

      const xScale = d3
        .scaleTime()
        .domain(xDomain)
        .range([0, this.dimensions.width]);

      const yScale = d3
        .scaleLinear()
        .domain(yDomain)
        .range([this.dimensions.height, this.dimensions.marginTop]);

      /* Line */
      const lineGenerator = d3
        .line()
        .x((d) => xScale(xAccessor(d)))
        .y((d) => yScale(yAccessor(d)))
        .curve(d3.curveBumpX);

      const line = svg
        .append("path")
        .datum(data)
        .attr("d", lineGenerator)
        .attr("stroke", "rgba(38,208,43,1)")
        .attr("stroke-width", 1)
        .attr("stroke-linejoin", "round")
        .attr("fill", "none");

      /* Markers */
      const markerLine = svg
        .append("line")
        .attr("x1", 0)
        .attr("x2", 0)
        .attr("y1", 0)
        .attr("y2", this.dimensions.height)
        .attr("stroke-width", 1)
        .attr("stroke", "rgb(145,159,166)")
        .attr("opacity", 0);

      const markerDot = svg
        .append("circle")
        .attr("cx", 0)
        .attr("cy", 0)
        .attr("r", 8)
        .attr("fill", "rgba(38,208,43,1)")
        .attr("opacity", 0);

      /* Bisector */
      const bisect = d3.bisector(xAccessor);

      /* Events */
      svg.on("mousemove", (e) => {
        var dateEle = document.querySelector('#date');
        dateEle.style.display = 'block';
        const [posX, posY] = d3.pointer(e);
        const date = xScale.invert(posX);
        dateEle.style.left = (e.clientX - 80)+'px';
        dateEle.innerHTML = getText(data, date);
        const index = bisect.center(data, date);
        const d = data[index];

        const x = xScale(xAccessor(d));
        const y = yScale(yAccessor(d));

        markerLine.attr("x1", x).attr("x2", x).attr("opacity", 1);

        markerDot.attr("cx", x).attr("cy", y).attr("opacity", 1);

        d3.select("[data-heading]").text(getText(data, d));
        d3.select("[data-total]").text(yAccessor(d));
      });

      svg.on("mouseleave", () => {
        const lastDatum = data[data.length - 1];
        document.querySelector('#date').style.display = 'none';
        markerLine.attr("opacity", 0);
        markerDot.attr("opacity", 0);

        d3.select("[data-heading]").text("Weekly downloads");
        d3.select("[data-total]").text(yAccessor(lastDatum));
      });
    };
        var data = api.oneyear.historicals;
        const sortedData = this.sortData(data);
        draw(sortedData);
  }
};
</script>

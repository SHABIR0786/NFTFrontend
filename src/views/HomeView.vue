<template>
  <div>
    <!-- <sparkline
      width="100"
      height="30"
      :indicatorStyles="spIndicatorStyles3"
      :tooltipProps="spTooltipProps3"
    >
      <sparklineCurve
        :data="spData3"
        :limit="spData3.length"
        :spotlight="spIndex3"
        :styles="spCurveStyles3"
        :spotStyles="spSpotStyles3"
        :spotProps="spSpotProps3"
        :refLineType="spRefLineType3"
        :refLineStyles="spRefLineStyles3"
        :textStyles="spTextStyles3"
      />
    </sparkline> -->
  </div>
</template>
<script>
// import sparkline from "vue-sparklines";
// export default {
//   components: {
//     sparkline,
//   },
//   data() {
//     return {
//       spData3: (() => {
//         const len = 15;
//         return Array.from(
//           {
//             length: len,
//           },
//           () => Math.floor(Math.random() * len)
//         );
//       })(),
//       spCurveStyles3: {
//         stroke: "#54a5ff",
//         fill: "#000",
//       },
//       spSpotStyles3: {
//         fill: "#54a5ff",
//       },
//       spSpotProps3: {
//         size: 2,
//       },
//       spRefLineType3: "avg",
//       spRefLineStyles3: {
//         stroke: "#d14",
//         strokeOpacity: 1,
//         strokeDasharray: "2, 2",
//       },
//       spIndex3: 3,
//       spTextStyles3: {
//         fill: "#d14",
//         fontSize: "12",
//       },
//       spIndicatorStyles3: {
//         stroke: "#000",
//       },
//       spTooltipProps3: {
//         formatter(val) {
//           return `当前数据为：<label style="color:${val.color};font-weight:bold;">${val.value}</label>`;
//         },
//       },
//     };
//   },
// };
</script>

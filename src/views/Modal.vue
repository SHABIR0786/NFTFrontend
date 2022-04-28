<template>
<div class="">

    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter">
        Open Modal
    </button>

    <!-- Modal -->
    <div class1="modal show modal_show" class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
        <div class="modal-dialog modal-lg modal-dialog-centered " role="document" style="width: 660px;height: 535px;">
            <div class="modal-content" style="border: none;">
                <!-- <div class="modal-header bg_color_modal" >
        <h5 class="modal-title" id="exampleModalLongTitle">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">×</span>
        </button>
      </div> -->
                <div class="modal-body bg_color_modal rounded">
                    <!-- <div class="container pb-3"><button class="float-right btn p-0 px-2 m-0 btn-danger" style="top: -15px;left: 27px;">×</button></div> -->
                    <div class="container-fluid p-0">

                        <div class="row">
                            <div class="col-md-12 col-sm-12  col-lg-4 "><img src="https://i.ibb.co/bLPdJ0R/Screenshot-2022-04-25-151947.png" class="rounded float-left modal_image" alt="image"></div>
                            <div class="col-md-12 col-sm-12 col-lg-8 text-white">
                                <div class="div_heading">
                                    <p class="h2 pt-3">Creatures World #6895<i class="fas fa-external-link-alt"></i></p>
                                    <p class="h5" style="color: #C598FF;">Creatures World NFT</p>
                                    <br>
                                    <p style="color :rgba(255, 255, 255, 0.3);" class="p-0 m-0">BOUGHT FOR</p>
                                    <p id="value_div" class="h5">9.70 ETH</p>
                                </div>
                            </div>

                        </div>
                        <hr class=" my-4 p-0" style="border-top: 1px solid rgba(255, 255, 255, 0.1);">
                        <div class="container">
                            <div class="row p-0 m-0 ">
                                <div class="col float-left p-0 m-0">
                                    <p class="text-white h4 text-left">Traits</p>
                                </div>
                                <div class="col float-right p-0 m-0">
                                    <p style="color :rgba(255, 255, 255, 0.3);" class="text-right">ORDERED BY RARITY</p>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="container pt-3 px-3">
                                <div class="row px-0 py-2 m-0">
                                    <div class="col custom_grey_color text-left">TRAIT</div>
                                    <div class="col custom_grey_color">TRAIT TYPE</div>
                                    <div class="col custom_grey_color">TRAIT</div>
                                    <div class="col custom_grey_color col text-right">TRAIT FLOOR</div>

                                </div>

                                <div class="row px-0 py-2 m-0 border border-dark rounded_6px text-white tr_bg_grey">
                                    <div class="col text-left">Yacht Captain</div>
                                    <div class="col custom_grey_color">Hat/Hair</div>
                                    <div class="col"><span class="percentage_class">3%</span> <span class="custom_grey_color">100/10,000</span></div>
                                    <div class="col text-right">2.4Ξ </div>
                                </div>
                                <div class="row px-0 py-2 m-0  text-white">
                                    <div class="col text-left">Black</div>
                                    <div class="col custom_grey_color">Fur</div>
                                    <div class="col"><span class="percentage_class">3%</span> <span class="custom_grey_color">200/10,000</span></div>
                                    <div class="col text-right">1.8Ξ </div>
                                </div>
                                <div class="row px-0 py-2 m-0 border border-dark rounded_6px text-white tr_bg_grey">
                                    <div class="col text-left">Rock On</div>
                                    <div class="col custom_grey_color">Hand</div>
                                    <div class="col"><span class="percentage_class">4%</span> <span class="custom_grey_color">320/1000</span></div>
                                    <div class="col text-right">1Ξ </div>
                                </div>
                                <div class="row px-0 py-2 m-0  text-white">
                                    <div class="col text-left">Cigarette</div>
                                    <div class="col custom_grey_color">Mouth</div>
                                    <div class="col"><span class="percentage_class">12%</span> <span class="custom_grey_color">296/10,000</span></div>
                                    <div class="col text-right">10.5Ξ </div>
                                </div>
                                <div class="row px-0 py-2 m-0 border border-dark rounded_6px text-white tr_bg_grey">
                                    <div class="col text-left">Turquoise</div>
                                    <div class="col custom_grey_color">Background</div>
                                    <div class="col"><span class="percentage_class">36%</span> <span class="custom_grey_color">320/1000</span></div>
                                    <div class="col text-right">0.32Ξ </div>
                                </div>

                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {

    data() {
        return {
            showModal: false,
        };
    },

    mounted() {

    },
    methods: {
        showmodalFun() {
            this.showModal = !this.showModal;
        },
    },
};
</script>

<style>
@media (min-width: 1024px) {
    .about {
        min-height: 100vh;
        display: flex;
        align-items: center;
    }
}

.bg_color_modal {
    background: linear-gradient(0deg, rgba(230, 230, 255, 0.05), rgba(230, 230, 255, 0.05)), #1C1D22;
}

.modal_image {
    height: 185px;
    width: 186px;
}

.modal_show {
    display: block !important;
    background: rgba(15, 15, 15, 0.8);
    height: auto !important;
    overflow: auto !important;
    border: 1px solid rgba(15, 15, 15, 0.8);
    ;

}

.modal_bg_blur {
    background: rgba(15, 15, 15, 0.8);
}

.custom_grey_color {
    color: rgba(255, 255, 255, 0.3);
}

.tr_bg_grey {
    background: rgba(230, 230, 255, 0.05)
}

.rounded_6px {
    border-radius: 6px;
}
</style>

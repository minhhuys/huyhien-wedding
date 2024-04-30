<template>
    <div class="second-section row no-gutters">
        <div class="col-12">
            <div class="second-section-main">
                <div class="second-section-wrapper position-relative mx-auto">
                    <div class="invitation-holder position-relative">
                        <div class="invitation-image position-absolute" data-aos="fade-right" data-aos-duration="1000">
                            <img src="@/assets/media/section-2-img.webp"
                                class="img-fluid" alt="">
                        </div>
                        <div class="invitation-text-holder position-relative w-100" data-aos="fade-left"
                            data-aos-duration="1000">
                            <div class="invitation-text-holder-inner">
                                <span>
                                    <img width="37" height="27"
                                        src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/04/h1-custom-icon-img-1.png"
                                        class="attachment-full size-full" alt="a" decoding="async" loading="lazy">
                                </span>
                                <h1 class="invitation-title">Minh Huy</h1>
                                <p class="invitation-separator">and</p>
                                <h1 class="invitation-title">Thu Hiền</h1>


                                <p class="font-prata mt-5">Buổi tiệc sẽ được diễn ra tại</p>
                                <img src="@/assets/media/crow.png" class="img-fluid mx-3" alt="">
                                <p class="invitation-text mt-3 ">
                                    <span class="font-weight-semibold h2 font-prata d-block mb-1">Star Palace</span>
                                    <span class="font-prata">Sen Tây Hồ, 127 Nhật Chiêu, Nhật Tân, Tây Hồ, Hà Nội</span>
                                </p>
                                <img src="@/assets/media/crow2.png" class="img-fluid mx-3" alt="">
                                <p class="invitation-date font-prata mt-3">vào lúc 17 giờ 30 <br>
                                    Thứ 5 | 02 - 05 - 2024</p>
                        <a href="https://maps.app.goo.gl/UBWz7WedZkFfZaqp8" target="_blank" class="text-dark font-weight-lighter" style="font-size: 13px; text-decoration: underline;">bản đồ</a>

                            </div>
                        </div>      
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");


.font-prata {
    font-family: "Prata";
}

.second-section {
    padding: 50px 0;

    .second-section-main {
        box-sizing: border-box;
        width: 100%;

        .second-section-wrapper {
            width: 1100px;
            z-index: 20;

            .invitation-holder {
                padding: 110px 0;

                .invitation-image {
                    width: 50%;
                    left: 0;
                    top: 0;
                    bottom: 0;
                    background-size: cover
                }

                .invitation-text-holder-inner {
                    width: 50%;
                    text-align: center;
                    margin-left: 50%;
                    padding: 50px 0;
                    background-color: #fff;
                    border: 25px solid rgba(251, 184, 172, .4);
                    border-left: none;

                    h1 {
                        font-size: 55px;
                        line-height: .87em;
                        margin: 8px;
                        font-family: "Great Vibes", cursive;
                    }

                    .invitation-separator {
                        position: relative;
                        display: inline-block;
                        margin: 9px 0 -4px;
                        padding: 0 12px;
                        font-style: italic;

                    }

                    .invitation-separator::before {
                        left: -10px;
                        content: "";
                        position: relative;
                        display: inline-block;
                        vertical-align: middle;
                        width: 73px;
                        height: 1px;
                        background-color: #ccc;
                    }

                    .invitation-separator::after {
                        right: -10px;
                        content: "";
                        position: relative;
                        display: inline-block;
                        vertical-align: middle;
                        width: 73px;
                        height: 1px;
                        background-color: #ccc;
                    }

                    .invitation-text {
                        // font-size: 20px;

                        span:first-child {
                            color: #c0690a;
                            font-size: 25px;
                            text-transform: uppercase
                        }

                        span:nth-child(2) {
                            font-size: 18px;
                        }

                    }
                }
            }

        }
    }

    .second-section-text {
        position: absolute;
        right: 0%;
        bottom: 10%;
    }

}

@media screen and (max-width: 768px) {
    .second-section {
        .second-section-main {
            .second-section-wrapper {
                width: 100%;

                .invitation-holder {
                    .invitation-image {
                        width: 100%;
                    }

                    .invitation-text-holder {
                        padding: 0 20px;

                        .invitation-text-holder-inner {
                            width: 100%;
                            margin-left: 0%;
                            border-left: 25px solid rgba(251, 184, 172, .4);
                        }
                    }

                }
            }
        }
    }
}
</style>
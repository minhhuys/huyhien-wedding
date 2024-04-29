<template>
    <div class="first-section position-relative">
        <img src="@/assets/media/fl-t-r.webp" alt="huyhien" width="600" />
        <img src="@/assets/media/fl-t-l.webp" class="position-absolute img-t-l" alt="huyhien" width="500">

        <div class="center-a-div">
            <p class="text-uppercase text-center fw-semibold text-description" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-once="false">
                weddings
            </p>
            <div class="bride-and-groom d-flex align-items-center justify-content-center" data-aos="fade-up"
                data-aos-delay="100" data-aos-duration="1200" data-aos-easing="ease-in-out" data-aos-once="false">
                <p>Minh Huy</p>
                <div>
                    <img src="@/assets/media/left.png" class="img-fluid mx-3" alt="">
                </div>
                <p>Thu Hiền</p>
            </div>
            <p class="text-uppercase text-center fw-semibold text-description" data-aos="fade-up" data-aos-delay="150"
                data-aos-duration="1400" data-aos-easing="ease-in-out" data-aos-once="false">
                we are getting married
            </p>
        </div>


        <!-- <div class="position-absolute img-bottom-section w-100">
            <div class="d-flex justify-content-between">
                <img src="@/assets/media/fl-b-l.png" alt="" class="img-fluid d-lg-block d-none">
                <img src="@/assets/media/fl-b-c.png" alt="" class="">
                <img src="@/assets/media/fl-b-r.png" alt="" class="img-fluid img-fluid d-lg-block d-none">
            </div>
        </div> -->
    </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");

.first-section {
    color: white;
    min-height: calc(100vh - 20px);
    // background-color: #fbb8ac;
    background-color: #c0d4ad;

    .img-t-l {
        right: 0;
    }

    .bride-and-groom {
        width: 1200px;

        p {
            font-family: "Great Vibes", cursive;
            font-size: 100px;
            font-weight: 600;
            letter-spacing: 2px;
        }

    }

    p {
        &.text-description {
            font-family: "Prata";
            font-size: 20px;
            letter-spacing: 8px;
        }
    }

    .img-bottom-section {
        bottom: 0;
        left: 0;

        img:nth-child(2) {
            position: absolute;
            bottom: 0;
            left: 100%;
            transform: translate(-50%, 0);
        }
    }
}

@media screen and (max-width: 768px) {
    .first-section {
        >img {
            width: 400px;
        }

        >img:nth-child(2) {
            display: none;
        }

        .bride-and-groom {
            flex-direction: column;
            width: 100vh;

            p {
                font-size: 50px;
                letter-spacing: 1px;
            }

        }

        p {
            &.text-description {
                font-size: 14px;
            }
        }

        .img-bottom-section {
            img:nth-child(2) {
                width: 400px;
            }
        }
    }
}
</style>
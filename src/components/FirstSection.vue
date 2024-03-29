<template>
    <div class="first-section position-relative">
        <img src="@/assets/media/fl-t-r.png" alt="huyhien" />
        <img src="@/assets/media/fl-t-l.png" class="position-absolute img-t-l" alt="huyhien">

        <div class="center-a-div">
            <p class="text-uppercase text-center fw-semibold text-description">
                weddings
            </p>
            <div class="bride-and-groom d-flex align-items-center">
                <p>Minh Huy</p>
                <div>
                    <img src="@/assets/media/left.png" class="img-fluid mx-3" alt="">
                </div>
                <p>Thu Hiền</p>
            </div>
            <p class="text-uppercase text-center fw-semibold text-description">
                we are getting married
            </p>
        </div>


        <div class="position-absolute img-bottom-section w-100">
            <div class="d-flex justify-content-between">
                <img src="@/assets/media/fl-b-l.png" alt="" class="img-fluid d-lg-block d-none">
                <img src="@/assets/media/fl-b-c.png" alt="" class="">
                <img src="@/assets/media/fl-b-r.png" alt="" class="img-fluid img-fluid d-lg-block d-none">
            </div>
        </div>




    </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Playfair&display=swap');
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
        p {
            font-family: "Playfair", serif;
            font-size: 100px;
            font-weight: 500;
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
            left: 50%;
            transform: translate(-50%, 0);
        }
    }


    // p {
    //     font-family: "Playfair Display";
    //     z-index: 1;
    //     height: auto;
    //     width: auto;
    //     color: rgb(251, 156, 140);
    //     text-decoration: none;
    //     white-space: nowrap;
    //     min-height: 0px;
    //     min-width: 0px;
    //     max-height: none;
    //     max-width: none;
    //     text-align: inherit;
    //     line-height: 450px;
    //     letter-spacing: 0px;
    //     font-weight: 400;
    //     font-size: 500px;
    //     top: 40%;
    // }

    // .img-wedding {
    //     z-index: 2;
    //     top: 55%;
    //     left: 40%;

    //     .img-wedding-2 {
    //         position: absolute;
    //         left: 65%;
    //         top: 25%;
    //     }

    // }
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
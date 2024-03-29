<template>
    <div class="third-section position-relative">
        <div class="third-section-content mx-auto mb-5">
            <div class="image-box text-center">
                <div class="image-box-inner">
                    <img src="https://wendola-nuxt.vercel.app/images/resource/countdown-1.jpg" alt="">
                    <div class="flower-box center-a-div">
                        <div class="icon-flower"></div>
                    </div>
                </div>
            </div>
            <div class="caption-box position-relative text-center">
                <div class="text">Ngày cưới của chúng tôi sắp tới</div><span class="icon-divider-img"></span>
            </div>
        </div>
        <div class="time-counter d-flex align-items-center justify-content-center">
            <span class="count">{{ days > 9 ? days : days < 0 ? 0 : `0${days}` }}</span>
                    <sub>Ngày</sub>
                    <span class="count">{{ hours > 9 ? hours : hours < 0 ? 0 : `0${hours}` }}</span>
                            <sub>Giờ</sub>
                            <span class="count">{{ minutes > 9 ? minutes : minutes < 0 ? 0 : `0${minutes}` }}</span>
                                    <sub>Phút</sub>
                                    <span class="count">{{ seconds > 9 ? seconds : seconds < 0 ? 0 : `0${seconds}`
                                            }}</span>
                                            <sub>Giây</sub>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            date: 'May 02, 2024 17:30:00',
            days: "",
            hours: "",
            minutes: "",
            seconds: ""
        }
    },

    methods: {
        estimateTime() {
            const countDownDate = new Date(this.date).getTime();
            this.timer = setInterval(() => {
                let now = new Date().getTime();
                let distance = countDownDate - now;
                this.days = Math.floor(distance / (1000 * 60 * 60 * 24));
                this.hours = Math.floor(
                    (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
                );
                this.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                this.seconds = Math.floor((distance % (1000 * 60)) / 1000);
            }, 1000);
        },
    },

    mounted() {
        this.estimateTime()
    }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");

.third-section {
    padding: 220px 0 50px 0;
    font-family: 'Prata';

    .third-section-content {
        width: 1100px;

        .image-box {
            margin-bottom: 220px;

            .image-box-inner {
                position: absolute;
                top: 10%;
                left: 50%;
                transform: translate(-50%, -50%);

                img {
                    border-radius: 50%;
                }

                .flower-box {
                    .icon-flower {
                        animation: spin 100s linear infinite;
                        background-image: url('https://wendola-nuxt.vercel.app/_nuxt/flowers-1.BsNB3zuG.png');
                        height: 641px;
                        width: 669px;
                    }
                }
            }


        }


        .caption-box {
            .text {
                font-size: 16px;
                font-weight: 800;
                letter-spacing: 2px;
                line-height: 1.2em;
                margin-bottom: 5px;
                position: relative;
                text-transform: uppercase;
            }

            .icon-divider-img {
                height: 22px;
                width: 172px;
                display: inline-flex;
                background-image: url('@/assets/media/divider1.png');
            }
        }

    }

    .time-counter {
        .count {
            display: block;
            font-size: 70px;
            font-weight: 400;
            line-height: 1em;
            margin-left: 110px;
            position: relative;
            text-align: center;
        }

        sub {
            font-size: 18px;
            font-weight: 400;
            margin-top: 40px;
            position: relative;
        }
    }
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(1turn);
    }
}
</style>

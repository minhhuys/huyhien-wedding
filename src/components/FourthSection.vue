<template>
    <section class="parallax">
        <div class="parallax-inner">
            <div class="card mx-auto">
                <div class="card-body p-5 position-relative" v-if="!isMessaged">
                    <h2>Bạn sẽ tham dự?</h2>

                    <div class="rdio rdio-primary radio-inline">
                        <input type="radio" class="ml-1" name="optradio" id="rdio1" :checked="willJoin"
                            @input="changeEvent(true)">
                        <label for="rdio1">
                            Có
                        </label>
                    </div>

                    <div class="rdio rdio-primary radio-inline">
                        <input type="radio" class="ml-1" name="optradio" id="rdio2" :checked="!willJoin"
                            @input="changeEvent(false)">
                        <label for="rdio2"> Không thể tham dự </label>
                    </div>

                    <div v-if="!willJoin">
                        <p class="unhappy mt-3 text-muted">🥲 Oops! Thật đáng tiếc, đừng lo lắng, chúng tôi vẫn ghi nhận
                            sự có mặt
                            của
                            bạn qua 1 trong 2
                            nền tảng sau 😅:</p>
                        <div class="d-flex align-items-center justify-content-between text-center">
                            <div class="qr-groom">
                                <img src="@/assets/media/qr-huy.jpg" width="150" alt="">
                                <p>Nhà trai</p>
                            </div>
                            <div class="d-lg-block d-none">
                                <img src="@/assets/media/left.png" class="img-fluid mx-3" alt="">
                            </div>
                            <div class="qr-groom">
                                <img src="@/assets/media/qr-huy.jpg" width="150" alt="">
                                <p>Nhà gái</p>
                            </div>
                        </div>
                    </div>


                    <form class="form">
                        <input type="text" v-model="name" placeholder="Tên của bạn"
                            class="form-control form-control-solid mt-3">

                        <input v-if="willJoin" type="text" v-model="comeupwith"
                            placeholder="Bạn sẽ đi với ai? VD: sự cô đơn, bạn X..."
                            class="form-control form-control-solid mb-3">

                        <textarea name="participant-wish" cols="30" rows="8" placeholder="Lời chúc"
                            v-model="message"></textarea>

                        <button class="btn btn-primary" @click.prevent="sendMessage">Gửi thông điệp</button>
                    </form>
                </div>
                <div class="card-body" v-else>
                    <div class="promotion">
                        <div class="wedding-thanksful">
                            <div class="thanksful-title" id="confeti">
                                <img src="@/assets/media/cracker.png" alt />
                                <p class="mb-0">Cảm ơn bạn đã xác nhận sự tham dự</p>
                            </div>
                            <div class="add-to-calendar">
                                <p class="mb-0 mr-3">Thêm sự kiện này vào calendar của bạn</p>
                                <add-to-calendar-button name="Huy Hiền's Wedding"
                                    description="Cảm ơn bạn đã nhận lời đến chung vui cùng Huy và Hiền 🥳"
                                    startDate="2024-05-02" startTime="17:30" endDate="2024-05-02" endTime="23:00"
                                    timeZone="Asia/Saigon"
                                    location="Sen Tây Hồ, 127 Nhật Chiêu, Nhật Tân, Tây Hồ, Hà Nội"
                                    options="'Google','Apple'" listStyle="dropdown-static" buttonStyle="flat"
                                    trigger="click" lightMode="light"></add-to-calendar-button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
const TOKEN = `6943323952:AAFRbnTRCuynz_sGhKSOgQP8RkCjyNUwyOo`;
const GROUP_ID = `-4179900065`
const TOKEN_CNAME = "is_wished";
import 'add-to-calendar-button';

export default {
    data() {
        return {
            willJoin: true,
            name: "",
            comeupwith: "",
            message: "",
            isMessaged: false
        }
    },

    methods: {
        changeEvent(join) {
            this.willJoin = join
        },

        setCookie(cname, cvalue, exdays) {
            var d = new Date();
            d.setTime(d.getTime() + exdays * 24 * 60 * 60 * 1000);
            var expires = "expires=" + d.toUTCString();
            document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
        },

        getCookie(cname) {
            var name = cname + "=";
            var decodedCookie = decodeURIComponent(document.cookie);
            var ca = decodedCookie.split(";");
            for (var i = 0; i < ca.length; i++) {
                var c = ca[i];
                while (c.charAt(0) == " ") {
                    c = c.substring(1);
                }
                if (c.indexOf(name) == 0) {
                    return c.substring(name.length, c.length);
                }
            }
            return "";
        },

        async sendMessage() {

            if (!this.name || !this.message) return;

            let data = {
                name: this.name,
                comeupwith: this.comeupwith,
                message: this.message,
            };

            // eslint-disable-next-line
            let template = `Tên: \*${data.name}*%0AĐi cùng: \*${data.comeupwith}*%0AThông điệp: \*${data.message}*`;

            const url = `https://api.telegram.org/bot${TOKEN}/sendMessage?chat_id=${GROUP_ID}&parse_mode=markdown&text=${template}`;

            await fetch(url, {
                method: "GET",
                headers: {
                    "Content-Type": "application/json",
                },
            }).then((response) => {
                console.log(response.json())
            }).then(() => {
                this.setCookie(TOKEN_CNAME, true, 30);
                this.isMessaged = true
            });
        }
    },

    mounted() {
        let cookie = this.getCookie(TOKEN_CNAME);
        if (cookie) {
            this.isMessaged = true;
        }
    }
}
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");

.parallax {
    background: url('https://images.pexels.com/photos/192136/pexels-photo-192136.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940') repeat fixed 100%;
    background-size: cover;
    color: aliceblue;
    padding: 100px 0;
    font-family: 'Prata';

    .card {
        max-width: 500px;
        color: #212529;
        background-image: url('@/assets/media/flower-form.png');
        background-position: center right;
        background-repeat: no-repeat;

        .card-body {
            &:before {
                animation: zoom-two 5s linear infinite;
                background-image: url('@/assets/media/fl-card-t-r.png');
                background-repeat: no-repeat;
                content: "";
                height: 200px;
                position: absolute;
                right: -40px;
                top: -30px;
                width: 206px;
            }

            &:after {
                animation: zoom-two 5s linear infinite;
                background-image: url('@/assets/media/fl-card-b-l.png');
                background-repeat: no-repeat;
                content: "";
                height: 200px;
                position: absolute;
                left: -40px;
                bottom: -30px;
                width: 206px;
            }

        }
    }

    p.unhappy {
        font-size: 14px;
    }

    input[type="text"] {
        width: 100%;
        height: 56px;
        background-color: #f0f1f1;
        border-radius: 4px;
        font-size: 16px;
        padding-left: 15px;
        border: none;
        outline: none;
        margin-bottom: 15px;
    }


    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    textarea {
        width: 100%;
        resize: none;
        background-color: #f0f1f1;
        border-radius: 4px;
        font-size: 16px;
        padding: 15px;
        border: none;
        outline: none;
        margin-bottom: 15px;
    }

    button {
        width: 100%;
        height: 56px;
        background-color: #c0d4ad;
        border-radius: 2px;
        color: white;
        border: none;
        font-weight: 600;
        font-size: 18px;
        font-weight: 700;
        outline: none;
        cursor: pointer;

        &:hover {
            background-color: #c0d4ad;
        }
    }

    .wedding-thanksful {
        margin: 20px 0;
        border: 1px solid #c0d4ad;
        border-radius: 2px;

        .thanksful-title {
            height: 65px;
            line-height: 65px;
            background: #c0d4ad;
            display: flex;
            align-items: center;
            justify-content: center;

            img {
                margin-right: 8px;
            }

            p {
                font-weight: 600;
            }
        }

        .add-to-calendar {
            display: flex;
            align-items: center;
            margin: 16px 0;
            padding: 0 16px;

            p {
                font-size: 14px;
            }

            p,
            button {
                width: 50%;
            }

            button {
                display: flex;
                align-items: center;
                justify-content: center;
                background: #dd902c;
                border: none;
                outline: none;
                height: 40px;
                color: white;
                font-weight: 600;
                border-radius: 2px;
            }
        }
    }


    .rdio {
        position: relative;

        input[type="radio"] {
            opacity: 0;
        }

        label {
            padding-left: 10px;
            cursor: pointer;
            margin-bottom: 7px !important;

            &:before {
                width: 18px;
                height: 18px;
                position: absolute;
                top: 1px;
                left: 0;
                content: '';
                display: inline-block;
                -moz-border-radius: 50px;
                -webkit-border-radius: 50px;
                border-radius: 50px;
                border: 1px solid #c0d4ad;
                background: #fff;
            }
        }

        input[type="radio"] {
            margin: 0px;

            &:disabled+label {
                color: #999;

                &:before {
                    background-color: #c0d4ad;
                }
            }

            &:checked+label::after {
                content: '';
                position: absolute;
                top: 5px;
                left: 4px;
                display: inline-block;
                font-size: 11px;
                width: 10px;
                height: 10px;
                background-color: #c0d4ad;
                -moz-border-radius: 50px;
                -webkit-border-radius: 50px;
                border-radius: 50px;
            }
        }
    }

    .rdio-default input[type="radio"]:checked+label:before {
        border-color: #c0d4ad;
    }

    .rdio-primary input[type="radio"]:checked+label {
        &:before {
            border-color: #c0d4ad;
        }

        &::after {
            background-color: #c0d4ad;
        }
    }

}

@keyframes zoom-two {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(.95);
    }

    100% {
        transform: scale(1);
    }
}


@media screen and (max-width: 768px) {
    .parallax {
        padding: 20px;

        .card-body {

            &::before,
            &::after {
                display: none;
            }
        }
    }
}
</style>
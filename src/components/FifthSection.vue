<template>
    <div class="fifth-section position-relative">
        <div class="fifth-section-header text-center my-5">
            <img src="@/assets/media/ring.jpeg" alt="" width="250" data-aos="fade-up" data-aos-delay="10"
                data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-once="false">

            <h1 data-aos="fade-up" data-aos-delay="20" data-aos-duration="1200" data-aos-easing="ease-in-out"
                data-aos-once="false">Our Memories</h1>
            <h6 class="header-subtitle" data-aos="fade-up" data-aos-delay="30" data-aos-duration="1400"
                data-aos-easing="ease-in-out" data-aos-once="false">
                happiness
            </h6>
        </div>

        <carousel :autoplay="true" :dots="false" :nav="false" autoWidth loop rewind>
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-6.jpg">
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-7.jpg">
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-8.jpg">
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-9.jpg">
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-3.jpg">
            <img src="https://gretnagreen.qodeinteractive.com/wp-content/uploads/2018/05/h1-img-2.jpg">
        </carousel>
    </div>
</template>

<script>
import carousel from 'vue-owl-carousel'

export default {
    components: { carousel },
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");

.fifth-section {
    font-family: 'Prata';

    .fifth-section-header {
        h1 {
            font-weight: 600;
        }

        .header-subtitle {
            position: relative;
            display: inline-block;
            padding: 0 12px;
            margin: 20px 0 0;
            display: inline-block;
            padding: 0 12px;
            margin: 20px 0 0;
            color: #979797;
            font-size: 16px;
            font-style: italic;

            &::before {
                left: -73px;
                content: "";
                position: absolute;
                top: 50%;
                width: 73px;
                height: 1px;
                background-color: #ccc;
            }

            &::after {
                right: -73px;
                content: "";
                position: absolute;
                top: 50%;
                width: 73px;
                height: 1px;
                background-color: #ccc;
            }
        }
    }
}
</style>
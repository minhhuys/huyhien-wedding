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
        <masonry
            :cols="3"
            :gutter="10"
            >
            <img src="@/assets/media/img-1.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-2.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1200" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-3.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1300" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-4.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1400" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-5.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1400" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-6.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1500" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-8.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1500" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-7.png" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1700" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-9.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1800" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-13.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="1900" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-10.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="2000" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-11.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="2100" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-12.webp" class="img-fluid mb-2" 
            data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="2200" data-aos-easing="ease-in-out" data-aos-once="false">
            <img src="@/assets/media/img-14.webp" class="img-fluid mb-2" data-aos="fade-up" data-aos-delay="50"
                data-aos-duration="2300" data-aos-easing="ease-in-out" data-aos-once="false">
        </masonry>
    </div>
</template>

<script>
import Vue from 'vue'
// import carousel from 'vue-owl-carousel'
import VueMasonry from 'vue-masonry-css'

Vue.use(VueMasonry);
export default {

}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Prata&display=swap");
.pinterest-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  grid-auto-rows: 10px;
  gap: 10px;
}

.grid-item {
  grid-row-end: span 2;
}

.grid-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

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
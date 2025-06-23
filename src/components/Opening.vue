<script setup>
import { ref } from "vue";
import moment from "moment";

const props = defineProps({ data: Object, caption: Object });
const deadline = ref("2025-06-25 18:30:00");

const saveCalendar = () => {
  const title = "&text=Tasyakuran Ulang Tahun ke 70 Kakung Suradi";
  const location = "Wonogiri";
  const dates =
    "&dates=" +
    moment(deadline.value).utc().format("YYYYMMDDTHHmmss[Z]") +
    "%2F" +
    moment(deadline.value).utc().format("YYYYMMDDTHHmmss[Z]");

  const url =
    "https://www.google.com/calendar/render?action=TEMPLATE" +
    title +
    location +
    dates;

  window.open(url, "_blank");
};
</script>
<template>
  <v-container height="100dvh" class="relative overflow-hidden p-0">
    <v-carousel
      height="100dvh"
      :show-arrows="false"
      :cycle="true"
      :interval="6000"
      hide-delimiters
    >
      <v-carousel-item
        v-for="(item, i) in props.data?.foto_opening"
        :key="i"
        :src="item"
        height="100dvh"
        cover
      ></v-carousel-item>
    </v-carousel>
    <div
      class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-gray-200/5 to-[#1E1E1E]"
    >
      <div class="p-5">
        <div
          class="absolute bottom-[12rem] left-0 w-full flex justify-center animate__animated animate__zoomIn animate__delay-1s"
        >
          <div class="w-full text-center">
            <div class="flex justify-center">
              <img
                src="/public/img/ultah.webp"
                alt=""
                class="w-[100px] h-[100px]"
              />
            </div>

            <vue3-flip-countdown
              countdownSize="1.4rem"
              labelSize=".8rem"
              mainColor="#fff"
              labelColor="#fff"
              :flipAnimation="false"
              :labels="{
                days: 'Hari',
                hours: 'Jam',
                minutes: 'Menit',
                seconds: 'Detik',
              }"
              :deadline="deadline"
              class="animate__animated animate__zoomIn animate__delay-2s t1xt-white"
            />

            <v-btn
              color="#69B8CF"
              prepend-icon="mdi-calendar"
              @click="saveCalendar"
              class="mt-3 animate__animated animate__zoomIn animate__delay-2s"
              rounded
            >
              Simpan Tanggal
            </v-btn>
          </div>
        </div>
      </div>
    </div>
    <div class="absolute bottom-5 left-0 animate__animated animate__zoomIn animate__delay-2s">
      <div class="px-3">
        <Splide
          :options="{
            type: 'loop',
            perPage: 3,
            autoplay: true,
            interval: 1000,
            pagination: false,
            arrows: false,
            gap: 10,
          }"
          aria-label="Vue Splide Example"
        >
          <SplideSlide v-for="item in props.data?.foto_opening" :key="item">
            <img
              :src="item"
              alt="Amantrana"
              class="w-full h-[150px] object-cover rounded-lg"
            />
          </SplideSlide>
        </Splide>
      </div>
    </div>
  </v-container>
</template>

<style>
.flip-clock__piece {
  margin: 0 10px !important;
}
</style>

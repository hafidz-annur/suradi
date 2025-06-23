<script setup>
import moment from "moment";

const props = defineProps({ data: Object });
</script>
<template>
  <v-container height="70dvh" class="relative p-0 overflow-hidden">
    <img
      :src="props.data?.foto_opening[1]"
      alt="Amantrana"
      class="w-full h-full object-cover"
    />
    <div
      class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-[#1E1E1E]/50 to-[#1E1E1E] py-10"
    >
      <div class="flex justify-center items-center px-5 h-full">
        <div class="text-center w-full">
          <div class="flex justify-center">
            <div class="w-[70%]">
              <div data-aos="fade-left" data-aos-delay="1000">
                <div class="p-5 py-2">
                  <div
                    class="flex justify-center animate__animated animate__zoomIn"
                  >
                    <img
                      src="/public/img/ultah.webp"
                      alt=""
                      class="w-[50px] h-[50px]"
                    />
                  </div>
                  <h4 class="text-5xl text-white text-nowrap">Tasyakuran</h4>
                </div>
                <div>
                  <div
                    class="flex justify-center items-center gap-3 md:px-10 px-2"
                  >
                    <div class="w-40">
                      <v-divider thickness="3" color="white" opacity="1" />
                      <p class="my-2 text-center text-2xl">Rabu</p>
                      <v-divider thickness="3" color="white" opacity="1" />
                    </div>
                    <div class="w-20">
                      <p class="text-lg">2025</p>
                      <p class="text-3xl">25</p>
                      <p class="text-lg">18.30</p>
                    </div>
                    <div class="w-40 text-center">
                      <v-divider thickness="3" color="white" opacity="1" />
                      <p class="my-2 text-2xl">Juni</p>
                      <v-divider thickness="3" color="white" opacity="1" />
                    </div>
                  </div>
                  <div class="text-center">
                    <p class="mt-5 text-[14px]">
                      Toko Bangunan Laris Berkah, Jatipurno, Jatipurno
                      KAB. WONOGIRI, JATIPURNO, JAWA TENGAH, ID, 57693
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </v-container>
</template>

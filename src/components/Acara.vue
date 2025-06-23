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
          <p class="mb-10" data-aos="zoom-in" data-aos-delay="500">
            Bergabunglah bersama kami untuk menyaksikan dan merayakan momen
            penuh syukur ini. Kami ingin Anda menjadi bagian dari hari istimewa
            kami dalam merayakan 70 tahun perjalanan hidup yang penuh makna.
          </p>

          <div class="flex justify-center">
            <div class="w-[70%]">
              <div data-aos="fade-left" data-aos-delay="1000">
                <div class="p-5 py-2">
                  <v-icon
                    icon="mdi-book-heart-outline"
                    class="mb-2"
                    size="25"
                    color="white"
                  ></v-icon>
                  <h4 class="text-2xl text-white text-nowrap">Akad Nikah</h4>
                </div>
                <div>
                  <div
                    class="flex justify-center items-center gap-3 md:px-10 px-2"
                  >
                    <div class="w-40">
                      <v-divider thickness="3" color="white" opacity="1" />
                      <p class="my-2 text-center">
                        {{ props.data?.acara?.akad_nikah?.hari }}
                      </p>
                      <v-divider thickness="3" color="white" opacity="1" />
                    </div>
                    <div class="w-20">
                      <p>
                        {{ props.data?.acara?.akad_nikah?.tahun }}
                      </p>
                      <p class="text-3xl">
                        {{ props.data?.acara?.akad_nikah?.tanggal }}
                      </p>
                      <p></p>
                    </div>
                    <div class="w-40 text-center">
                      <v-divider thickness="3" color="white" opacity="1" />
                      <p class="my-2">
                        {{ props.data?.acara?.akad_nikah?.bulan }}
                      </p>
                      <v-divider thickness="3" color="white" opacity="1" />
                    </div>
                  </div>
                  <div class="text-center mt-4">
                    <p>
                      {{ props.data?.acara?.akad_nikah?.waktu }}
                    </p>
                    <p>
                      {{ props.data?.acara?.akad_nikah?.tempat }}
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

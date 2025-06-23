<script setup>
const props = defineProps({ name: String, data: Object });

const emits = defineEmits(["selected"]);
const openInvitation = () => {
  emits("selected", "Pembukaan");
};
</script>
<template>
  <v-container height="100dvh" class="relative p-0 overflow-hidden">
    <img
      src="/public/img/galeri/4.webp"
      alt=""
      class="h-full scale-[1.4] object-cover object-bottom"
    />

    <div
      class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-gray-200/5 to-gray-800"
    >
      <div class="absolute bottom-10 left-0 w-full flex justify-center">
        <div class="text-center pt-10">
          <div class="flex justify-center animate__animated animate__zoomIn">
            <img
              src="/public/img/ultah.webp"
              alt=""
              class="w-[50px] h-[50px]"
            />
          </div>
          <p
            class="font-bold text-[#CFB893] text-[14px] uppercase text-dark animate__animated animate__zoomIn my-2"
          >
            Tasyakuran Ulang Tahun
          </p>
          <h1
            class="text-5xl animate__animated animate__zoomIn animate__delay-1s my-2"
          >
            Kakung Suradi
          </h1>

          <h1
            class="text-8xl text-[#CFB893] font-bold animate__animated animate__zoomIn animate__delay-1s my-2"
          >
            70 <sup>th</sup>
          </h1>
          <v-btn
            @click="openInvitation"
            color="#CFB893"
            prepend-icon="mdi-email-open-heart-outline"
            class="mt-5 animate__animated animate__zoomIn animate__delay-2s"
            rounded
          >
            Buka Undangan
          </v-btn>
        </div>
      </div>
    </div>
  </v-container>
</template>

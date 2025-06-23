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
      src="/public/img/galeri/6.jpg"
      alt=""
      class="h-full scale-[1.4] object-cover object-bottom"
    />

    <div
      class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-[#1E1E1E]/50 to-[#1E1E1E]"
    >
      <div class="absolute bottom-10 left-0 w-full flex justify-center">
        <div class="text-center pt-10">
          <p
            class="font-bold text-[#fad6b2] text-[14px] uppercase text-dark animate__animated animate__zoomIn  my-2"
          >
            Tasyakuran Ulang Tahun
          </p>
          <h1
            class="text-5xl animate__animated animate__zoomIn animate__delay-1s my-2"
          >
            Kakung Suradi
          </h1>

          <h1
            class="text-8xl text-[#a07951] font-bold animate__animated animate__zoomIn animate__delay-1s my-2"
          >
            70 <sup>th</sup>
          </h1>
          <v-btn
            @click="openInvitation"
            color="primary"
            size="small"
            prepend-icon="mdi-email-open-heart-outline"
            class="mt-5 animate__animated animate__zoomIn animate__delay-2s"
          >
            Buka Undangan
          </v-btn>
        </div>
      </div>
    </div>
  </v-container>
</template>

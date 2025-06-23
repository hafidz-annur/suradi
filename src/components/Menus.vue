<script setup>
import { ref, onMounted, watch } from "vue";

const props = defineProps({ data: String, active: String });
const emit = defineEmits(["selected"]);

let intervalId;
const audio = ref(null);
const autoplay_menu = ref(false);
const autoplay_music = ref(false);
const menus = ref([
  {
    icon: "mdi-home",
    title: "Pembukaan",
  },
  {
    icon: "mdi-calendar-star",
    title: "Acara",
  },
  {
    icon: "mdi-emoticon-wink-outline",
    title: "Penutupan",
  },
]);

const selected = ref(null);
const selectedMenu = () => {
  emit("selected", selected.value);
  if (autoplay_menu.value) {
    autoplay_menu.value = false;
    clearInterval(intervalId);
  }
};

const autoplayMenu = () => {
  if (autoplay_menu.value) {
    let index = menus.value.findIndex((menu) => menu.title === selected.value);
    const menus_count = menus.value.length;

    intervalId = setInterval(() => {
      if (index >= menus_count) {
        autoplay_menu.value = false;
        selected.value = "Pembukaan";
        clearInterval(intervalId);
        emit("selected", selected.value);
        return;
      }

      const element = menus.value[index].title;
      selected.value = element;
      emit("selected", selected.value);
      index++;
    }, 5000);
  } else {
    clearInterval(intervalId);
  }
};

const playMusic = () => {
  if (!audio.value) return;

  if (audio.value.paused) {
    audio.value
      .play()
      .then(() => {
        autoplay_music.value = true;
      })
      .catch((err) => {
        console.error("Audio play failed:", err);
      });
  } else {
    audio.value.pause();
    autoplay_music.value = false;
  }
};

watch(() => {
  if (props.active) {
    selected.value = props.active;
  }
});

onMounted(() => {
  audio.value = new Audio(props.data?.musik);
  autoplay_menu.value = true;
  // autoplayMenu();
  // playMusic();
});
</script>

<template>
  <div class="fixed top-[10px] left-0 w-full z-[9999] flex flex-col">
    <div class="flex justify-between px-5">
      <v-btn
        size="x-small"
        color="primary"
        :icon="!autoplay_menu ? 'mdi-play-outline' : 'mdi-pause'"
        @click="
          autoplay_menu = !autoplay_menu;
          autoplayMenu();
        "
        class="mb-2"
      />
      <v-btn
        size="x-small"
        color="primary"
        :icon="!autoplay_music ? 'mdi-volume-off' : 'mdi-volume-high'"
        @click="playMusic()"
      />
    </div>
  </div>
</template>

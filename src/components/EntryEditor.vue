<script lang="ts" setup>
import EmojiField from "@/components/EmojiField.vue";
import ArrowCircleRight from "@/assets/icons/arrow-circle-right.svg";
import { Ref, ref, computed } from "vue";
import Emoji from "@/types/Emoji";

const text = ref("");

//Settiamo il valorer di emoji tipizzando con Emoji o null
const emoji: Ref<Emoji | null> = ref(null);
//Non possiamo quindi assegnare valori diversi da quelli specificati nel modello
//Errore
//emoji.value = "sdsp"

const chartCount = computed(() => text.value.length);
</script>
<template>
  <form class="entry-form" @submit.prevent>
    <textarea
      v-model="text"
      placeholder="New Journal Entry for danielkelly_io"
    ></textarea>
    <EmojiField v-model="emoji" />
    <div class="entry-form-footer">
      <span>{{ chartCount }} / 280</span>
      <button>Remember <ArrowCircleRight width="20" /></button>
    </div>
  </form>
</template>

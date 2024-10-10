<script setup lang="ts">
import TheHeader from "@/components/TheHeader.vue";
import EntryEditor from "./components/EntryEditor.vue";
import EntryCard from "@/components/EntryCard.vue";
import { reactive } from "vue";
import User from "@/types/User";
//Esempio di funzione in TS
//const sum = (x: number, y: numberber) => x + y;

//in caso di errore ci viene subito segnalato
//sum(1, 3);

const user: User = reactive({
  id: 1,
  username: "pippo",
  settings: [],
});

console.log(user);
</script>

<template>
  {{ user.id }}
  <main class="container m-auto p-10">
    <TheHeader />
    <EntryEditor />
    <ul>
      <li>
        <EntryCard />
      </li>
    </ul>
  </main>
</template>

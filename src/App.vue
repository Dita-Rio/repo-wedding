<script setup lang="ts">
import Invitation from './components/Invitation.vue';
import Heading from './components/Heading.vue';
import { reactive } from 'vue';
import TheBride from './components/TheBride.vue';
import TheGroom from './components/TheGroom.vue';
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
const state = reactive({ render: false });
</script>

<template>
  <div
    class="scroller flex flex-wrap justify-center max-w-md w-screen h-screen"
  >
    <Invitation @render="(value) => (state.render = value)" />
    <Heading v-if="state.render" />
    <TheBride v-if="state.render" />
    <TheGroom v-if="state.render" />
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&family=Tangerine:wght@700&display=swap');
</style>

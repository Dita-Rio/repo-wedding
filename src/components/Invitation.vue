<template>
  <section
    id="opener"
    class="flex flex-col fixed items-center top-0 bottom-0 justify-end w-screen h-screen pb-8 text-white invitation"
  >
    <h3 class="name-animate iskry text-3xl tracking-widest">DITA - RIO</h3>
    <p class="mt-5 muli font-light">Dear :</p>
    <span class="font-bold">Syahrizal</span>
    <span
      class="p-3 mt-8 text-sm font-light rounded-3xl muli cursor-pointer bg-black text-white"
      v-on:click="close()"
      >Buka Undangan
    </span>
  </section>
</template>

<script lang="ts" setup>
const emit = defineEmits(['render']);

const close = () => {
  emit('render', true);
  document.getElementById('opener')?.classList.add('close-invitation');
};
</script>

<style>
/*
The CSS export should solely be used as a reference.
For a more detailed animation export the JSON file should be used.
*/
.name-animate {
  animation: slide_right 1200ms 0ms ease-in-out forwards;
}

.close-invitation {
  animation: close_invitation 1200ms 0ms ease-in-out forwards;
}

@keyframes slide_right {
  from {
    transform: translateX(-300%);
  }
  to {
    transform: translateX(0);
  }
}

@keyframes close_invitation {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-1000%);
  }
}
</style>

<template>
  <section
    class="groom flex flex-col text-white w-screen h-screen justify-between"
  >
    <h4
      class="muli-light px-8 py-6 text-2xl font-light"
      :class="state.isShow ? 'surat-animate' : ''"
    >
      The <br />
      Groom
    </h4>
    <div
      class="card flex flex-col name-animate bg-black/[.25] border-2 w-full px-16 py-12 h-1/2 rounded-tl-3xl rounded-tr-3xl -mb-2 muli-light"
    >
      <span class="name muli-light">Rio Dwi Ugroseno </span>
      <br />
      <div class="muli-light text-xs">
        <strong>Putra kedua dari</strong>
        <span> Bapak Aris Ruslan dan Ibu Nirwana</span>
      </div>
    </div>
  </section>
</template>
<script lang="ts" setup>
import { onMounted, reactive } from 'vue';
import { isInViewport } from '../utils/screen';

const state = reactive({
  isShow: false
});

const scrollEvent = (e: any) => {
  isInViewport(document.querySelector('.groom') as HTMLElement)
    ? (state.isShow = true)
    : (state.isShow = false);
};

onMounted(() => {
  window.addEventListener('scroll', scrollEvent, true);
});
</script>

<style>
.hairline-groom {
  margin: auto;
  width: 50px;
  border: 1px solid white;
  content: '';
  height: 1px;
}
</style>

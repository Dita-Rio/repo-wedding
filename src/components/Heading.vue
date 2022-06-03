<template>
  <section
    id="opener"
    class="flex flex-col p-5 justify-end bg-black w-screen h-screen pb-8 text-white heading"
  >
    <div class="heading-wrapper">
      <h3 class="text-2xl tracking-widest muli name-animate">
        THE WEDDING <br />
        DITA & RIO
      </h3>
      <div class="date-time flex w-full text-sm font-light sfpro">
        <div
          class="date border-y-2 border-r-2 p-4 w-full flex justify-between items-center"
        >
          <span>Date</span> <span>02-07-2022</span>
        </div>
        <div class="date border-y-2 p-4 w-full flex flex-row justify-between">
          <div class="days flex flex-col justify-center items-center">
            <span>{{ state.days }}</span>
            <span>Days</span>
          </div>
          <div class="time flex flex-col items-center">
            <span>{{ state.hour }}</span>
            <span>Hours</span>
          </div>
        </div>
      </div>
      <div class="surat-animate">
        <span class="text-bold"
          >Assalamualaikum warahmatullahi <br />
          wabarakatuh
        </span>
        <br />
        <small>
          “Dan di antara tanda-tanda kekuasaan-Nya ialah Dia menciptakan untukmu
          pasangan-pasangan dari jenismu sendiri, supaya kamu cenderung dan
          merasa tenteram kepadanya, dan dijadikan-Nya diantaramu rasa kasih dan
          sayang. Sesungguhnya pada yang demikian itu benar-benar terdapat
          tanda-tanda bagi kaum yang berfikir.”
          <br />
        </small>
        <span class="mt-5 text-sm">(QS Ar-Rum : 21)</span>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
import dayjs from 'dayjs';
import duration from 'dayjs/plugin/duration';
import relativeTime from 'dayjs/plugin/relativeTime';
import { computed, reactive } from 'vue';

dayjs.extend(duration);
dayjs.extend(relativeTime);

const state = reactive({
  days: 0,
  hour: 0
});

var countDownDate = new Date('Jul 2, 2022 09:00:00').getTime();

// Update the count down every 1 second
var x = setInterval(function () {
  // Get today's date and time
  var now = new Date().getTime();

  // Find the distance between now and the count down date
  var distance = countDownDate - now;

  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);

  state.days = days;
  state.hour = hours;
  // Display the result in the element with id="demo"
}, 1000);
</script>

<style>
/*
The CSS export should solely be used as a reference.
For a more detailed animation export the JSON file should be used.
*/

.surat-animate {
  animation: slide_bottom 1200ms 0ms ease-in-out forwards;
}

.close-invitation {
  animation: close_invitation 1200ms 0ms ease-in-out forwards;
}

@keyframes slide_bottom {
  from {
    transform: translateY(300%);
  }
  to {
    transform: translateY(0);
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

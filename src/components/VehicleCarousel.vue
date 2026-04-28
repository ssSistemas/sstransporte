<template>
  <section class="vehicle-carousel-section">
    <div class="section-header">
      <span class="section-label">Nossa frota</span>
      <h2>Veículos para transporte empresarial</h2>
      <p>
        Ônibus, micro-ônibus e vans para atender empresas em Serra do
        Salitre/MG, EuroChem e região.
      </p>
    </div>

    <div class="vehicle-carousel">
      <button class="carousel-btn left" @click="previousSlide">‹</button>

      <div class="carousel-image-wrapper">
        <img
          :src="vehicles[currentIndex].image"
          :alt="vehicles[currentIndex].alt"
          class="carousel-image"
        />

        <div class="carousel-caption">
          <h3>{{ vehicles[currentIndex].title }}</h3>
          <p>{{ vehicles[currentIndex].description }}</p>
        </div>
      </div>

      <button class="carousel-btn right" @click="nextSlide">›</button>
    </div>

    <div class="carousel-dots">
      <button
        v-for="(vehicle, index) in vehicles"
        :key="vehicle.title"
        class="dot"
        :class="{ active: currentIndex === index }"
        @click="goToSlide(index)"
        :aria-label="`Ver veículo ${index + 1}`"
      ></button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from "vue";

import onibusSsFacility from "../assets/onibusSsfacility.png";
import vanSsFacility from "../assets/vanSsFacility.png";

const currentIndex = ref(0);

const vehicles = [
  {
    title: "Ônibus SS Facility",
    description:
      "Ideal para transporte diário de equipes, empresas, obras e operações industriais.",
    image: onibusSsFacility,
    alt: "Ônibus branco da SS Facility Transporte Empresarial",
  },
  {
    title: "Van SS Facility",
    description:
      "Perfeita para transporte de grupos menores, com conforto e segurança.",
    image: vanSsFacility,
    alt: "Van branca da SS Facility Transporte Empresarial",
  },
];

function nextSlide() {
  currentIndex.value = (currentIndex.value + 1) % vehicles.length;
}

function previousSlide() {
  currentIndex.value =
    currentIndex.value === 0 ? vehicles.length - 1 : currentIndex.value - 1;
}

function goToSlide(index: number) {
  currentIndex.value = index;
}
</script>

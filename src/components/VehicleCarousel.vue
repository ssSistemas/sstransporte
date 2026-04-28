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
    title: "Ônibus Executivo 46 Lugares",
    description:
      "Ônibus confiável, equipado com motor Mercedes-Benz, ideal para transporte empresarial diário. Veículo com capacidade para 46 passageiros, manutenção em dia e revisões constantes para garantir segurança, pontualidade e qualidade no atendimento.",
    image: onibusSsFacility,
    alt: "Ônibus SS Facility Transporte Empresarial com 46 lugares e motor Mercedes-Benz",
  },
  {
    title: "Van Renault Master 15 Lugares",
    description:
      "Van Renault Master ano 2016, muito confiável e ideal para transporte de equipes menores. Veículo com capacidade para 15 passageiros, manutenção em dia e revisões constantes, garantindo segurança, conforto e eficiência no transporte empresarial.",
    image: vanSsFacility,
    alt: "Van Renault Master SS Facility com 15 lugares para transporte empresarial",
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

<template>
  <main class="landing-transporte">
    <section class="hero">
      <div class="hero-content">
        <p class="tag">SS Facility Transporte Empresarial</p>

        <h1>
          Transporte empresarial em Serra do Salitre/MG para funcionários e
          equipes
        </h1>

        <p class="subtitle">
          Levamos colaboradores com segurança, pontualidade e conforto para
          empresas, obras, alojamentos, mineradoras e indústrias da região, com
          foco em rotas próximas à EuroChem.
        </p>

        <div class="actions">
          <a
            class="btn-primary"
            href="https://wa.me/553499577020"
            target="_blank"
          >
            Solicitar orçamento pelo WhatsApp
          </a>

          <a class="btn-secondary" href="#servicos"> Conhecer serviços </a>
        </div>
      </div>
    </section>
    <VehicleCarousel />
    <ServicesSection />
    <section class="section-destaque-seguranca">
      <div class="destaque-container">
        <div class="destaque-texto">
          <span class="badge">Segurança e confiança</span>

          <h2>
            Transporte empresarial com foco total em manutenção e segurança
          </h2>

          <p>
            A SS Facility Transporte Empresarial atua com responsabilidade e
            compromisso com a segurança dos passageiros. Nossa frota passa por
            manutenções constantes, garantindo veículos sempre revisados,
            seguros e prontos para operação.
          </p>

          <p>
            Trabalhamos com um padrão rigoroso de cuidado e inspeção, reduzindo
            riscos, evitando falhas e garantindo que sua equipe chegue ao
            destino com tranquilidade, conforto e pontualidade todos os dias.
          </p>

          <div class="destaque-itens">
            <div>✔ Manutenção preventiva constante</div>
            <div>✔ Veículos revisados e seguros</div>
            <div>✔ Compromisso com pontualidade</div>
            <div>✔ Transporte confiável para empresas</div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
<script setup lang="ts">
import VehicleCarousel from "../components/VehicleCarousel.vue";
import ServicesSection from "../components/ServicesSection.vue";
</script>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const baseUrl = import.meta.env.BASE_URL

const imagens = [
  `${baseUrl}images/massagem-1.jpg`,
  `${baseUrl}images/massagem-2.jpg`
]

const slideAtual = ref(0)

let intervalo: number | undefined

function proximoSlide() {
  slideAtual.value = (slideAtual.value + 1) % imagens.length
}

function mudarSlide(index: number) {
  slideAtual.value = index
}

onMounted(() => {
  intervalo = window.setInterval(() => {
    proximoSlide()
  }, 5000)
})

onUnmounted(() => {
  clearInterval(intervalo)
})
</script>

<template>
  <section id="inicio" class="relative min-h-screen overflow-hidden flex items-center">
    <div
      v-for="(imagem, index) in imagens"
      :key="index"
      class="absolute inset-0 bg-cover bg-center transition-opacity duration-1000"
      :class="slideAtual === index ? 'opacity-100' : 'opacity-0'"
      :style="{ backgroundImage: `url(${imagem})` }"
    ></div>

    <div class="absolute inset-0 bg-black/55"></div>
    <div class="absolute inset-0 bg-gradient-to-r from-black/75 via-black/35 to-transparent"></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6 w-full pt-24">
      <div class="max-w-2xl text-white">
        <span class="font-jetbrains inline-block mb-5 px-4 py-2 rounded-full bg-white/15 border border-white/20 text-sm font-semibold backdrop-blur-sm">
          Massoterapia e bem-estar
        </span>

        <h1 class="text-4xl md:text-6xl font-bold leading-tight">
          Alívio para o corpo. Calma para a mente.
        </h1>

        <p class="mt-6 text-lg md:text-xl text-white/90 leading-relaxed max-w-xl">
          Atendimento personalizado para reduzir dores musculares, aliviar o estresse e proporcionar uma experiência real de cuidado e relaxamento.
        </p>

        <div class="mt-8 flex flex-col sm:flex-row gap-4">
          <a
            href="https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20sessão%20de%20massoterapia."
            target="_blank"
            class="font-jetbrains inline-flex items-center justify-center bg-green-800 text-white px-8 py-4 rounded-lg font-semibold hover:bg-green-900 transition duration-300"
          >
            Agendar pelo WhatsApp
          </a>

          <a
            href="#servicos"
            class="font-jetbrains inline-flex items-center justify-center border border-white/80 text-white px-8 py-4 rounded-lg font-semibold hover:bg-white hover:text-gray-900 transition duration-300"
          >
            Conhecer serviços
          </a>
        </div>
      </div>
    </div>

    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 z-20 flex gap-3">
      <button
        v-for="(_, index) in imagens"
        :key="index"
        @click="mudarSlide(index)"
        class="h-1 rounded-full transition-all duration-300"
        :class="slideAtual === index ? 'w-12 bg-white' : 'w-8 bg-white/40'"
        type="button"
      ></button>
    </div>
  </section>
</template>

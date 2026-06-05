<script setup lang="ts">
import { ref } from 'vue'

const depoimentos = [
  {
    id: 1,
    categoria: 'Ombros',
    titulo: 'Alívio da tensão nos ombros',
    texto:
      'Cheguei com os ombros muito tensos depois de uma semana pesada. A sessão foi conduzida com calma e senti uma leveza real no corpo.',
    nome: 'Mariana S.',
    servico: 'Massagem Terapêutica',
    detalhe: 'Ideal para tensão acumulada'
  },
  {
    id: 2,
    categoria: 'Estresse',
    titulo: 'Um momento real de pausa',
    texto:
      'Eu precisava desacelerar. O ambiente tranquilo, o cuidado no atendimento e a massagem me ajudaram a relaxar de verdade.',
    nome: 'Ana P.',
    servico: 'Massagem Relaxante',
    detalhe: 'Ideal para rotina intensa'
  },
  {
    id: 3,
    categoria: 'Costas',
    titulo: 'Mais conforto nas costas',
    texto:
      'O atendimento foi focado nos pontos onde eu sentia mais desconforto. Saí da sessão com uma sensação melhor de mobilidade e bem-estar.',
    nome: 'Carlos R.',
    servico: 'Alívio de Tensão',
    detalhe: 'Ideal para desconfortos musculares'
  },
  {
    id: 4,
    categoria: 'Pernas',
    titulo: 'Sensação de pernas mais leves',
    texto:
      'Procurei o atendimento por sentir muito cansaço nas pernas. A sessão foi leve, cuidadosa e trouxe uma sensação muito boa de descanso.',
    nome: 'Fernanda L.',
    servico: 'Drenagem Linfática',
    detalhe: 'Ideal para sensação de peso'
  }
]

const depoimentoAtivo = ref(depoimentos[0])

function selecionarDepoimento(depoimento: typeof depoimentos[0]) {
  depoimentoAtivo.value = depoimento
}
</script>

<template>
  <section id="depoimentos" class="py-24 bg-white">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center mb-14">
        <span class="font-jetbrains inline-block mb-4 text-sm font-semibold text-green-700">
          Depoimentos
        </span>

        <h2 class="text-3xl md:text-5xl font-bold text-gray-900">
          Histórias de alívio e bem-estar
        </h2>

        <p class="mt-5 text-gray-600 max-w-2xl mx-auto text-lg">
          Veja como cada atendimento pode ser direcionado para uma necessidade diferente do corpo.
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch">
        <!-- Depoimento principal -->
        <div class="lg:col-span-7 bg-[#f8f4ee] rounded-3xl p-8 md:p-12 border border-gray-200 shadow-sm">
          <div class="flex flex-wrap items-center gap-3 mb-8">
            <span class="font-jetbrains text-xs font-semibold text-green-800 bg-green-100 px-3 py-2 rounded-full">
              {{ depoimentoAtivo.servico }}
            </span>

            <span class="font-jetbrains text-xs font-semibold text-gray-600 bg-white px-3 py-2 rounded-full border border-gray-200">
              {{ depoimentoAtivo.detalhe }}
            </span>
          </div>

          <div class="text-green-800 text-7xl leading-none mb-2">
            “
          </div>

          <h3 class="text-2xl md:text-4xl font-bold text-gray-900 leading-tight">
            {{ depoimentoAtivo.titulo }}
          </h3>

          <p class="mt-6 text-gray-700 text-lg md:text-xl leading-relaxed">
            {{ depoimentoAtivo.texto }}
          </p>

          <div class="mt-10 pt-6 border-t border-gray-200 flex items-center justify-between gap-4">
            <div>
              <p class="font-jetbrains text-sm font-bold text-gray-900">
                {{ depoimentoAtivo.nome }}
              </p>

              <p class="mt-1 text-sm text-gray-500">
                Cliente atendido
              </p>
            </div>

            <div class="hidden sm:flex items-center gap-1 text-green-800 text-xl">
              ★★★★★
            </div>
          </div>
        </div>

        <!-- Lista lateral -->
        <div class="lg:col-span-5 grid grid-cols-1 gap-4">
          <button
            v-for="depoimento in depoimentos"
            :key="depoimento.id"
            type="button"
            @click="selecionarDepoimento(depoimento)"
            class="text-left rounded-2xl p-6 border transition duration-300"
            :class="
              depoimentoAtivo.id === depoimento.id
                ? 'bg-gray-950 text-white border-gray-950 shadow-xl'
                : 'bg-white text-gray-900 border-gray-200 hover:border-green-800 hover:shadow-md'
            "
          >
            <div class="flex items-center justify-between gap-4">
              <span
                class="font-jetbrains text-sm font-bold"
                :class="depoimentoAtivo.id === depoimento.id ? 'text-green-300' : 'text-green-800'"
              >
                {{ depoimento.categoria }}
              </span>

              <span
                class="w-8 h-8 rounded-full flex items-center justify-center text-sm"
                :class="depoimentoAtivo.id === depoimento.id ? 'bg-white text-gray-950' : 'bg-[#f8f4ee] text-green-800'"
              >
                →
              </span>
            </div>

            <h4 class="mt-4 text-lg font-bold">
              {{ depoimento.titulo }}
            </h4>

            <p
              class="mt-2 text-sm leading-relaxed"
              :class="depoimentoAtivo.id === depoimento.id ? 'text-gray-300' : 'text-gray-600'"
            >
              {{ depoimento.detalhe }}
            </p>
          </button>
        </div>
      </div>

      <!-- CTA final -->
      <div class="mt-16 text-center">
        <p class="text-gray-600 text-lg">
          Quer entender qual atendimento combina com o seu momento?
        </p>

        <a
          href="https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20avaliação%20de%20massoterapia."
          target="_blank"
          class="font-jetbrains mt-6 inline-flex items-center justify-center bg-green-800 text-white px-8 py-4 rounded-lg font-semibold hover:bg-green-900 transition duration-300"
        >
          Agendar avaliação pelo WhatsApp
        </a>
      </div>
    </div>
  </section>
</template>
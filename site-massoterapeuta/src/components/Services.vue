<script setup lang="ts">
const whatsappLink =
  'https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20sessão%20de%20massoterapia.'

const avaliacaoLink =
  'https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20avaliação%20gratuita%20para%20saber%20qual%20massagem%20é%20ideal%20para%20mim.'

const servicos = [
  {
    imagem: '/images/servicos/Relaxamento%20e%20Estresse.jpg',
    etiqueta: 'Mais procurado',
    titulo: 'Relaxamento e Estresse',
    descricao:
      'Ideal para quem vive uma rotina intensa e precisa aliviar tensões físicas e mentais.',
    beneficios: [
      'Relaxamento profundo',
      'Alívio da tensão',
      'Sensação de leveza'
    ],
    tempo: '50 min'
  },
  {
    imagem: '/images/servicos/massage%20therapist%20hands%20leg.jpg',
    etiqueta: 'Dores e tensão',
    titulo: 'Massagem Terapêutica',
    descricao:
      'Atendimento focado em pontos de tensão, desconfortos musculares e rigidez corporal.',
    beneficios: [
      'Alívio muscular',
      'Mais mobilidade',
      'Redução da rigidez'
    ],
    tempo: '50 min'
  },
  {
    imagem: '/images/servicos/leg%20massage%20athlete.jpg',
    etiqueta: 'Para atletas',
    titulo: 'Massagem Esportiva',
    descricao:
      'Indicada para quem pratica atividade física e busca recuperação muscular e mais disposição.',
    beneficios: [
      'Recuperação muscular',
      'Menos rigidez',
      'Mais desempenho'
    ],
    tempo: '60 min'
  },
  {
    imagem: '/images/servicos/neck%20massage%20pain.jpg',
    etiqueta: 'Alívio muscular',
    titulo: 'Dores no Pescoço',
    descricao:
      'Técnica voltada para aliviar tensões na região do pescoço, ombros e costas.',
    beneficios: [
      'Alívio da tensão',
      'Relaxamento muscular',
      'Mais conforto no dia a dia'
    ],
    tempo: '50 min'
  }
]
</script>

<template>
  <section id="servicos" class="py-24 bg-[#f8f4ee]">
    <div class="container mx-auto px-4">
      <div class="text-center mb-14">
        <span class="inline-block mb-4 text-sm font-semibold text-green-700">
          Serviços
        </span>

        <h2 class="text-3xl md:text-5xl font-bold text-gray-900">
          Tratamentos pensados para o seu bem-estar
        </h2>

        <p class="mt-5 text-gray-600 max-w-2xl mx-auto text-lg">
          Cada sessão é personalizada de acordo com sua rotina, seu corpo e seu momento.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div
          v-for="servico in servicos"
          :key="servico.titulo"
          class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-200 hover:-translate-y-2 hover:shadow-xl transition duration-300 flex flex-col"
        >
          <div class="h-56 overflow-hidden">
            <img
              :src="servico.imagem"
              :alt="servico.titulo"
              class="w-full h-full object-cover hover:scale-105 transition duration-500"
            />
          </div>

          <div class="p-7 flex flex-col flex-1">
            <div class="mb-4">
              <span class="text-xs font-semibold text-green-700 bg-green-50 px-3 py-1 rounded-full">
                {{ servico.etiqueta }}
              </span>
            </div>

            <h3 class="text-xl font-bold text-gray-900 mb-3">
              {{ servico.titulo }}
            </h3>

            <p class="text-gray-600 mb-5 leading-relaxed">
              {{ servico.descricao }}
            </p>

            <ul class="space-y-2 mb-6">
              <li
                v-for="beneficio in servico.beneficios"
                :key="beneficio"
                class="text-sm text-gray-700 flex items-center gap-2"
              >
                <span class="text-green-700 font-bold">✓</span>
                {{ beneficio }}
              </li>
            </ul>

            <div class="mt-auto">
              <div class="flex items-center justify-between pt-5 border-t border-gray-100">
                <span class="text-sm text-gray-500">
                  Tempo médio: {{ servico.tempo }}
                </span>
              </div>

              <a
                :href="whatsappLink"
                target="_blank"
                class="mt-6 inline-flex w-full items-center justify-center bg-green-800 text-white px-5 py-3 rounded-lg font-semibold hover:bg-green-900 transition"
              >
                Agendar sessão
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-16 bg-white border border-gray-200 rounded-2xl px-6 py-12 md:px-12 text-center shadow-sm">
        <div class="max-w-3xl mx-auto">
          <h3 class="text-2xl md:text-3xl font-bold text-gray-900">
            Dúvidas sobre o melhor atendimento para você?
          </h3>

          <p class="mt-4 text-gray-600 text-base md:text-lg leading-relaxed">
            Fale comigo pelo WhatsApp. Faço uma avaliação rápida para indicar a massagem ideal para as suas necessidades.
          </p>

          <a
            :href="avaliacaoLink"
            target="_blank"
            class="mt-8 inline-flex items-center justify-center bg-green-800 text-white px-8 py-4 rounded-lg font-semibold hover:bg-green-900 transition duration-300"
          >
            Agendar Avaliação Gratuita
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
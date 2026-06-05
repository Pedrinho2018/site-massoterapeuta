<script setup lang="ts">
const diferenciais = [
  {
    titulo: 'Óleos e cremes premium',
    descricao: 'Produtos selecionados para oferecer mais conforto, cuidado e qualidade no contato com a pele.'
  },
  {
    titulo: 'Ambiente climatizado',
    descricao: 'Espaço preparado para proporcionar conforto térmico, tranquilidade e relaxamento durante a sessão.'
  },
  {
    titulo: 'Avaliação personalizada',
    descricao: 'Antes do atendimento, entendemos sua necessidade para indicar a técnica mais adequada.'
  },
  {
    titulo: 'Foco no seu alívio',
    descricao: 'Técnicas direcionadas para as regiões onde você sente mais tensão, dor ou desconforto.'
  },
  {
    titulo: 'Biossegurança total',
    descricao: 'Ambiente higienizado, maca preparada com cuidado e atenção aos detalhes de segurança.'
  },
  {
    titulo: 'Acesso fácil',
    descricao: 'Atendimento pensado para tornar sua experiência mais prática, confortável e tranquila.'
  }
]
</script>

<template>
  <section class="py-24 bg-[#f8f4ee]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-14 items-center">
        <div>
          <span class="font-jetbrains inline-block mb-4 text-sm font-semibold text-green-700">
            Por que escolher
          </span>

          <h2 class="text-3xl md:text-5xl font-bold text-gray-900 leading-tight">
            Cuidado, conforto e atenção em cada detalhe
          </h2>

          <p class="mt-6 text-gray-600 text-lg leading-relaxed">
            Cada sessão é planejada para oferecer uma experiência segura, acolhedora e personalizada para o seu momento.
          </p>

          <a
            href="https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20avaliação%20gratuita."
            target="_blank"
            class="font-jetbrains mt-8 inline-flex bg-green-800 text-white px-7 py-4 rounded-lg font-semibold hover:bg-green-900 transition"
          >
            Agendar avaliação
          </a>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div
            v-for="diferencial in diferenciais"
            :key="diferencial.titulo"
            class="bg-white rounded-2xl p-6 border border-gray-200 shadow-sm hover:-translate-y-1 hover:shadow-lg transition duration-300"
          >
            <div class="w-10 h-10 rounded-full bg-green-100 text-green-800 flex items-center justify-center font-bold mb-4">
              ✓
            </div>

            <h3 class="font-bold text-gray-900">
              {{ diferencial.titulo }}
            </h3>

            <p class="mt-3 text-sm text-gray-600 leading-relaxed">
              {{ diferencial.descricao }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
const passos = [
  {
    numero: '01',
    titulo: 'Você chama no WhatsApp',
    descricao: 'Entre em contato e conte rapidamente o que você está sentindo ou buscando.'
  },
  {
    numero: '02',
    titulo: 'Entendemos sua necessidade',
    descricao: 'Avaliamos sua rotina, tensão corporal, objetivo e preferência de atendimento.'
  },
  {
    numero: '03',
    titulo: 'Indicamos a sessão ideal',
    descricao: 'Você recebe uma orientação simples para escolher o atendimento mais adequado.'
  },
  {
    numero: '04',
    titulo: 'Agendamos seu horário',
    descricao: 'Combinamos o melhor dia e horário para você cuidar do seu bem-estar.'
  }
]
</script>

<template>
  <section class="py-24 bg-white">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center mb-14">
        <span class="font-jetbrains inline-block mb-4 text-sm font-semibold text-green-700">
          Como funciona
        </span>

        <h2 class="text-3xl md:text-5xl font-bold text-gray-900">
          Atendimento simples, acolhedor e personalizado
        </h2>

        <p class="mt-5 text-gray-600 max-w-2xl mx-auto text-lg">
          Do primeiro contato ao agendamento, tudo é pensado para deixar sua experiência leve e tranquila.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="passo in passos"
          :key="passo.numero"
          class="bg-[#f8f4ee] rounded-2xl p-7 border border-gray-200 hover:-translate-y-1 hover:shadow-lg transition duration-300"
        >
          <span class="font-jetbrains text-3xl font-bold text-green-800">
            {{ passo.numero }}
          </span>

          <h3 class="mt-5 text-xl font-bold text-gray-900">
            {{ passo.titulo }}
          </h3>

          <p class="mt-3 text-gray-600 leading-relaxed">
            {{ passo.descricao }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
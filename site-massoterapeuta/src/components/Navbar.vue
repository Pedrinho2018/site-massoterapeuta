<template>
  <header class="fixed top-0 left-0 w-full z-50 bg-black/20 backdrop-blur-sm">
    <div class="max-w-7xl mx-auto px-6 py-5 flex items-center justify-between">
      <a href="#inicio" class="font-jetbrains text-white text-lg font-bold tracking-wide">
        Essência Terapêutica
      </a>

      <nav class="hidden md:flex items-center gap-8 font-jetbrains text-sm font-semibold">
        <a href="#inicio" class="menu-link active">Home</a>
        <a href="#servicos" class="menu-link">Serviços</a>
        <a href="#sobre" class="menu-link">A Empresa</a>
        <a href="#contato" class="menu-link">Contato</a>
      </nav>

      <a
        href="https://wa.me/5566999121068?text=Olá,%20quero%20agendar%20uma%20sessão%20de%20massoterapia."
        target="_blank"
        class="hidden md:inline-flex font-jetbrains bg-green-800 text-white px-5 py-3 rounded-lg text-sm font-semibold hover:bg-green-900 transition"
      >
        Agendar
      </a>
    </div>
  </header>
</template>

<style scoped>
.menu-link {
  position: relative;
  color: rgba(255, 255, 255, 0.72);
  text-decoration: none;
  padding-bottom: 10px;
  transition: color 0.3s ease;
}

.menu-link:hover {
  color: white;
}

.menu-link::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 2px;
  background: white;
  transition: width 0.3s ease;
}

.menu-link:hover::after {
  width: 100%;
}

.menu-link.active {
  color: white;
}

.menu-link.active::after {
  width: 100%;
}
</style>
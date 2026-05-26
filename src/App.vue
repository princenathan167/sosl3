<script setup>
const programs = [
  {
    title: "Web Development",
    description:
      "Students learn HTML, CSS, JavaScript, and Vue.js to build responsive and modern websites.",
    icon: "💻",
  },
  {
    title: "Graphic Design",
    description:
      "Students create logos, edit images, and design digital content using professional tools.",
    icon: "🎨",
  },
  {
    title: "Networking",
    description:
      "Students gain networking and IT support skills for computer systems and network management.",
    icon: "🌐",
  },
]
</script>

<template>
  <div
    class="min-h-screen bg-gradient-to-br from-slate-950 via-slate-900 to-sky-950 text-white px-6 py-10"
  >
    <div
      class="max-w-7xl mx-auto bg-white/5 border border-white/10 rounded-[35px] overflow-hidden shadow-[0_0_60px_rgba(0,0,0,0.6)] backdrop-blur-xl"
    >
      <!-- HERO SECTION -->
      <div
        class="grid lg:grid-cols-2 gap-16 items-center px-8 md:px-16 py-16"
      >
        <!-- LEFT CONTENT -->
        <div>
          <p
            class="uppercase tracking-[6px] text-sky-400 text-sm font-semibold mb-5"
          >
            SOS Technical High School
          </p>

          <h1
            class="text-5xl md:text-7xl font-black leading-tight mb-6 text-white"
          >
            Modern Technology Education
          </h1>

          <p
            class="text-gray-300 text-lg leading-relaxed mb-8 max-w-2xl"
          >
            SOS Technical High School provides students with skills in website
            development, graphic design, and networking to prepare them for
            modern careers in technology and innovation.
          </p>

          <div class="flex flex-wrap gap-4">
            <button
              class="bg-sky-500 hover:bg-sky-400 text-white px-8 py-4 rounded-2xl font-semibold transition duration-300 shadow-lg hover:scale-105"
            >
              Learn More
            </button>

            <button
              class="border border-sky-400/40 bg-white/5 hover:bg-sky-500/10 text-sky-300 hover:text-white px-8 py-4 rounded-2xl font-semibold transition duration-300"
            >
              Explore Programs
            </button>
          </div>
        </div>

        <!-- LOGO SECTION -->
        <div class="flex justify-center">
          <div
            class="bg-white rounded-[30px] p-6 shadow-2xl border border-white/20 hover:scale-105 transition duration-300"
          >
            <img
              src="/images.jpeg"
              alt="SOS Children's Villages Logo"
              class="w-[420px] max-w-full object-contain rounded-2xl"
            />
          </div>
        </div>
      </div>

      <!-- PROGRAMS SECTION -->
      <div
        class="grid md:grid-cols-3 gap-8 px-8 md:px-16 pb-16"
      >
        <div
          v-for="program in programs"
          :key="program.title"
          class="bg-white/5 border border-white/10 rounded-3xl p-8 hover:bg-sky-500/10 hover:border-sky-400/30 transition duration-300 hover:-translate-y-2 shadow-lg"
        >
          <div
            class="w-16 h-16 rounded-2xl bg-sky-500/20 flex items-center justify-center text-3xl mb-6"
          >
            {{ program.icon }}
          </div>

          <h2 class="text-3xl font-bold text-white mb-4">
            {{ program.title }}
          </h2>

          <p class="text-gray-300 leading-relaxed text-lg">
            {{ program.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  font-family: "Inter", sans-serif;
}

body {
  margin: 0;
}
</style>
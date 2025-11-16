<template>

    <section id="experience" class="text-white mt-18"> <!-- Fondo decorativo -->
        <div class="absolute right-0 top-0 h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>

        <!-- Skills -->
        <div data-aos="flip-left" class="mt-16 flex flex-col items-center">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">

                <h1 class="text-4xl font-bold text-white mb-4 text-left md:text-center">
                    My
                    <span
                        class="text-transparent bg-clip-text bg-gradient-to-r from-green-300 to-secondary">Skills</span>
                </h1>

                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-6 gap-6 mt-8">

                    <div v-for="skill in Skills" :key="skill.id"
                        class="flex items-center justify-center p-4 rounded-2xl border border-white/10 bg-white/5 backdrop-blur-sm hover:bg-white/10 transition">
                        <img :src="skill.logo" :alt="skill.name" class="h-12 w-12 object-contain" />
                    </div>

                </div>

            </div>
        </div>


        <!-- Experiences -->
        <div data-aos="flip-left" class="mt-16 flex flex-col items-center">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%] mx-auto">
                <h1 class="text-4xl font-bold text-white mb-4 text-left md:text-center">
                    My
                    <span
                        class="text-transparent bg-clip-text bg-gradient-to-r from-white to-green-500">Experiences</span>
                </h1>
            </div>

            <div class="space-y-8 py-8 w-[80%] mx-auto">
                <div v-for="element in Experiences" :key="element.id"
                    class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]">
                    <div class="w-1/4 flex justify-center">
                        <img src="https://vulletic.com.ar/wp-content/uploads/2024/06/Vulletic_logo.png" alt="icon" />
                    </div>
                    <div class="w-3/4 pl-4">
                        <h3
                            class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                            {{ element.role }}
                        </h3>
                        <p class="text-white">{{ element.company }}</p>
                        <p class="text-gray-300">{{ element.date }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

</template>


<script setup>

//AGREGAR EXPERIENCIAS Y TEECH STACK
import { ref } from 'vue';
import { onMounted } from "vue";

onMounted(() => {
    const bars = document.querySelectorAll(".skill-bar")

    const observer = new IntersectionObserver(
        entries => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const el = entry.target
                    el.style.width = el.getAttribute("data-width")
                    el.style.transition = "width 1.5s ease-in-out"
                    observer.unobserve(el)
                }
            })
        },
        { threshold: 0.3 }
    )

    bars.forEach(bar => observer.observe(bar))
})
const Skills = ref([

    {
        id: 1,
        name: '.NET',
        logo: 'https://img.icons8.com/?size=100&id=1BC75jFEBED6&format=png&color=000000'

    },
    {
        id: 2,
        name: 'Aspire',
        logo: 'https://aspire.dev/_astro/aspire-logo-32.DGHSFRgf.svg'
    },
    {
        id: 3,
        name: 'Blazor',
        logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Blazor.png/960px-Blazor.png?20201024035312'
    },
    {
        id: 4,
        name: 'Linux system administration (Debian-based)',
        logo: 'https://img.icons8.com/?size=100&id=fG5Tnj4ARIoI&format=png&color=000000'
    },
    {
        id: 5,
        name: 'MongoDB',
        logo: 'https://img.icons8.com/?size=100&id=8rKdRqZFLurS&format=png&color=000000'
    },
    {
        id: 6,
        name: 'PostgreSQL',
        logo: 'https://img.icons8.com/?size=100&id=Pv4IGT0TSpt8&format=png&color=000000'
    },
    {
        id: 7,
        name: 'Docker',
        logo: 'https://img.icons8.com/?size=100&id=cdYUlRaag9G9&format=png&color=000000'
    },
    {
        id: 8,
        name: 'DigitalOcean',
        logo:'https://img.icons8.com/?size=100&id=PJVoaac1LEJy&format=png&color=000000'
    },
    {
        id:9,
        name:'Cloudflare',
        logo:'https://img.icons8.com/?size=100&id=fUGx53gD9Jof&format=png&color=000000'
    },
    {
        id:10,
        name: 'Azure',
        logo: 'https://img.icons8.com/?size=100&id=VLKafOkk3sBX&format=png&color=000000'
    },
    {
        id:11,
        name:'Nginx',
        logo:'https://img.icons8.com/?size=100&id=LhQ8M0RI4YLP&format=png&color=000000'
    },
    {
        id:12,
        name:'Vue',
        logo:'https://img.icons8.com/?size=100&id=rY6agKizO9eb&format=png&color=000000'
    }
])
const Experiences = ref([
    {
        id: 1,
        role: 'Backend developer',
        company: 'Vulletic EV Chargers',
        date: 'October 2022 - At present'
    }
])

</script>
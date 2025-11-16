<template>
  <section id="projects" class="text-white mt-20">
    <div class="text-center mb-12">
      <h2 class="text-4xl font-bold text-white">
        My
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-500 to-yellow-500">
          Projects
        </span>
      </h2>
    </div>

    <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
      data-aos="fade-right">
      <li v-for="project in Projects" :key="project.id" class="rounded-xl overflow-hidden shadow-lg">
        <!-- Imagen -->
        <div class="h-52 md:h-[24rem] rounded-t-xl relative group" :style="{
          backgroundImage: `url(${project.image})`,
          backgroundSize: 'cover',
          backgroundPosition: 'center'
        }">
          <!-- Overlay -->
          <div
            class="overlay absolute inset-0 bg-[#1a1919] bg-opacity-0 hidden group-hover:flex group-hover:bg-opacity-80 items-center justify-center transition-all duration-500">
            <div class="p-4">

              <p class="text-[#ffffff] text-sm leading-relaxed">
                {{ project.message }}
              </p>
            </div>

          </div>
        </div>

        <!-- Info -->
        <div class="bg-[#111a3e] p-4 border border-[#1f1641] rounded-b-xl">
          <h3 class="text-xl font-semibold text-white">{{ project.title }}</h3>
          <p class="text-gray-400 text-sm mt-2">{{ project.description }}</p>

          <div class="flex flex-wrap gap-2 mt-3">
            <span v-for="tech in project.technologies" :key="tech"
              class="px-2 py-1 text-xs rounded-md bg-[#1f2a48] text-gray-300">
              {{ tech }}
            </span>
          </div>
        </div>
      </li>
    </ul>
  </section>
</template>


<script setup>
import { ref } from "vue";

const Projects = ref([
  {
    id: 1,
    category: "web development",
    message: 'The realization of this project helped me learn to understand real-time communication and message delivery. At first, I developed this project using SignalR and RabbitMQ to store messages in a queue, but it turned out to be inefficient by its bad implementation, so I took the initiative to move the core technologies to Firebase Cloud Messaging. Thanks to that, we were able to guarantee the delivery of notifications to both types of users, web users and mobile users.',
    image: "/notifications-service.png",
    title: "Notifications service",
    description: "Notifications service for mobile user and web users using FCM.",
    technologies: [".NET 8", "Firebase Cloud Messaging", "MongoDB"]
  },
  {
    id: 2,
    category: "web development",
    image: "/estacion-2.png",
    message: 'This was my first project, and thanks to it I learned how a RESTful API work, from development and database integration to managing JSON data, testing, and deploying the application to servers. This experience also taught me the importance of teamwork and delivering effective solutions for end clients.',
    title: "Weve business backend",
    description: "This service allows you to create electric charging stations and connect chargers to them.",
    technologies: [".NET 6", "MongoDB", "Azure Blob Storage", "Azure DevOps"]
  },
  {
    id: 3,
    category: "web development",
    image: "/weve-admin.png",
    message:'This platform provides Weve’s owner with an organized and structured way to visualize data from all users, charging stations, and various related objects. Weve admin has features such as banning users, deleting charging stations, and sending global notifications.',
    title: "Weve admin backend",
    description: "Platform that controls and monitors Weve business users.",
    technologies: [".NET 6", "MongoDB"]
  },
  {
    id: 4,
    category: "web development",
    image: "/firmware-charger.png",
    message:'The development of this project solved the lack of control over firmware versions. Thanks to Azure Blob Storage, it became possible to store different versions, request a specific one, and retrieve a sorted list of all available versions. This was essential for maintaining proper traceability and ensuring an organized and reliable version management system.',
    title: "Firmware version management backend",
    description: "Backend to store, retrieve, delete, and manage electric charger firmware versions.",
    technologies: [".NET 8", "Azure Blob Storage"]
  },
  {
    id: 5,
    category: "devops",
    image: "/grafana2.png",
    message:'Thanks to this solution, we are able to monitor server resources. It allows us to control and pay attention to any server changes. I also integrated Slack notifications in case of crashes or overloads. This stack was built using Docker Compose, which allowed us to combine Grafana for data visualization, Node Exporter to collect data, and Prometheus for monitoring and alerting.',
    title: "Server monitoring service",
    description: "Server monitoring built with Grafana, Node Exporter, and Prometheus.",
    technologies: ["Docker", "Grafana", "Node exporter", "Prometheus", "Ubuntu"]
  }
]);
</script>

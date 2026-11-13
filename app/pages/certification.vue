<template>
  <div>
    <!-- Page Header -->
    <div class="cert-div">
      <div class="certifications">
        <h1 class="cert-heading">CERTIFICATIONS</h1>
      </div>
    </div>

    <!-- Certifications Grid -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8 lg:gap-10 px-4 sm:px-8 lg:px-16 py-10 place-items-center items-start">
      <div 
        v-for="(cert, index) in certifications" 
        :key="index" 
        class="cert-item flex flex-col items-center justify-between h-full w-full max-w-[420px]"
      >
        <div class="group relative w-full aspect-[4/3] rounded-[20px] bg-[#2b2b2b] flex justify-center items-center p-5 shadow-[0_8px_20px_#00000066] transition duration-300 ease-in-out hover:scale-105 hover:shadow-[0_15px_30px_#00000088] hover:z-20">
          <img 
            :src="cert.image" 
            :alt="cert.label" 
            class="w-full h-full object-contain cursor-pointer" 
            @click="openModal(cert.image)" 
          />
        </div>

        <div class="flex flex-col items-center justify-between flex-grow w-full mt-4">
          <p class="cert-label text-center min-h-[3rem] flex items-center justify-center">
            {{ cert.label }}
          </p>
          <a :href="cert.verifyUrl" target="_blank" rel="noreferrer" class="inline-block mt-4">
            <button class="bg-[#1e96fc] text-white px-4 py-2 rounded-lg transition duration-300 shadow-md hover:bg-[#187ad1]">
              Verify Certification
            </button>
          </a>
        </div>
      </div>
    </div>

    <br />

    <!-- Image Modal Popup -->
    <Transition name="fade">
      <div 
        v-if="selectedImage" 
        class="fixed inset-0 bg-black/80 flex items-center justify-center z-50 p-4 cursor-pointer" 
        @click="closeModal"
      >
        <img :src="selectedImage" class="max-w-[90%] max-h-[90%] rounded-lg shadow-2xl" alt="Enlarged Certification" />
      </div>
    </Transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'

useHead({
  title: 'Certifications | Kirby Villegas'
})

const certifications = ref([
  {
    label: 'Word Associate Certification',
    image: '/images/Word Certidication-1.png',
    verifyUrl: 'https://www.certiport.com/portal/pages/credentialverification.aspx'
  },
  {
    label: 'Powerpoint Associate Certification',
    image: '/images/PPT Certificate-1.png',
    verifyUrl: 'https://www.certiport.com/portal/pages/credentialverification.aspx'
  },
  {
    label: 'Networking Basics Certification',
    image: '/images/Networking cert.png',
    verifyUrl: 'https://www.credly.com/badges/475ba18b-9325-49f1-a882-c865d6fcf812'
  }
])

const selectedImage = ref(null)

const openModal = (imageSrc) => {
  selectedImage.value = imageSrc
}

const closeModal = () => {
  selectedImage.value = null
}

const url = useRequestURL()

const title = 'Certifications | Kirby Villegas'
const description = 'Explore the certifications of Kirby Villegas, an aspiring web developer. Verify your credentials and learn more about his professional achievements.'

useHead({
  title,
  link: [{ rel: 'canonical', href: url.href }],
})

useSeoMeta({
  description,
  ogTitle: title,
  ogDescription: description,
  ogType: 'website',
  ogUrl: url.href,
  ogImage: `${url.origin}/images/Word Certidication-1.png`, 
  ogImageAlt: 'Word Associate Certification image',
})

</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
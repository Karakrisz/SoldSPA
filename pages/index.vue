<script setup>
import { ref, onMounted } from 'vue'

const headerVideo = ref(null)

onMounted(() => {
  handleVideoPlayback()
})

const handleVideoPlayback = () => {
  const video = headerVideo.value
  if (video) {
    video.muted = true
    video
      .play()
      .then(() => {
        console.log('Video is playing')
      })
      .catch((error) => {
        console.log('Video play failed:', error)
      })
  }
}
</script>
<template>
  <section>
    <div class="hero-content">
      <NuxtImg
        src="/img/slide.webp"
        alt="Soldah Kft"
        class="hero-content__img"
        :srcset="['/img/slide.webp 1920w', '/img/slide.webp 100w']"
      />
    </div>
  </section>
  <AboutSection />
  <ServicesSection />
  <section>
    <div class="video-content">
      <video
        class="video-content__video"
        autoplay
        loop
        muted
        playsinline
        width="1920"
        height="100%"
        preload="metadata"
        ref="headerVideo"
      >
        <source src="/video/bontas.mp4" type="video/mp4" />
        Sajnáljuk, a böngésződ nem támogatja a videó elemet.
      </video>
    </div>
  </section>
  <WorksSection />
  <BlogSection />
</template>

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
  <WorksSection />
  <BlogSection />
</template>

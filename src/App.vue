<script setup>
import SiteHeader from './components/SiteHeader.vue'
import HomeHero from './components/HomeHero.vue'
import MenuSection from './components/MenuSection.vue'
import StorySection from './components/StorySection.vue'
import VisitSection from './components/VisitSection.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <SiteHeader />
  <main>
    <HomeHero />
    <section class="intro-band">
      <p>“好好吃饭，是日子里最踏实的浪漫。”</p>
      <small>每日现做 · 当季食材 · 一席家常</small>
    </section>
    <MenuSection />
    <StorySection />
    <VisitSection />
  </main>
  <SiteFooter />
</template>

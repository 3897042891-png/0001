<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <header class="topbar">
    <a class="brand" href="#home" aria-label="巷里小馆首页" @click="closeMenu">
      <span class="brand-mark">巷</span>
      <span>
        <span class="brand-name">巷里小馆</span>
        <span class="brand-sub">XIANG LI · JIANGNAN KITCHEN</span>
      </span>
    </a>
    <button
      class="menu-toggle"
      type="button"
      :aria-label="menuOpen ? '关闭导航' : '打开导航'"
      :aria-expanded="menuOpen"
      aria-controls="primary-navigation"
      @click="menuOpen = !menuOpen"
    >
      {{ menuOpen ? '×' : '☰' }}
    </button>
    <nav id="primary-navigation" class="nav" :class="{ open: menuOpen }" aria-label="主导航">
      <a href="#menu" @click="closeMenu">当季菜单</a>
      <a href="#story" @click="closeMenu">关于小馆</a>
      <a href="#visit" @click="closeMenu">来店里坐坐</a>
      <a class="nav-cta" href="#reserve" @click="closeMenu">预约座位&nbsp; ↗</a>
    </nav>
  </header>
</template>

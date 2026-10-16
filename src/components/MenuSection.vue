<script setup>
const dishes = [
  {
    name: '春笋腌笃鲜',
    description: '慢炖三小时 · 春日限定',
    price: '¥ 68',
    image: 'https://images.unsplash.com/photo-1603208614668-b35c95647eaf?auto=format&fit=crop&w=900&q=82',
    alt: '清爽的时令蔬菜小菜',
  },
  {
    name: '桂花糖醋小排',
    description: '手熬桂花糖 · 酸甜刚好',
    price: '¥ 58',
    image: 'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?auto=format&fit=crop&w=900&q=82',
    alt: '刚出锅的招牌家常菜',
  },
  {
    name: '时蔬清炒双菇',
    description: '每日鲜采 · 清鲜爽口',
    price: '¥ 42',
    image: 'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=900&q=82',
    alt: '新鲜采摘的当季食材',
  },
]
</script>

<template>
  <section class="section" id="menu">
    <div class="section-heading">
      <div>
        <div class="eyebrow">SEASONAL FAVORITES</div>
        <h2>今日好味道</h2>
      </div>
      <p>跟着时令吃，认真对待每一口。<br />菜单随季节与每日采买微调。</p>
    </div>
    <div class="dishes">
      <article v-for="dish in dishes" :key="dish.name" class="dish-card">
        <div class="dish-image">
          <img :src="dish.image" :alt="dish.alt" loading="lazy" />
        </div>
        <div class="dish-info">
          <div>
            <h3>{{ dish.name }}</h3>
            <p>{{ dish.description }}</p>
          </div>
          <span class="price">{{ dish.price }}</span>
        </div>
      </article>
    </div>
  </section>
</template>

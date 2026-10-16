<script setup>
import { computed, reactive, ref } from 'vue'

function formatLocalDate(date) {
  const year = date.getFullYear()
  const month = String(date.getMonth() + 1).padStart(2, '0')
  const day = String(date.getDate()).padStart(2, '0')
  return `${year}-${month}-${day}`
}

const today = computed(() => formatLocalDate(new Date()))
const form = reactive({ name: '', phone: '', date: '', time: '', guests: '2 位用餐' })
const formMessage = ref('')

function submitReservation() {
  formMessage.value = `${form.name}，收到您的预约请求，我们会拨打 ${form.phone} 与您确认。`
  form.name = ''
  form.phone = ''
  form.date = ''
  form.time = ''
  form.guests = '2 位用餐'
}
</script>

<template>
  <section class="section visit" id="visit">
    <div>
      <div class="eyebrow">COME FIND US</div>
      <h2>留一张桌，等你来</h2>
      <div class="visit-details">
        <div>
          <div class="detail-label">ADDRESS</div>
          <div class="detail-value">杭州市上城区南山路 68 号<br />巷子往里走 80 米</div>
        </div>
        <div>
          <div class="detail-label">OPENING HOURS</div>
          <div class="detail-value">午市 11:00 – 14:00<br />晚市 17:00 – 21:30</div>
        </div>
        <div>
          <div class="detail-label">CALL US</div>
          <div class="detail-value"><a href="tel:057188862688">0571 · 8886 2688</a></div>
        </div>
        <div>
          <div class="detail-label">FOLLOW</div>
          <div class="detail-value">小红书 / 微信：巷里小馆</div>
        </div>
      </div>
    </div>
    <div class="reserve-box" id="reserve">
      <h3>预约一顿好饭</h3>
      <p>留下信息，我们会尽快与您确认。</p>
      <form class="reserve-form" @submit.prevent="submitReservation">
        <input v-model="form.name" name="name" placeholder="怎么称呼您" aria-label="怎么称呼您" required />
        <input v-model="form.phone" name="phone" type="tel" placeholder="联系电话" aria-label="联系电话" required />
        <input v-model="form.date" name="date" type="date" :min="today" aria-label="预约日期" required />
        <select v-model="form.time" name="time" aria-label="预约时段" required>
          <option disabled value="">选择时段</option>
          <option>午市 12:00</option>
          <option>午市 13:00</option>
          <option>晚市 18:00</option>
          <option>晚市 19:00</option>
          <option>晚市 20:00</option>
        </select>
        <select v-model="form.guests" class="wide" name="guests" aria-label="用餐人数">
          <option>2 位用餐</option>
          <option>1 位用餐</option>
          <option>3 位用餐</option>
          <option>4 位用餐</option>
          <option>5 位及以上</option>
        </select>
        <button class="button button-primary wide" type="submit">提交预约请求&nbsp; ↗</button>
        <p class="form-message" role="status" aria-live="polite">{{ formMessage }}</p>
      </form>
    </div>
  </section>
</template>

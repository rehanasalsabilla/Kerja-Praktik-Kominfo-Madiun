<template>
  <div
    class="visitor-card flex flex-col items-center text-white rounded-full p-5 mx-auto relative mb-10"
  >
    <div class="flex items-center justify-between space-x-4">
      <!-- Tombol View -->
      <div class="flex flex-col items-start space-y-2 w-1/4">
        <button
          @click="changeView('harian')"
          :class="{ 'text-white border-l-4 border-white': currentView === 'harian' }"
          class="text-sm font-semibold text-gray-300 py-2 px-4 hover:text-white focus:outline-none"
        >
          Harian
        </button>
        <button
          @click="changeView('bulanan')"
          :class="{ 'text-white border-l-4 border-white': currentView === 'bulanan' }"
          class="text-sm font-semibold text-gray-300 py-2 px-4 hover:text-white focus:outline-none"
        >
          Bulanan
        </button>
        <button
          @click="changeView('tahunan')"
          :class="{ 'text-white border-l-4 border-white': currentView === 'tahunan' }"
          class="text-sm font-semibold text-gray-300 py-2 px-4 hover:text-white focus:outline-none"
        >
          Tahunan
        </button>
      </div>

      <!-- Judul dan Data -->
      <div class="text-center flex-1" ref="countContainer">
        <h2 class="text-xl font-bold">Jumlah Pengunjung</h2>
        <p
          v-if="currentView === 'harian' && isVisible"
          class="text-4xl font-bold text-yellow-400 mt-4"
        >
          <count-up :end-val="todayVisitorCount" :duration="2.5"></count-up>
        </p>
        <p
          v-if="currentView === 'bulanan' && isVisible"
          class="text-4xl font-bold text-yellow-400 mt-4"
        >
          <count-up :end-val="monthlyVisitorCount" :duration="2.5"></count-up>
        </p>
        <p
          v-if="currentView === 'tahunan' && isVisible"
          class="text-4xl font-bold text-yellow-400 mt-4"
        >
          <count-up :end-val="yearlyVisitorCount" :duration="2.5"></count-up>
        </p>
      </div>

      <!-- Gambar People -->
      <img src="/img/people.png" alt="Illustration" class="w-32 h-32" />
    </div>
  </div>
</template>

<script>
import CountUp from 'vue-countup-v3'; // Import the CountUp component

export default {
  components: {
    CountUp,
  },
  props: {
    todayVisitorCount: {
      type: Number,
      required: true,
    },
    monthlyVisitorCount: {
      type: Number,
      required: true,
    },
    yearlyVisitorCount: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      currentView: "harian",
      isVisible: false,
    };
  },
  mounted() {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            this.isVisible = true;
            observer.unobserve(entry.target);
          }
        });
      },
      { threshold: 0.5 }
    );

    observer.observe(this.$refs.countContainer);
  },
  methods: {
    changeView(view) {
      this.currentView = view;
    },
  },
};
</script>

<style scoped>
.visitor-card {
  height: 165px;
  background-color: #064e3b;
  background-image: url('/img/Visitor.png'); /* gunakan path public */
  background-size: cover;
  background-position: center;
  width: 70%;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>

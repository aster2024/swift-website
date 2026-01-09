<script>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination, Autoplay } from 'swiper/modules'
import 'swiper/css/bundle'

export default {
  components: {
    Swiper,
    SwiperSlide,
    Navigation,
    Pagination,
    Autoplay,
  },
  data() {
    return {
      modules: [Navigation, Pagination, Autoplay],
      figures: [
        {
          src: './figures/overall_illustration.png',
          caption: 'Overall illustration: SWIFT vs. text-based reward models',
        },
        {
          src: './figures/efficiency.png',
          caption: 'Efficiency comparison (parameters / compute)',
        },
        {
          src: './figures/main_results.png',
          caption: 'Main results figure/table (from the paper)',
        },
      ],
    }
  },
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Figures</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="22" :md="18" :lg="14" :xl="12">
        <swiper
          :loop="true"
          :slidesPerView="1"
          :modules="modules"
          :navigation="{ hideOnClick: true }"
          :pagination="{ hideOnClick: true, clickable: true, type: 'bullets' }"
          :autoplay="{ delay: 6000, disableOnInteraction: false, pauseOnMouseEnter: true }"
        >
          <swiper-slide v-for="fig in figures" :key="fig.src">
            <el-card class="card">
              <el-image :src="fig.src" fit="contain" class="figure" />
              <div class="caption">{{ fig.caption }}</div>
              <div class="hint">
                如果这里显示空白/裂图，把截图文件放到 <code>public/figures/</code> 并命名为
                <code>overall_illustration.png</code>/<code>efficiency.png</code>/<code>main_results.png</code>
              </div>
            </el-card>
          </swiper-slide>
        </swiper>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.card {
  margin-top: 20px;
}

.figure {
  width: 100%;
}

.caption {
  text-align: center;
  margin-top: 12px;
  color: var(--el-text-color-primary);
}

.hint {
  text-align: center;
  margin-top: 8px;
  color: var(--el-text-color-secondary);
  font-size: 14px;
}
</style>

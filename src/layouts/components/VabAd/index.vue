<template>
  <div class="vab-ad">
    <el-carousel
      v-if="adList"
      height="30px"
      direction="vertical"
      :autoplay="true"
      :interval="3000"
      indicator-position="none"
    >
      <el-carousel-item v-for="(item, index) in adList" :key="index">
        <el-tag type="warning">Ad</el-tag>
        <a target="_blank" :href="item.url">{{ item.title }}</a>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script>
  // import { getList } from '@/api/ad'
  export default {
    name: 'VabAd',
    data() {
      return {
        nodeEnv: process.env.NODE_ENV,
        adList: [
          {
            title: 'Artemis 2.0.8版本发布，点我体验',
            url: 'https://cloud.mate.vip',
          },
          {
            title: 'MateCloud 2.0.8版本发布，点我体验',
            url: 'https://cloud.mate.vip',
          },
        ],
      }
    },
    // created() {
    //   this.fetchData()
    // },
    methods: {
      // async fetchData() {
      //   const { data } = await getList()
      //   this.adList = data
      // },
    },
  }
</script>
<style lang="scss" scoped>
  .vab-ad {
    height: 30px;
    padding-right: $base-padding;
    padding-left: $base-padding;
    margin-bottom: -20px;
    line-height: 30px;
    cursor: pointer;

    a {
      color: #999;
    }
  }
</style>

<template>
  <div class="body">
    <button @click="showCalendarDialog">显示</button>
    <vue-hash-calendar
      ref="picker"
      model="inline"
      :visible.sync="isShowCalendar"
      picker-type="date"
      @click="confirm"
      :isShowAction="false"
      @slidechange="slidechange"
    >
      <div slot="day" slot-scope="scope">
        <div v-if="scope.extendAttr.isToday">今</div>
        <div v-else>{{ scope.date.day }}</div>
      </div>
    </vue-hash-calendar>
    <div></div>
  </div>
</template>

<script>

export default {
  name: 'demo',
  data () {
    return {
      isShowCalendar: true, // 是否显示弹窗
      isShowTips: false, // 是否显示下载提示
      defaultDatetime: new Date(),
      direction: 'down'
    }
  },
  mounted () {},
  methods: {
    showCalendarDialog () {
      // 显示日历
      this.isShowCalendar = true
    },
    confirm (item) {
      console.log('item', item)
    },
    slidechange (item) {
      console.log('slidechange', item)
      this.direction = item
    }
  }
}
</script>

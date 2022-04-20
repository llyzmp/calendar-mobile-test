<template>
  <div class="home">
    <van-checkbox-group v-model="result" @change="changeGroup">
      <van-checkbox :name="item" v-for="item in data" :key="item">复选框 {{item}}</van-checkbox>
    </van-checkbox-group>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      result: ['a', 'b', 'c', 'd', 'e'],
      data: ['a', 'b', 'c', 'd', 'e'],
      last: []
    }
  },
  methods: {
    changeGroup (data) {
      console.log('data', data)
      if (data.length === 1) {
        this.last = data
      }
      // this.result = ['a', 'b']
      if (data.length === 0) {
        this.result = this.last
      }
    }
  }
}
</script>

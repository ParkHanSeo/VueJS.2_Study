<template>
  <div>
    <h1>Welcome to {{ title }}~!</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getData">Get</button>
    <button type="button" @click="setData">Set</button>

    <select class="form-control" v-model="region" @change="changeRegion">
      <option :key="i" :value="d.v" v-for="(d, i) in options">{{ d.t }}</option>
    </select>
    <table class="table table-vordered" v-if="tableShow">
      <tr :key="i" v-for="(d, i) in options">
        <td>{{ d.v }}</td>
        <td>{{ d.t }}</td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      title: '박지훈',
      title2: 'test',
      input1: 'abc',
      options: [
        { v: 'S', t: 'Seoul' },
        { v: 'J', t: 'Jeju' },
        { v: 'B', t: 'Busan' }
      ],
      region: 'J',
      tableShow: true
    }
  },
  watch: {
    input1() {
      console.log(this.input1)
    }
  },
  beforeCreate() {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    console.log('mounted')
  },
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated() {
    console.log('updated')
  },
  beforeDestroy() {
    console.log('beforeDestroy')
  },
  destroyed() {
    console.log('destroyed')
  },
  methods: {
    getData() {
      alert(this.input1)
    },
    setData() {
      this.input1 = '1234'
    },
    changeRegion() {
      alert(this.region)
    }
  }
}
</script>

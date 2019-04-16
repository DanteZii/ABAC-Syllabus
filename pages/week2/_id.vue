<template>
    <div>
         <h1>{{ item.age }}</h1>
    </div>
</template>
<script>
export default {
  validate ({ params }) {
    // 必须是number类型
    return /^\d+$/.test(params.id)
  },


  async asyncData({ $axios, params }) {
    const item = await $axios.$get(`https://cuneoclass.firebaseio.com/students.json/${params.id}`)
    return{ item }
  }
}
</script>

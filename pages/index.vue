<template>
  <section class="con">
    <h1>Lunedi</h1>
    <div
    v-for="item in items"
    :key="item.id"
    class="wrapper"
    >
    <div class="alink">
      <ul class="wriper">
                <li class="name">
                  <div class="ch">{{item.tname}}</div>
                  <div>{{item.name}}</div>   
                  <div class="ifmt">{{item.information}}</div>              
                </li>
                <div class="timew">
                  <div class="timew2">
                  <div class="stime">{{item.stime}}</div>
                  <h6 class="line">---</h6>
                  <div class="stime">{{item.etime}}</div></div>
                  <div class="classroom">
                    <span class="classroomc">{{ item.classroom }}</span>
                  </div>
              </div>
      </ul>
      
    </div> 
    </div>
  </section>
</template>

<script>

export default {
  async asyncData({ $axios }) {
    const items = await $axios.$get('https://cuneoclass.firebaseio.com/abacw1.json')
    return{ items }
  },
  computed: {
    // 计算属性的 getter
    items: function () {
      // `this` 指向 vm 实例
      return this.item.split('').reverse().join('')
    }
  }


}
</script>

<style>
</style>
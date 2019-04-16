<template>
  <section class="con">
    <h1>Martedì</h1>
    <div
    v-for="item in items"
    :key="item.id"
    class="wrapper"
    >
    <div class="alink">
      <ul class="wriper">
                <li class="name">{{item.name}}</li>
                <div class="timew">
                  <div class="timew2">
                  <div>{{item.stime}}</div>
                  <h6 class="stime">---</h6>
                  <div>{{item.etime}}</div></div>
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
    const items = await $axios.$get('https://cuneoclass.firebaseio.com/week2.json')
    return{ items }
  }
}
</script>

<style>
</style>

<template>
  <section class="con">
    <h1>Sabato</h1>
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
    const items = await $axios.$get('https://cuneoclass.firebaseio.com/abacw6.json')
    return{ items }
  }
}
</script>

<style>
</style>
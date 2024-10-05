<script setup>

</script>

<template>
  <div class="area">

    <input class="input" type="text" v-model="son" placeholder="a"><br>
    <input class="input" type="text" v-model="daraja" placeholder="b"><br>
    <input class="input" type="text" v-model="boluvchi" placeholder="boluvchi"><br>
    <button class="input" @click="qoldiq">click</button><br>
    <span class="input">qoldiq: {{ this.qoldi }}</span><br>
  </div>
</template>
<script>
export default {
  data() {
    return {
      qoldi: 0,
      bolinma: 0,
      son: 0,
      daraja: 0,
      boluvchi: 0,
      // son: 0,
      // daraja: 0,
      // boluvchi: 0
    }
  },
  methods: {
    qoldiq(){
      this.umu = Math.pow(this.son, this.daraja)
      this.qoldi = this.umu % this.boluvchi
    }
  },
}
</script>

<style scoped>
.area{
  width: 100%;
  height: 100vh;
  padding: 30px 30px;
}
.input{
  width: 100%;
  height: 50px;
  font-size: 30px;
}
</style>





<!-- <template>
  <div class="flex flex-col justify-between items-center w-[100%] h-[500px] pt-[30px]">
    <input type="text" class="w-[80%] h-[50px] text-[30px] border-[2px]" v-model="hour">
    <input type="text" class="w-[80%] h-[50px] text-[30px] border-[2px]" v-model="minute">
    <button class="w-[80%] text-[white] rounded-[15px] h-[50px] bg-[red]" @click="calculate()">Score</button>
    <br>
    <span class="text-[50px]">{{ score }}°</span>
  </div>
</template>

<script>
export default {
    name: '',

    data() {
        return {
          score: 0,
          hour: '',
          minute: '',
          minute_degree: 0,
          hour_degree: 0,
        };
    },

    mounted() {
      
    },

    methods: {
        calculate(){
            if(parseInt(this.hour) !== 12){
                this.minute_degree = parseInt(this.minute) / 5 * 30
                this.hour_degree = parseInt(this.hour) * 30 + (parseInt(this.minute) * 1/2)
                if(this.minute_degree > this.hour_degree){
                    this.score = this.minute_degree - this.hour_degree
                }else{
                    this.score = this.hour_degree - this.minute_degree
                }
            }
            else{
                this.minute_degree = parseInt(this.minute) / 5 * 30
                this.hour_degree = parseInt(this.minute) * 1/2
                if(this.minute_degree > this.hour_degree){
                    this.score = this.minute_degree - this.hour_degree
                }else{
                    this.score = this.hour_degree - this.minute_degree
                }
            }
        }
    },
};
</script> -->

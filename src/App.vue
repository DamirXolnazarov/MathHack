<template>
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
</script>

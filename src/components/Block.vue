<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    click me
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            clickTime: 0
        }
    },
    mounted() {
        console.log('component mounted')
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.clickTime += 10
            },10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.clickTime)
            this.$emit('stop', this.clickTime) 
        }
    }
}
</script>

<style>
.block  {
    width: 400px;
    border-radius: 20px;
    background: #64e9ee;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>
<template>
  <div class="icon">
      <img @click="change" v-if="id" src="@/assets/arrow-down.png">
      <img @click="change1" v-else :class="changeup" src="@/assets/arrow-red.png">
  </div>
</template>

<script>
export default {
    data(){
        return{
            id:true,
            changeup:'down'
        }
    },
    methods:{
        change(){
            if(this.id == true){
                this.id = false
            }else{
                this.id = true
            }
        },
        change1(){
            if(this.changeup == 'down'){
                this.changeup = ''
            }else{
                this.changeup = 'down'
            }

        }
    }

}
</script>

<style lang="scss">
.icon{
    .down{
         transform: rotate(180deg);
    }
}

</style>
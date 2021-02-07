<template>
<div class='v-main'>
    <h1 @click="lip">{{a}}</h1>

    <div  @click="setNumber(item)" v-for="item in arr" :key="item">{{item}}</div>
    <div>{{doneCount}}</div>
  </div>
</template>

<script>
    import {mapActions, mapGetters} from "vuex";

  export default {
    name: "v-main",
    props: {},
    data() {
      return {
          a: 111,
          arr: [567, 516,526,67,687]
      }
    },
    computed: {
        ...mapGetters({
            doneCount: 'ITEM'
        })
    },
      methods:{
          ...mapActions({
              cart: 'CART'
          }),
          setNumber: function (item) {
              this.$emit('set', item)
          },
          search() {
             return this.ITEM
          },
          lip(){
              console.log(this.$parent.$options)
          }

      }
  }
</script>

<style scoped>

</style>

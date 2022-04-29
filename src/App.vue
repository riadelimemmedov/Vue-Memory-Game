<template>
  <transition-group name="slideContainer" mode="out-in">
    <component
      key="mainComponent"
      @activeComponentEvent="activeComponent=$event"
      :is="activeComponent"><!-- eger dynamic sekilde componentleri istifade etmek isteyirnsense compoentn tagi ve :is den istifade etmelinse birde data propertysine deyisken adi vermelinseki :is ile binding ede bilek componentdi ekrana yeni template tagi icine dynamic bir sekilde -->
    </component>
    <canvas id="canvas" key="canvasComponent" v-show="activeComponent =='app-celebrate'"></canvas>
  </transition-group>
</template>

<script>
  import GameCards from './components/GameCards.vue'
  import Failure from './components/Failure.vue'
  import Celebrate from './components/Celebrate.vue'

  export default{
    data:function(){
      return{
        activeComponent:'app-game-cards',
      }
    },
    components:{
      'app-game-cards':GameCards,
      'app-failure':Failure,
      'app-celebrate':Celebrate,
    }
  }

</script>

<style>

  body{/* butun componentlerein css inde olacag bu kod cunki scopped dan istifade olunmadi */
    font-family: sans-serif;
  }

  .slideContainer-enter{}
  .slideContainer-enter-active{
    animation: slide-in .3s ease-in-out forwards;
  }
  .slideContainer-leave{}
  .slideContainer-leave-active{
    animation: slide-out .3s ease-in-out forwards;
  }

  @keyframes slide-in{
    from{
      transform: translateX(-1000px);
      opacity: 0;
    }
    to{
      transform: translateX(0px);
      opacity: 1;
    }
  }

  @keyframes slide-out{
    from{
      transform: translateX(0px);
      opacity: 1;
    }
    to{
      transform: translateX(1000px);
      opacity: 0;
    }
  }

</style>

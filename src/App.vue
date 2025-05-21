


<script>
import Card from './components/Card.vue';
import Card2 from './components/Card2.vue';
import VueProjectList from './components/VueProjects.js'
import desktopProjectList from './components/DesktopProjects.js'
// import { VueProjectList } from './components/VueProjects';

export default{
  name:'App',
  data(){
    return{
      VueProjectList,
      desktopProjectList
    }
  },
  components:{
    Card,
    Card2
  },
  
}
</script>

<template>



<div  style="max-width: 1300px;background-color: black;padding-bottom: 20px;gap:60px;" class="w-full  mx-auto flex flex-col  items-center justify-center" >

<div style="gap: 30px;" class="w-full flex flex-col items-center  mt-60">

  <p style="font-size: 48px;">Web Apps</p>

  <div class="w-full flex flex-wrap items-center justify-center gap-60">
<Card v-for="ele in VueProjectList" :key="ele?.project_name"  :cardDetails="ele" />
  </div>

</div>


 
<div style="gap: 30px;" class="w-full flex flex-col items-center  mt-60">

  <p style="font-size: 48px;">Desktop Apps</p>

  <div class="w-full flex flex-wrap items-center justify-center gap-60">
<Card2  v-for="ele in desktopProjectList" :key="ele?.project_name"  :cardDetails="ele" />
  </div> 

</div> 

</div>  

</template>
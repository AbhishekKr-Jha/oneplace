

<script>   
export default{
    name:'Card2',  
     props:{
        cardDetails:Object
    },
    methods:{
         downloadFile(fileurl) {
      const url = fileurl 
      const a = document.createElement('a');
      a.href = url;
      a.download = ''; 
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);
    }
    }
}
</script>


<template>

 <div  class="card relative">
        <div style="height: 180px; padding: 6px;" class="w-full ">
            <img :src="cardDetails?.image_link" class="w-full h-full object-fit-contain rounded-lg"  alt="load...">
            <!-- <img src="../assets/li.jpeg" class="w-full h-full object-fit-contain rounded-lg"  alt="load..."> -->
        </div>
        <div style="padding: 10px;padding-top: 0;gap: 0px;" class="w-full flex flex-col  ">

            <p  :style="{ fontSize: '44px', color: cardDetails?.textColor || 'rgb(1, 84, 154)' }" class="text-red font-medium  text-primary">{{cardDetails?.project_name}}  </p>
            <p style="font-size: 20px;margin-top: 5px;" class="text-center w-full  "> - {{cardDetails?.project_type}}  - </p>
 
<div style="margin-top: 20px;" class="flex flex-col gap-10 ">
    <p class="text-lg">{{ cardDetails.description.line1 ? `• ${cardDetails.description.line1}` : ' • • • ' }}</p>
    <p class="text-lg">{{ cardDetails.description.line2 ? `• ${cardDetails.description.line2}` : ' • • • ' }}</p>
    <p class="text-lg " :class="{'text-center':!cardDetails.description.line3}"> {{ cardDetails.description.line3 ? `• ${cardDetails.description.line3}` : ' • • • ' }}</p>
</div>



            <div style="gap: 30px;" class="w-full absolute bottom-15 left-0 flex justify-center items-center  "> 
                <a :href="cardDetails?.github_link" target="_blank" class=" block"><i style="font-size: 30px;" class="fa-brands fa-github "></i></a>
                <div @click="downloadFile(cardDetails?.application_link)" style="padding: 7px 11px;" class="bg-red rounded-full block pointer"><i style="font-size: 20px;"  class="fa-solid fa-arrow-down text-2xl"></i></div>
            </div>

        </div> 

    </div>

</template>
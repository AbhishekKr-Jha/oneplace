

<script>

export default{
    name:'card',
    props:{
        cardDetails:Object
    }
}
</script>





<template>
    <div class="card relative">
        <div style="height: 150px; padding: 6px;" class="w-full ">
            <img :src="cardDetails?.image_link" class="w-full h-full object-fit-contain rounded-lg"  alt="load...">
        </div>
        <div style="padding: 10px;padding-top: 0;gap: 0px;" class="w-full flex flex-col  ">

            <p style="font-size: 44px;" class="text-red font-medium  text-primary">{{cardDetails?.project_name}}  </p>
            <p style="font-size: 20px;margin-top: 5px;" class="text-center w-full  "> - {{cardDetails?.project_type}}  - </p>
 
<div style="margin-top: 20px;" class="flex flex-col gap-10 ">
    <p class="text-lg">{{ cardDetails.description.line1 ? `• ${cardDetails.description.line1}` : ' • • • ' }}</p>
    <p class="text-lg">{{ cardDetails.description.line2 ? `• ${cardDetails.description.line2}` : ' • • • ' }}</p>
    <p class="text-lg text-center "> {{ cardDetails.description.line3 ? `• ${cardDetails.description.line3}` : ' • • • ' }}</p>
</div>



            <div style="gap: 30px;" class="w-full absolute bottom-15 left-0 flex justify-center items-center  "> 
                <a :href="cardDetails?.github_link" target="_blank" class=" block"><i style="font-size: 30px;" class="fa-brands fa-github "></i></a>
                <a :href="cardDetails?.hosting_link" target="_blank" class=" block"><i style="font-size: 30px;"  class="fa-solid fa-eye text-2xl"></i></a>
            </div>

        </div> 

    </div>
</template>
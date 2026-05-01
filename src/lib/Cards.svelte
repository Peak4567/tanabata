<script>
   import { onMount } from "svelte";
   import { goto } from '$app/navigation';
   let images = [
      { src: "/img/4.svg", alt: "Card" },
      { src: "/img/6.svg", alt: "Card" },
      { src: "/img/7.svg", alt: "Card" },
      { src: "/img/9.svg", alt: "Card" },
   ];
   let cardArray = $state([]);
   function cardClick(index) {
      let item = cardArray[index]
      console.log(item)
      if(item.status === false){
         goto('/edit/' + (index+1))
      }else{
         goto('/view/'+ (index+1))
      }
      localStorage.setItem("blessingData",JSON.stringify(cardArray))
    
   }
   onMount(() => {
      cardArray = JSON.parse(localStorage.getItem("blessingData")) || [
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false },
         { name: "", blessing: "", status: false }
      ];
   });
</script>

<div class="container mx-auto">
   <div class="w-full">
      <div class="relative">
         <div class="card-1">
            <button
               onclick={() => {cardClick(0)}}
               class="absolute top-[400px] left-[20rem] lg:left-[54rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  1
               </div>
               <img src={images[0].src} alt="" class="" />
            </button>
            <button onclick={() => {cardClick(1)}}
               class="absolute top-[300px] left-[100px] lg:left-[50rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  2
               </div>
               <img src={images[1].src} alt="" class="" />
            </button>
            <button onclick={() => {cardClick(2)}}
               class="absolute top-[500px] left-90 lg:left-[50rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  3
               </div>
               <img src={images[2].src} alt="" class="" />
            </button>
            <button onclick={() => {cardClick(3)}}
               class="absolute top-[400px] left-90 lg:left-[40rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  4
               </div>
               <img src={images[3].src} alt="" class="" />
            </button>
         </div>
         <div class="card-2">
            <button onclick={() => {cardClick(4)}}
               class="absolute top-[500px] left-[30rem] lg:left-[40rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  5
               </div>
               <img src={images[0].src} alt="" class="" />
            </button>
            <button onclick={() => {cardClick(5)}}
               class="absolute top-[400px] left-[40rem] lg:left-[60rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  6
               </div>
               <img src={images[1].src} alt="" class="" />
            </button>
            <button onclick={() => {cardClick(6)}}
               class="absolute bottom-[500px] left-[30rem] lg:left-[34rem] w-10 hover:scale-110"
            >
               <div
                  class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute"
               >
                  7
               </div>
               <img src={images[1].src} alt="" class="" />
            </button>
         </div>
         <div class="flex justify-center">
               <img src="/img/tree.webp" alt="" class="w-200 mb-50">
         </div>
      </div>
   </div>
</div>

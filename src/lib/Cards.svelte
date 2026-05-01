<script>
    let images = [
        { src: "/img/4.svg", alt: "Card" },
        { src: "/img/6.svg", alt: "Card" },
        { src: "/img/7.svg", alt: "Card" },
        { src: "/img/9.svg", alt: "Card" },
    ];
</script>

<div class="container mx-auto">
    <div class="w-full">
        <div class="relative ">
       <div class="card-1">
         <button class="absolute top-[15rem] left-[10rem] lg:left-[50rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">1</div>
            <img src={images[0].src} alt="" class="" />
         </button>
         <button class="absolute top-[5rem] left-[100px] lg:left-[50rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">2</div>
            <img src={images[1].src} alt="" class="" />
         </button>
         <button class="absolute top-[300px] left-90 lg:left-[50rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">3</div>
            <img src={images[2].src} alt="" class="" />
         </button>
         <button class="absolute top-[100px] left-90  lg:left-[40rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">4</div>
            <img src={images[3].src} alt="" class="" />
         </button>
       </div>
       <div class="card-2">
        <button class="absolute top-[15rem] left-[30rem] lg:left-[40rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">5</div>
            <img src={images[0].src} alt="" class="" />
         </button>
        <button class="absolute top-[20px] left-[40rem] lg:left-[60rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">6</div>
            <img src={images[1].src} alt="" class="" />
         </button>
        <button class="absolute top-[40px] left-[30rem] lg:left-[30rem] w-10 hover:scale-110">
            <div class="bg-red-500 rounded-full w-5 h-5 flex item-center justify-center text-white absolute">7</div>
            <img src={images[1].src} alt="" class="" />
         </button>
       </div>
    </div>
    </div>
</div>

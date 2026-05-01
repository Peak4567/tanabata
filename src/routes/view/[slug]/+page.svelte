<script>
    import { onMount } from "svelte";
    import { page } from '$app/state';
    let cardArray = $state([]);

    onMount(() => {
        cardArray = JSON.parse(localStorage.getItem("blessingData"))
    })

    const slug = page.params.slug;


</script>
<div class=" w-screen h-[850px] m-0 p-0 flex">
    <div class=" w-1/3 h-auto flex justify-center items-center">
        <div class=" w-3/5 h-2/3 flex flex-col justify-center p-0 rounded-4xl overflow-hidden bg-white">
            <div class=" w-auto h-1/6 flex justify-center items-center p-0">
                <p class=" text-2xl cursor-default">
                    ใบอธิษฐานของคุณ
                </p>
            </div>
            <div class=" w-auto h-2/3 flex flex-col justify-center items-center p-0">
                <div class=" w-2/3 h-full bg-contain bg-no-repeat bg-center bg-[url('/img/card.webp')] flex flex-col items-center pt-30">
                    <p class=" text-2xl">
                        
                    </p>
                </div>
            </div>
            <div class=" w-auto h-1/6 flex justify-center items-center p-0 ">
                <a href="/" class=" w-2/3 h-1/3 flex">
                    <button class=" w-full h-full flex justify-center items-center gap-2 rounded-4xl bg-pink-400 text-white transition delay-50 duration-200 ease-in
                    hover:bg-pink-600 cursor-pointer">
                        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-x-icon lucide-circle-x"><circle cx="12" cy="12" r="10"/><path d="m15 9-6 6"/><path d="m9 9 6 6"/></svg>
                        ปิดคำอธิฐาน
                    </button>
                </a>
            </div>
        </div>
    </div>
    <div class=" w-2/3 h-auto">

    </div>
</div>
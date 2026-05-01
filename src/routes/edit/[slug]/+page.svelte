<script>
    import { goto } from '$app/navigation';
    import {onMount} from "svelte";
    import { page } from '$app/state';

    let cardArray = $state([]);
    onMount(() => {
        cardArray = JSON.parse(localStorage.getItem("blessingData"));
    })

    let name = $state("");
    let blessing = $state("");
    const slug = page.params.slug;


    function addCard() {

        cardArray[slug - 1].name = name;
        cardArray[slug -1].blessing = blessing;

        if(name != "" || blessing != ""){
            cardArray[slug -1].status = true;
        }

        localStorage.setItem("blessingData", JSON.stringify(cardArray));

        goto('/');
    }

</script>

<div class="flex justify-center mt-7">
    <div>
        <img src="/img/Tanzuka.webp" alt="Tanzuka" class="w-100 h-180">
        <div class="w-100 h-160 absolute top-47 ">
            <h1 class="text-center mt-30 text-[28px] mb-3">เขียนคำอธิษฐาน</h1>

            <label for="name" class="ml-10 text-[20px]">ชื่อของคุณ</label>
            <br>
            <input type="text" id="name" placeholder="กรอกชื่อของคุณ" bind:value={name}  class="border border-gray-500 rounded-md ml-10 text-[15px] w-80 h-8 pl-3 mb-3" required>
            <br>
            <label for="blessing"class="ml-10 text-[20px]">คำอวยพร</label>
            <br>
            <textarea name="blessing" id="blessing" placeholder="เขียนคำอวยพรของคุณที่นี่..." bind:value={blessing}  class="border border-gray-500 rounded-md ml-10 text-[15px] w-80 h-50 pl-3 pt-2 pr-3" required></textarea>
            <br>

            <button class="ml-27 pl-8 pr-8 pt-3 pb-3 cursor-pointer rounded-xl mt-5 bg-pink-400 text-white hover:bg-pink-500 text-[20px]" 
            onclick={addCard}>Make a wish!</button>
        </div>
    </div>
</div>
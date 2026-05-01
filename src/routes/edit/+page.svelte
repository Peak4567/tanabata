<script>
    import { redirect } from "@sveltejs/kit";
    import { goto } from '$app/navigation';
    import {onMount} from "svelte";

    let cardArray = $state([]);
    onMount(() => {
        cardArray = JSON.parse(localStorage.getItem("blessingData")) || [];
    })

    let name = $state("");
    let blessing = $state("");

    

    let cardObj = {
        name: "",
        blessing: "",
        status: true
    }

    function addCard() {

        cardObj["name"] = name;
        cardObj["blessing"] = blessing;

        cardArray.push(cardObj);

        localStorage.setItem("blessingData", JSON.stringify(cardArray));

        goto('/');
    }

</script>

<div class="flex justify-center mt-10">
    <div class="w-70 h-110 border">
        <h1 class="text-center mt-10 text-[20px] mb-7">เขียนคำอธิษฐาน</h1>

        <label for="name" class="ml-5 text-[15px]">ชื่อของคุณ</label>
        <br>
        <input type="text" id="name" placeholder="กรอกชื่อของคุณ" bind:value={name} class="border rounded-md ml-5 text-[10px] w-60 h-6 pl-3 mb-3">
        <br>
        <label for="blessing"class="ml-5 text-[15px]">คำอวยพร</label>
        <br>
        <textarea name="blessing" id="blessing" placeholder="เขียนคำอวยพรของคุณที่นี่..." bind:value={blessing} class="border rounded-md ml-5 text-[10px] w-60 h-30 pl-3 pt-2 pr-3"></textarea>
        <br>

        <button class="ml-19 border-2 pl-5 pr-5 cursor-pointer rounded-xl mt-5" 
        onclick={addCard}>อวยพรเลย!</button>
    </div>
</div>
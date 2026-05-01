<script>
    // (แก้ไขบรรทัดด้านล่าง) #1 ให้น้องๆ เปลี่ยนตัวแปร todo ให้ update ค่าอัตโนมัติ ด้วย $state() ที่สำหรับเก็บค่าที่รับ input เข้ามาจาก <input /> (ประเภท string)
    let todo = ""; 
    // (แก้ไขบรรทัดด้านล่าง) #3 ให้น้องๆ เปลี่ยนตัวแปร todos ให้ update ค่าอัตโนมัติ ด้วย $state() สำหรับเก็บค่า todolist ทั้งหมด (ประเภท array)
    let todos = [];

    function addTodo() {
        // #5 ให้น้องๆ เติม Code ในฟังก์ชัน addTodo() สำหรับเพิ่มค่าเข้าไปใน array ที่ชื่อ todos
        // - สร้าง todoObj โดยใส่ค่าที่ได้จากกล่องข้อความ <input /> =  { task: _____, status: false } 
        // - เพิ่ม todoObj เข้า todos
    }
    function delTodo(index) {
        // #9 ให้น้องๆ เติม Code ในฟังก์ชัน delTodo(index) สำหรับลบค่าใน array ที่ชื่อ todos
    }
</script>

<div class="container">
    <div class="head-container">
        <h1>Todolist</h1>
        <hr />

        <div class="input-container">
            ¸

            <!-- (แก้ไขบรรทัดด้านล่าง) #2 ให้น้องๆเชื่อม input เข้ากับตัวแปร todo -->
            <input type="text" id="input-todo" />

            <!-- (แก้ไขบรรทัดด้านล่าง) #4 ให้น้องๆเติม event เมื่อกดปุ่มให้เรียกฟังก์ชัน addTodo-->
            <button id="add-button" _______={addTodo}> Add </button>


        </div>

        <div id="todos">
            {#each todos as todo, index}
                <div class="todo">

                    <!-- #6 ให้น้องๆ สร้าง checkbox และ ผูกค่าสถานะของcheckbox เข้ากับ todo.status -->
                    <!-- พิมโค้ด #6 ที่บรรทัดนี้ -->
                    
                    <!-- #7 ให้น้องๆแสดงข้อความ จากการวนลูป todos ด้วยตัวแปร todo -->
                    <!-- พิมโค้ด #7 ที่บรรทัดนี้ -->
                    
                    <!-- #8 ให้น้องๆ สร้าง button สำหรับลบ todo และ เติม event เมื่อกดปุ่มให้เรียกฟังก์ชัน delTodo(index) -->
                    <!-- พิมโค้ด #8 ที่บรรทัดนี้ -->
                    
                </div>
            {/each}
        </div>
    </div>
</div>

<style>
    h1 {
        text-align: center;
    }
    #input-todo {
        width: 200px;
        height: 20px;
    }
    #add-button {
        padding: 5px;
        width: 60px;
        background-color: green;
        color: white;
    }
    .head-container {
        width: 500px;
        border: 2px solid black;
        padding: 20px 50px 50px 50px;
    }
    .input-section {
        width: 500px;
    }
    .input-container {
        display: flex;
        justify-content: center;
        gap: 10px;
    }
    .container {
        display: flex;
        justify-content: center;
    }
    #todos {
        display: flex;
        justify-content: center;
        flex-direction: column;
        margin-left: 5px;
    }
    .todo {
        margin-top: 25px;
        padding: 0px 50px 0px 50px;
        width: 400px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        font-size: 20px;
        gap: 10px;
        border: 2px solid black;
    }

    input,
    p,
    button {
        margin-left: 5px;
    }
</style>

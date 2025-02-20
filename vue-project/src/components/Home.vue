<script setup>
import { ref } from 'vue';

import Popup from './Popup.vue';

const isShow = ref(false)

const handleShow = (value) => {
  isShow.value = value
}
</script>

<template>
    <div class="container">
        <div><img src="../assets/images/task.png" alt="logo">
            <div class="header-container">
                <div style="display: flex;">
                    <h6>Let's get this done!</h6>
                    <img src="../assets/images/hand.png" alt="hand">
                </div><button class="new-task" @click="handleShow(true)">+ New task</button>
            </div>
        </div>
        <div class="task-board">
            <div class="column">
                <div class="general todo">
                    <h2 class="title">Todo</h2>
                    <span class="task-count">1</span>
                </div>
                <div class="task-card">
                    <div class="sub-title">
                        <p class="category">Marketing</p>
                        <div class="task-actions"><i class="fa-solid fa-pen"></i><i class="fa-solid fa-trash"></i></div>
                    </div>
                    <h3>Write SEO article for new product</h3>
                    <p class="description">This is an existential moment for effective altruism and the rationalist community writ-large. </p>
                    <div style="display: flex; gap: 10px;"><i class="fa-regular fa-clock"></i>
                        <p class="date">June 30,
                            2022</p>
                    </div>
                </div>
            </div>
            <div class="column">
                <div class="general doing">
                    <h2 class="title">Doing</h2>
                    <span class="task-count">1</span>
                </div>
                <div class="task-card">
                    <div class="sub-title">
                        <p class="category">Marketing</p>
                        <div class="task-actions"><i class="fa-solid fa-pen edit"></i><i class="fa-solid fa-trash delete"></i></div>
                    </div>
                    <h3>Write SEO article for new product</h3>
                    <p class="description">This is an existential moment for effective altruism and the rationalist community writ-large. </p>
                    <div style="display: flex; gap: 10px;"><i class="fa-regular fa-clock"></i>
                        <p class="date">June 30,
                            2022</p>
                    </div>
                </div>
            </div>
            <div class="column">
                <div class="general finished">
                    <h2 class="title">Finished</h2>
                    <span class="task-count">1</span>
                </div>
                <div class="task-card">
                    <div class="sub-title">
                        <p class="category">Marketing</p>
                        <div class="task-actions"><i class="fa-solid fa-pen"></i><i class="fa-solid fa-trash"></i></div>
                    </div>
                    <h3>Write SEO article for new product</h3>
                    <p class="description">This is an existential moment for effective altruism and the rationalist community writ-large. </p>
                    <div style="display: flex; gap: 10px;"><i class="fa-regular fa-clock"></i>
                        <p class="date">June 30,
                            2022</p>
                    </div>
                </div>
            </div>
        </div>
        
    <Popup v-if="isShow" :handleShow="handleShow"/>
    </div>
</template>
<style scoped>
    .container {
        position: absolute;
        font-family: Arial, sans-serif;
        padding: 10px;
        max-width: 1400px;
        margin: auto;
    }

    .header-container {
        display: flex;
        justify-content: space-between;
    }

    .new-task {
        background-color: #fff;
        color: rgb(87, 86, 86);
        padding: 10px 15px;
        border: none;
        cursor: pointer;
        border-radius: 5px;
        height: 40px;
        font-size: 18px;
    }

    .task-board {
        display: flex;
        gap: 40px;
    }

    .column {
        border-radius: 5px;
    }

    .general {
        display: flex;
        justify-content: space-between;
        align-items: center; 
        padding: 0 10px; 
        height: 50px;
    }

    .todo {
        background: #03a9f4;
        border-radius: 5px;
    }

    .doing {
        background: #f4c20d;
        border-radius: 5px;
    }

    .finished {
        background: #4caf50;
        border-radius: 5px;
    }

    .task-card {
        background: white;
        padding: 15px;
        border-radius: 5px;
        margin-top: 10px;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }

    .sub-title {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .task-actions {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        cursor: pointer;
    }

    .title {
        display: flex;
        align-items: center;
        padding: 5px 10px;
        color: white;
    }

    .task-count {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-right: 10px;
        border-radius: 5px;
        padding: 5px 10px;
        font-size: 18px;
        height: 20px;

    }

    .todo .task-count {
        background: #25b7fa;
        color: #fff;
    } 

    .doing .task-count {
        background: #f9ce36;
        color: #fff;
    } 

    .finished .task-count {
        background: #67e56b;
        color: #fff;
    } 

    .description {
        color: #575c60;
    }

    .fa-clock {
        display: flex;
        align-items: center;
        justify-content: center;
    }

</style>
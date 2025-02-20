<template>
    <div class="popup">
        <div class="overlay"></div>
        <div class="container"> 
            <i class="fa-solid fa-xmark" @click="props.handleShow(false)"></i>
            <h2 class="title center">Edit todo</h2>
            
            <input type="text" class="part" placeholder="category" v-model="todoDetails.category">
            <input type="text" class="part" placeholder="title" v-model="todoDetails.title">
            <textarea  class="part" placeholder="description" v-model="todoDetails.description"></textarea>

            <div class="sub-part"> 
                <div class="">
                    <input type="radio" id="todo" name="status" v-model="todoDetails.status" value="0">
                    <label for="todo">Todo</label>
                </div>

                <div>
                    <input type="radio" id="doing" name="status" v-model="todoDetails.status" value="1">
                    <label for="doing">Doing</label>
                </div>

                <div>
                    <input type="radio" id="finished" name="status" v-model="todoDetails.status" value="2">
                    <label for="finished">Finished</label>
                </div>
            </div>        

            <button class="part btn" @click="submit">Submit</button>
        </div>
    </div>
</template>

<script setup>
    import { reactive } from 'vue';
    import { ref } from 'vue';
    import Home from './Home.vue';

    const props = defineProps({
        handleShow: Function
    });

    const todoDetails = reactive({
        id: "",
        category: '',
        title: '',
        description: '',
        status: 0,
        date: ''
    });

    const submit = () => {
        if(todoDetails.category === '' || todoDetails.title === '' || todoDetails.description === '') {
            alert('Please fill all the fields');
            return;
        }

        console.log(todoDetails);
    }


    const handleNewTask = () => {
        
    }


</script>

<style scoped>
    /* * {
        box-sizing: border-box;
        max-width: 800px;
    } */

    .popup {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.5);
    }

    .container {
        background-color: #fff;
        position: absolute;
        width: 600px;
        height: 400px;
        display: flex;
        flex-direction: column;
        margin: 0 auto;
        padding: 15px;
        border-radius: 10px;
        border: 1px solid black;
    }

    .fa-xmark {
        display: flex;
        justify-content: flex-end;
        font-size: 20px;
        cursor: pointer;
    }

    .title { 
        color: gray;
        font-size: 30px;
        font-weight: 700;
    }
    .part {
        font-size: 18px;
        padding: 5px 5px;
        border-radius: 5px;
        border: 1px solid black;
        margin-bottom: 10px;
    }

    .sub-part {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        margin: 10px 100px 0;
        font-size: 20px;
    }

    .center {
        text-align: center;
    }

    .btn {
        background-color: #fff;
        margin-top: 10px;
        cursor: pointer;
    }
</style>
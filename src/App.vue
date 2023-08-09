<script setup>

import {ref,reactive} from 'vue'

let username = ref('')
let name = ref('')
const password = ref('')
const oldPassword = ref('')
const confarmPassword = ref('')
let show = ref(false)
let successIcon = ref(false)

function registarBtn(){
    let gmailName = username.value
    if(gmailName.indexOf('@') == -1){
        alert('please input your vaild gmail account')
    }

   else if(password.value.length<3){
        alert('password length more then 2')
    }
    else{
         show.value = true
    }  
}

function logInBtn(){
    if(oldPassword.value !== confarmPassword.value){
        alert('password is worng')
    }
    else if(oldPassword.value == ''){
        alert('please field the password')
    }
    else{
        alert('successfuly login')
        successIcon.value = true
    }
}

</script>

<template>
    <section class="w-full bg-cyan-200 h-screen">
        <div class=" ">
            <div class="w-1/2 m-auto py-10 ">
                <div class="py-20 bg-cyan-950">
                    <h1 :class="show == true ?'hidden':'block'" class="w-28 border-b m-auto text-center text-white text-2xl font-semibold">login</h1>
                    <h1 v-show="show" :class="successIcon == true?'hidden':'block'" class="w-52 border-b m-auto text-center text-white text-2xl font-semibold">second step</h1>
                    <div :class="successIcon == true?'flex':'hidden'" class="justify-center">
                        <svg height="60px" width="60px" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" 
                                viewBox="0 0 512 512" xml:space="preserve">
                            <path style="fill:#D7EBFF;" d="M256,512C114.837,512,0,397.157,0,256S114.837,0,256,0s256,114.843,256,256S397.163,512,256,512z"/>
                            <path style="fill:#C4E2FF;" d="M512,256C512,114.843,397.163,0,256,0v512C397.163,512,512,397.157,512,256z"/>
                            <path style="fill:#88CC2A;" d="M256,478.609c-122.75,0-222.609-99.864-222.609-222.609S133.25,33.391,256,33.391
                                S478.609,133.256,478.609,256S378.75,478.609,256,478.609z"/>
                            <path style="fill:#7FB335;" d="M478.609,256c0-122.744-99.859-222.609-222.609-222.609v445.217
                                C378.75,478.609,478.609,378.744,478.609,256z"/>
                            <path style="fill:#FFFFFF;" d="M233.739,356.174c-8.544,0-17.087-3.261-23.609-9.783l-68.804-68.804
                                c-13.044-13.038-13.044-34.179,0-47.218c13.044-13.044,34.174-13.044,47.218,0l45.195,45.19l95.282-95.278
                                c13.044-13.044,34.174-13.044,47.218,0c13.044,13.038,13.044,34.179,0,47.218L257.348,346.391
                                C250.827,352.913,242.283,356.174,233.739,356.174z"/>
                            <path style="fill:#EDF0F2;" d="M329.021,180.283L256,253.3v94.192c0.435-0.393,0.928-0.681,1.348-1.101l118.891-118.891
                                c13.044-13.038,13.044-34.179,0-47.218C363.196,167.239,342.065,167.239,329.021,180.283z"/>
                        </svg>
                    </div>
                </div>
                <div :class="show == true ?'hidden':'block'" class="bg-white py-10 text-center">
                    <div class="pb-5">
                        <input v-model="username" type="text" placeholder="username" class="outline-none border-cyan-950 border-b pl-1">
                    </div>
                    <div class="pb-5">
                        <input v-model="password" type="password" placeholder="password" class="outline-none border-cyan-950 border-b pl-1">
                    </div>
                    <div class="bg-white py-3 w-full flex justify-end pr-2">
                        <button @click="registarBtn()" class="bg-cyan-800 py-1 px-2 rounded-md text-white">registration</button>
                    </div>
                </div>

                <div :class="show == true ?'block':'hidden'" class="bg-white text-center">
                    <div :class="successIcon == true?'hidden':'block'">
                        <div class="py-5">
                            <input v-model="name" type="text" placeholder="name" class="outline-none border-cyan-950 border-b pl-1">
                        </div>
                        <div class="pb-5">
                            <input v-model="oldPassword" type="password" placeholder="password" class="outline-none border-cyan-950 border-b pl-1">
                        </div>
                        <div class="pb-5">
                            <input v-model="confarmPassword" type="password" placeholder="confarm password" class="outline-none border-cyan-950 border-b pl-1">
                        </div>
                        <div class="bg-white py-3 w-full flex justify-end pr-2">
                            <button @click=logInBtn() class="bg-cyan-800 py-1 px-2 rounded-md text-white">logIn</button>
                        </div>
                    </div>
                    
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>

</style>

<template>
    <div class="page">
        <h2>Home Page</h2>
        <el-button type="primary" @click="testAxios()">调用axios</el-button>
        <el-button type="primary" @click="getUser()">查询用户</el-button>
        <el-button type="primary" @click="getMenu()">查询菜单</el-button>
    </div>
</template>

<script>
import axios from 'axios';
import mock from '@/mock/mock.js';
export default {
    name:'Home',
    methods:{
        testAxios(){
            axios.get('http://localhost:8080').then(res=> {alert(res.data)});
        },
        getUser(){
            axios.get('http://localhost:8080/user').then(res => {alert(JSON.stringify(res.data))});
        },
        getMenu(){
            axios.get('http://localhost:8080/menu').then(res => {alert(JSON.stringify(res.data))});
        }
    }
}
</script>
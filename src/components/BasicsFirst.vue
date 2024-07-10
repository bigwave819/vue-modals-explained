<template>
    <div>
      <div v-if="showModal">
        <ul>
          <li v-for="book in books" v-bind:key="book" class="list">
            <img :src="book.img" :alt="book.title">
            <h3>{{ book.title }}</h3>
            <p>{{ book.author }}</p>
          </li> 
        </ul>
      </div>
      <button @click="ToggleModal">
        <span v-if="showModal == false">Show Books</span>
        <span v-if="showModal == true">Hide Books</span>
      </button>
    </div>
    </template>
    
    <script>
    export default {
      data() {
        return{
          showModal: true,
          books: [
            {title: 'Walking into the shadow', author:"sean paul", img: require('@/assets/1.jpg')},
            {title: 'Walking into the shadow', author:"sean paul", img: require('@/assets/1.jpg')},
            {title: 'Walking into the shadow', author:"sean paul", img: require('@/assets/1.jpg')},
          ]
        }
      },
      methods:{
        ToggleModal () {
            this.showModal = !this.showModal
        }
      }
    }
    </script>
    
    <style>
    #app {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
    }
    p, h3, ul{
      margin: 0;
      padding: 0;
    }
    li{
      list-style-type: none;
      background: #fff;
      margin: 20px auto;
      padding: 10px 20px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    img{
      height: 100px;
      width: 100px;
    }
    li:hover{
      box-shadow: 0 3px 5px 3px rgba(0, 0, 0, 0.4);
      padding: 10px;
    }
    button{
      padding: 20px;
      width: 100%;
      margin: 20px auto;
      height: 60px;
      border: none;
      border-radius: 20px;
      font-size: 20px;
      color:#fff;
      background: pink;
    }
    </style>
    
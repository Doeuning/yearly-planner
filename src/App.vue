<template>
  <div id="app">
    <year-header @addTodo="openModal"></year-header>
    <div class="year-wrap">
      <div class="month-wrap" v-for="(month, index) in months" :key="index">
        <one-month :propmonth="month"></one-month>
      </div>
    </div>
    <input-modal @close="closeModal" @addNewTodo="addNewTodo" v-if="modal" :propmonth="months" />
  </div>
</template>

<script>
import oneMonth from './components/oneMonth'
import yearHeader from './components/yearHeader'
import inputModal from './components/inputModal'

export default {
  name: 'App',
  data(){
    return {
      year: 12,
      modal: false,
      months: [
        {
          id: 1,
          todoList: ['1월의 할일']
        },
        {
          id: 2,
          todoList: ['2월의 할일']
        },
        {
          id: 3,
          todoList: ['3월의 할일']
        },
        {
          id: 4,
          todoList: ['4월의 할일']
        },
        {
          id: 5,
          todoList: ['5월의 할일']
        },
        {
          id: 6,
          todoList: ['6월의 할일']
        },
        {
          id: 7,
          todoList: ['7월의 할일']
        },
        {
          id: 8,
          todoList: []
        },
        {
          id: 9,
          todoList: []
        },
        {
          id: 10,
          todoList: []
        },
        {
          id: 11,
          todoList: []
        },
        {
          id: 12,
          todoList: []
        },
      ]
    }
  },
  components: {
    oneMonth,
    yearHeader,
    inputModal,
  },
  methods: {
    openModal() {
      this.modal = true;
    },
    closeModal() {
      this.modal = false;
    },
    addNewTodo(selectedMonth, newTodoData){
      let todoArray = [];
      todoArray.push(JSON.parse(newTodoData));
      console.log(todoArray, selectedMonth, newTodoData);
      // localStorage.setItem(selectedMonth, JSON.stringify(todoArray));
      // for (let i = 0; i < this.months.length; i++) {
      //   if (i == selectedMonth) {
      //     let todoArray = [];
      //     if (localStorage.getItem(i) !== '') {
      //       todoArray.push(JSON.parse(newTodoData));
      //       localStorage.setItem(selectedMonth, JSON.stringify(todoArray));
      //       this.months[i].todoList.push(newTodoData);
      //     }
      //   }
      // }
    }
  },
  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== 'loglevel:webpack-dev-server') {
          // let originArray = [];
          // if (localStorage.getItem(i) !== '') {
          //   originArray.push(JSON.parse(localStorage.getItem(i)));
          //   localStorage.setItem(i, JSON.stringify(originArray));
          //   this.months[i].todoList.push(localStorage.getItem(i));
          // }
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#app {
  min-height: 100vh;
  background: #efefef;
}
.year-wrap {
  display: flex;
  flex-wrap: wrap;
  justify-content: stretch;
  box-sizing: border-box;
  height: 100vh;
  padding: 50px 10px 10px;
  .month-wrap {
    width: calc((100% - 64px) / 4);
    box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.05);
    margin: 8px;
    border-radius: 5px;
    background: #fff;
  }
}
</style>
<style lang="scss" src="./assets/reset.scss"></style>
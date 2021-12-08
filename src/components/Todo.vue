<template>
  <div class="todo">
    <div class="top ">
      <h1 class="fw-bold">Todo</h1>
      <button class="btn-switch">
        <img src="@/assets/icon-moon.svg" alt="Change color theme" />
      </button>
    </div>
    <div class="champ ">
      <div class="add mt-1">
        <button id="add-btn" @click="add()">+</button>
        <input
          type="text"
          class="w-100"
          placeholder="Create a new todo..."
          autocomplete="off" v-model="tache"
        />
      </div>
      <div class="list">
        <ul class="todos ">
          <li v-for="task, index in list" :key="index" class="task" > 
            <!-- <span class="circle">
            </span> -->
            <input type="checkbox" name="done" v-model="fini" @click="finish(index)" >
            <label for="" :class="{'line': fini}">{{task.task}}</label>
          </li>
        </ul>
        <div class="stat">
          <span class="left"> items left</span>
          <div class="filter">
            <button id="all" class="on">All</button>
            <button id="active">Active</button>
            <button id="completed">Completed</button>
          </div>
          <div class="corner">
            <button id="clear-completed">Clear Completed</button>
          </div>
        </div>

      </div>
      </div>

  </div>
</template>

<script>
export default {
  name: 'todo',
  data() {
    return {
      list: [],
      tache: '',
      fini: '',
    }
  },
  methods: {
    add() {
      console.log(this.list);
      this.list.push({"task":this.tache, "done":false})
      this.tache = ""
    },
    finish(i) {
      console.log(this.list[i].done = true);
        
    }
  }

} 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
  .todo
    color: white
    width: 50vw
    position: absolute
    top: 10vh
    left: 50%
    transform: translateX(-50%)
    .top      
      text-transform: uppercase
      display: flex
      align-items: center
      justify-content: space-around
      letter-spacing: 8px
      .btn-switch
        background-color: transparent
        border: none
    .champ
      margin-top: 10px
      .add 
        display: flex
        justify-content: space-around
        padding: 3px 6px
        border: solid gray 0.5px
        background-color: white
        border-radius: 15px
        input
          border: none
        #add-btn
          border: none
          background-color: transparent


      .list
        border: solid gray 0.5px
        background-color: white
        border-radius: 15px
        margin-top: 10px
        .todos
          color: black
          list-style: none
          padding: 5px 13px
          border-bottom: solid 1px hsl(0, 0%, 98%)
          .line 
            text-decoration: line-through
          .task
            display: flex
            .circle
              margin-right: 2%
              &::before
                content: ''
                display: inline-block
                width: 23px
                height: 23px
                border-radius: 50%
                border: solid 1px black
                cursor: pointer
                background-color: red
        .stat
          font-size: 12px
          display: flex 
          align-items: center
          position: relative
          .left 
            color: black
            font-size: 10px
          .filter
            margin-left: 8vw
            button
              border: none
              background-color: transparent
          .corner
            position: absolute
            right: 0
            button
              border: none
              background-color: transparent
            

  
  </style>

<template>
  <div class="todo">
    <div class="todo__header">
      <h1 class="todo__title">Todo list</h1>
      <button class="todo__button" @click="addTodo">Add</button>
    </div>
    <div class="todo__main">
      <ul class="todo__list">
        <li class="todo__item" v-for="(listItem, index) in this.todoList" :key="index">
          <label class="checkbox">
            <input type="checkbox" v-model="checkbox" :value="`value_${index}`" class="checkbox__input"/>
            <div class="checkbox__checkmark">
              <div class="checkbox__checkmark_true"></div>
            </div>
            <div class="checkbox__body">
              <p class="checkbox__text-normal">{{ listItem.listItemText }}</p>
              <p class="checkbox__text-small">{{ listItem.listItemSubtext }}</p></div>
          </label>
        </li>
      </ul>
      <div class="todo__list_shadow-bottom"></div>
    </div>
  </div>
</template>

<script>

export default {
  name: "TodoListComponent",
  props: ['todoList'],
  data() {
    return {
      checkbox: []
    }
  },
  methods: {
    addTodo() {
      console.log('add todo')

    }
  }
}
</script>

<style scoped lang="scss">

.todo {
  padding: 30px;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  background-color: #252E42;
  box-shadow: 0 14px 34px rgba(0, 0, 0, 0.25);
  border-radius: 20px 0 40px;
  position: relative;
  z-index: 3;
  transform-style: preserve-3d;

  ::-webkit-scrollbar {
    width: 4px;
    background-color: transparent;
  }

  ::-webkit-scrollbar-thumb {
    background-color: #FF8469;
    border-radius: 9em;
  }
}

.todo:before {
  content: '';
  position: absolute;
  z-index: -1;
  width: 94%;
  height: 70px;
  top: -10px;
  left: 0;
  background: linear-gradient(180deg, #31394D 0%, #091739 100%);
  border-radius: 20px;
  transform: translateZ(-1px) rotate(-2.32deg);
  transform-origin: 0 0 0;
}

.todo:after {
  content: "";
  position: absolute;
  z-index: -5;
  width: 85%;
  height: 85px;
  top: -15px;
  left: 0;
  background: linear-gradient(180deg, #4F5565 0%, #000000 53.65%);
  border-radius: 20px;
  transform: translateZ(-2px) rotate(-4.48deg);
  transform-origin: 0 0 0;
}

.todo__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 30px;
  color: #ffffff;

}

.todo__title {
  font-weight: 600;
  font-size: 28px;

}

.todo__button {
  background: #FF8469;
  border-radius: 7px;
  padding: 5px 10px;
  text-transform: uppercase;
  font-size: 14px;
  font-weight: 400;
  transition: 0.3s;
  cursor: none;
}
.todo__button:hover {
  background: #D95133;
  transition: 0.3s;

}
@media (min-width: 1024px) {
  .todo__button {
    cursor: pointer;
  }
}

.todo__main {
  width: 100%;
  height: 100%;
  padding: 20px 0;
  position: relative;
  overflow: hidden;
  display: flex;
}

.todo__list {
  width: 100%;
  height: 100%;
  overflow: auto;
  position: relative;
  padding: 0 10px 20px 0;
}

.todo__list_shadow-bottom {
  position: absolute;
  width: 98%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
  box-shadow: #252E42 0px -55px 30px -14px inset;
}


.todo-item {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}


.checkbox {
  display: flex;
  align-items: center;
  position: relative;
  margin-bottom: 20px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

@media (min-width: 1024px) {
  .checkbox:hover .checkbox__text-normal {
    color: #FF8469;
    transition: 0.3s;
  }
  .checkbox:hover .checkbox__checkmark {
    background-color: rgba(183, 85, 63, 0.2);
    transition: 0.3s;
  }
  .checkbox:hover input:checked ~ .checkbox__checkmark {
    background-color: #FF8469;
  }
  .checkbox {
    cursor: pointer;
  }
}

.checkbox input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

.checkbox input:checked ~ .checkbox__body .checkbox__text-normal {
  color: #4F5565;
  text-decoration: line-through;
  transition: all 0.25s
}

.checkbox input:checked ~ .checkbox__body .checkbox__text-small {
  color: #4F5565;
  text-decoration: line-through;
  transition: all 0.25s
}

.checkbox input:checked ~ .checkbox__checkmark {
  background-color: #FF8469;
}

.checkbox input:checked ~ .checkbox__checkmark .checkbox__checkmark_true {
  opacity: 1;
}



.checkbox .checkbox__checkmark {
  aspect-ratio: 1 / 1;
  width: 20px;
  background-color: #4F5565;
  transition: 0.3s;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
}



.checkbox .checkbox__checkmark_true {
  width: 5px;
  height: 11px;
  border: solid #ffffff;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
  opacity: 0;
  transition: opacity 0.25s ease;
}

.checkbox .checkbox__body {
  display: flex;
  flex-direction: column;
  align-items: start;
  text-align: left;
  width: 100%;
  margin-left: 15px;
}

.checkbox__text-normal {
  font-size: 16px;
  font-weight: 400;
  color: #ffffff;
}

.checkbox__text-small {
  font-size: 12px;
  color: #4F5565;
}

</style>

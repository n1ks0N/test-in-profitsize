<script setup>
import { ref } from "vue";
import TodoItem from "./components/TodoItem.vue";
const todoArray = ref([
  {
    id: 1,
    title: "delectus aut autem",
    text: "laboriosam mollitia et enim quasi adipisci quia provident illum",
    completed: false,
  },
  {
    id: 2,
    title: "quo laboriosam deleniti aut qui",
    text: "",
    completed: true,
  },
  {
    id: 3,
    title: "laboriosam mollitia et enim quasi adipisci quia provident illum",
    text: "",
    completed: false,
  },
  {
    id: 4,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: true,
  },
  {
    id: 5,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
  {
    id: 6,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
  {
    id: 7,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
  {
    id: 8,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
  {
    id: 9,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
  {
    id: 10,
    title: "repellendus sunt dolores architecto voluptatum",
    text: "accusamus eos facilis sint et aut voluptatem",
    completed: false,
  },
]);
</script>

<template>
  <div>
    <main>
      <div class="todo-wrapper">
        <div class="todo-wrapper__header">
          <h1 class="todo-wrapper__title">Todo list</h1>
          <button type="button" class="btn btn-add">Add</button>
        </div>
        <div class="todo-wrapper__cards">
          <TodoItem v-for="item in todoArray" :data="item" :key="item.id" />
        </div>
        <div class="todo-wrapper__bg" />
      </div>
    </main>
    <footer>
      <p class="footer__text">© 2022. Nikita Gromiakov</p>
    </footer>
  </div>
</template>

<style>
@import url("assets/base.css");
.btn {
  transition: background-color 0.2s ease-in-out;
}

main {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: center;
  width: 100vw;
  position: relative;
}
main::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: radial-gradient(35.13% 50% at 50% 50%, #252e42 0%, #161c2e 100%);
  /* background: red; */
  animation: bg-changer 1s infinite alternate both;
  z-index: -3;
}

@keyframes bg-changer {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.todo-wrapper {
  position: relative;
  padding: 30px;
  padding-right: 16px;
  margin-top: 120px;

  width: 420px;
  height: 540px;

  background: #252e42;
  box-shadow: 0px 14px 34px rgba(0, 0, 0, 0.25);
  box-sizing: border-box;
  border-radius: 20px 0px 40px;
}
.todo-wrapper::before {
  content: "";
  position: absolute;
  width: 395.1px;
  height: 67.97px;
  z-index: -1;
  top: -25px;
  left: 0;

  background: linear-gradient(180deg, #31394d 0%, #091739 100%);
  border-radius: 20px;
  transform: rotate(-2.32deg);
}
.todo-wrapper::after {
  content: "";
  position: absolute;
  width: 341.86px;
  height: 85.23px;
  top: -41px;
  left: 0;
  z-index: -2;

  background: linear-gradient(180deg, #4f5565 0%, #000000 53.65%);
  border-radius: 20px;
  transform: rotate(-4.48deg);
}
.todo-wrapper__header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0px;
  padding-right: 14px;
  height: 34px;
}

.btn-add {
  width: 54px;
  height: 27px;

  background: #ff8469;
  border-radius: 7px;
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;

  text-transform: uppercase;

  color: #ffffff;
}
.btn-add:hover {
  background: #d95133;
}

.todo-wrapper__title {
  font-style: normal;
  font-weight: 700;
  font-size: 28px;
  line-height: 34px;

  color: #ffffff;
}
.todo-wrapper__cards {
  overflow-y: scroll;
  height: 447px;
  margin-top: 20px;
  overflow-x: hidden;
}
.todo-wrapper__bg {
  position: relative;
  width: 0;
  height: 0;
}
.todo-wrapper__bg::after {
  content: "";
  position: absolute;
  width: 361px;
  height: 75px;
  bottom: 0;
  background: linear-gradient(180deg, rgba(37, 46, 66, 0) 0%, #252e42 67.19%);
}

footer {
  margin-top: 30px;
  text-align: center;
}
.footer__text {
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 20px;

  color: #414b62;
}

/* Adaptive */
@media screen and (max-width: 500px) {
  .todo-wrapper {
    width: calc(100vw - 30px);
    max-width: 397px;
    height: 580px;
  }
  .todo-wrapper::before {
    width: 328.11px;
  }
  .todo-wrapper::after {
    width: 284.18px;
  }
  .todo-wrapper__bg::after {
    width: calc(100vw - 30px - 60px);
    max-width: 397px;
    bottom: -5px;
  }
}
</style>

<script setup>
const props = defineProps({
  data: Object,
});
</script>

<template>
  <label class="todo-card">
    <span
      class="todo-card__checkmark"
      v-bind:class="{ 'todo-card__checkmark_active': data.completed }"
    />
    <div class="todo-card__content">
      <p
        class="todo-card__title"
        v-bind:class="{ 'todo-card__title_active': data.completed }"
      >
        {{ data.title }}
      </p>
      <p
        class="todo-card__text"
        v-bind:class="{ 'todo-card__text_active': data.completed }"
      >
        {{ data.text }}
      </p>
    </div>
    <input type="checkbox" class="todo-card__input" v-model="data.completed" />
  </label>
</template>

<style>
.todo-card {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  margin-bottom: 18px;
  /* padding-left: 35px; */
  cursor: pointer;
  position: relative;
  user-select: none;
  width: 360px;
}
.todo-card::after {
  content: "";
  position: absolute;
  right: -10px;
  width: 40px;
  height: 100%;
  background: linear-gradient(90deg, rgba(37, 46, 66, 0) 0%, #252E42 67.19%);
}
.todo-card:last-child {
  margin-bottom: 80px;
}
.todo-card__input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

/* Card's hovers */
.todo-card:hover .todo-card__checkmark:not(.todo-card__checkmark_active) {
  background: rgba(255, 132, 105, 0.2);
}
.todo-card:hover .todo-card__title {
  color: #ff8469;
}
.todo-card:hover .todo-card__title_active {
  color: #fff;
}

.todo-card__checkmark {
  height: 20px;
  width: 20px;
  background: #4f5565;
  border-radius: 6px;
  transition: background-color 0.2s ease-in-out;
  position: relative;
}
.todo-card__checkmark_active:after {
  content: "";
  position: absolute;
  display: block;
  left: 6.5px;
  top: 2.5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}
.todo-card__content {
  margin-left: 15px;
  width: 325px;
}
.todo-card__title {
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 20px;

  color: #ffffff;

  transition: color 0.2s ease-in-out;
}
.todo-card__text {
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;

  color: #4f5565;
  text-overflow: clip;
  white-space: nowrap;
}

/* For active cards */
.todo-card__title_active,
.todo-card__text_active {
  text-decoration-line: line-through;
  color: #4f5565;
}
.todo-card__checkmark_active {
  background: #ff8469;
}

/* Adaptive */
@media screen and (max-width: 500px) {
  .todo-card {
    width: calc(100vw - 30px - 60px)
  }
  .todo-card__content {
    width: calc(100vw - 30px - 95px);
  }
}
</style>

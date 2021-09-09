<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title has-text-left">
       {{today}}
      </p>
      <div class="has-text-right">
        <p class="card-header-title">{{tasks.length}} tasks</p>
      </div>
    </header>
    <div class="card-content">
      <div class="content">
        <new-todo></new-todo>
      </div>
      <div class="content"></div>
    </div>
  </div>
</template>

<script>
import NewTodo from './NewTodo'
export default {
  name: 'todo-card',
  components: {
    NewTodo
  },
  data () {
    return {
      days: ['Domingo', 'Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sábado'],
      months: ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'],
      tasks: []
    }
  },
  computed: {
    today: function() {
      let newDate = new Date()
      return `${this.days[newDate.getDay()]}, ${newDate.getDate()} de ${this.months[newDate.getMonth()]}`
    }
  }
}
</script>

<style>
.card {
  border-radius: 10px;
}
.card-header-title {
  color: #636368;
}
</style>
<template>
  <div>
    <h1>{{ nome }}</h1>
    <input type="text" v-model="nome">

    <h1>Minha Lista</h1>
    <input type="text" v-model="novoItem">
    <input type="button" value="Adicionar" @click="adicionarItem">

    <ul>
      <li v-for="(item, index) in task" :key="index">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nome: 'André',
      novoItem: '',
      task: [
       
      ]
    }
  },
  methods: {
    adicionarItem() {
      if (this.novoItem.trim() !== '') {
        this.task.push({ name: this.novoItem });
        this.novoItem = '';
      }
    }
  }
}
</script>



<template>
  <div class="home">
    <div>
      <v-col class="input"
            cols="12"
            sm="6"
          >
            <v-text-field
              v-model="inputTarefas"
              label="Tarefas"
              outlined
              clearable
              @keyup.enter="AddTarefa"
            ></v-text-field>
          </v-col>
      <div v-for="(tarefa, index) of tarefas" :key=(index)>
      <Tarefas
      :tarefa="tarefa"
        />
    </div>

  </div> 
  </div>
</template>

<script>
import Tarefas from '../views/Tarefas.vue'
export default {
  name: 'Home',
  data() {
        return{
           inputTarefas :  null,
           drawer: false,
           group: null,
           tarefas:[
        {titulo: 'Ser feliz', concluido: false},
        {titulo: 'Passar no hackthon', concluido: false},
         ]
        }
    },
    components: {
      Tarefas,

    }, 
    methods: {
      AddTarefa(){
        if(this.inputTarefas){
          this.tarefas.push({
            titulo: this.inputTarefas, concluido: false,
          })
        }this.inputTarefas = null
      }
    }
}
</script>
<style scoped>
.input{
  margin: 0 auto;
 
}
</style>
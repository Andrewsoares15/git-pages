<template>
  <div class="text-center teste">
      <v-list
      flat
      subheader

    >
      <v-list-item-group
        multiple
        active-class=""
      >
        <v-list-item>
          <template v-slot:default="{ active } ">
            <v-list-item-action class="chec">
              <v-checkbox :input-value="active"></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title>{{tarefa.titulo}}</v-list-item-title>
            </v-list-item-content>
          </template>
        </v-list-item>


      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
export default {
    name: 'Tarefas',
    props:['tarefa']
}
</script>

<style>
.chec{
    position: relative;
    left: 44%;
}
@media only screen and (max-width: 400px) {
  .chec{
    position: relative;
    left: 27%;
}
}

</style>
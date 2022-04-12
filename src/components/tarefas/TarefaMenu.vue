<template>
  <div>
      <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          
          v-bind="attrs"
          v-on="on"
          icon
        >
          <v-icon>
          mdi-menu-down
          mdi-application-edit-outline
          mdi-delete-empty
          </v-icon>
      
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
          @click="item.click()"
          
        >
          <v-icon left>
            {{item.icone}}
            {{item.icone}}
          </v-icon>

          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    
    <EditCamp
    v-if="items[0].editcamp"
    @fechaEdit="items[0].editcamp = false"
    :tarefa="tarefa"
     />
  
  </div>
</template>

<script>
import EditCamp from '../EditCamp/EditCamp.vue'
  export default {
  props:['tarefa'],
  components: { EditCamp },
    data: () => ({
      items: [
        { 
          icone:"mdi-application-edit-outline", 
          title: 'Editar',
          editcamp: false,
          click(){
            console.log("editar")
            this.editcamp = true
          }
        },
        { 
          icone:"mdi-delete-empty", 
          title: 'Excluir',
          click(){
            console.log("excluir")
          }
        },
      ],
    }),
  }
</script>

<style>

</style>
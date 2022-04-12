<template>
  <div>
      <v-dialog
      v-model="dialog"
      persistent
      max-width="290"
    >
      <v-card>
        <v-card-title class="text-h5">
          Editar Tarefa
        </v-card-title>
        <!-- <v-card-text>informe um novo titulo</v-card-text> -->

        <v-text-field
            class="px-3"
            label="Titulo"
            placeholder="Informe um titulo"
            outlined
          ></v-text-field>
        
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn

            color="red"
            text
            @click="dialog = false"
          >
            <v-icon color="red">
              mdi-close-circle
          </v-icon>
            Cancelar 
          </v-btn>
          <v-btn
            color="green darken-1"
            text
            @click="dialog = false"
          >
          <v-icon color="green darken-1">
              mdi-check-bold
          </v-icon>
            Editar
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        dialog: true,
      }
    },
  }
</script>

<style>

</style>
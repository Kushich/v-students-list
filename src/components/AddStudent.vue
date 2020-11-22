<template>
  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      persistent
      max-width="400"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          block
          v-bind="attrs"
          v-on="on"
        >
          Добавить студента
        </v-btn>
      </template>
      <v-card>
        <v-card-title class="headline">
          Добавить студента
        </v-card-title>
        <v-card-text>
          <v-form
            ref="form"
            v-model="valid"
            lazy-validation
          >
            <v-text-field
              v-model="name"
              :counter="10"
              :rules="nameRules"
              label="ФИО"
              required
            ></v-text-field>

            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Дата рождения"
              required
            ></v-text-field>

            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Вид спорта"
              required
            ></v-text-field>

            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Специализация"
              required
            ></v-text-field>

            <!-- <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Дата обследования"
              required
            ></v-text-field>
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Место обследования"
              required
            ></v-text-field> -->

            <v-btn
              color="red darken-1"
              text
              @click="dialog = false"
            >
              Отменить
            </v-btn>
            <v-btn
              color="green darken-1"
              text
              @click="dialog = false"
            >
              Добавить
            </v-btn>
          </v-form>
        </v-card-text>
      </v-card>

    </v-dialog>
  </v-row>
</template>

<script>
  export default {
    data () {
      return {
        dialog: false,
      }
    },
  }
</script>
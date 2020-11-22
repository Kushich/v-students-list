<template>
  <v-main class="grey lighten-3">
    <v-container class="grey lighten-3">
      <v-row>
        <v-col>
          <v-card>
            <v-card-title>
              <v-row>
                <v-col cols="12">
                  <add-student class="px-2"/>
                </v-col>
                <v-col cols="6">
                  <v-text-field
                    v-model="search"
                    append-icon="mdi-magnify"
                    label="Поиск"
                    single-line
                    hide-details
                  ></v-text-field>
                </v-col>
                <v-col cols="6">
                  <v-select
                    v-model="sportType"
                    :items="sportTypes"
                    label="Вид спорта"
                    hide-details
                    single-line
                  ></v-select>
                </v-col>
              </v-row>
            </v-card-title>
            <v-data-table
              :headers="headers"
              :items="students"
              :search="search"
              item-ley="student"
            ></v-data-table>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { students as studentsData } from './../data/students'
import AddStudent from './../components/AddStudent.vue'

@Component({
  components: {
    AddStudent
  },
})
export default class Home extends Vue {
  sportType = ''
  sportTypes = ['Любой', 'Футбол', 'Рукабол']
  search = ''
  students = studentsData

  get headers () {
    return [
      {
        text: 'ФИО',
        align: 'start',
        sortable: false,
        value: 'student',
      },
      { text: 'Дата рождения', value: 'dateOfBirth' },
      { 
        text: 'Вид спорта',
        value: 'sportType',
        filter: (value: string) => {
          if (!this.sportType) return true
          if (this.sportType === 'Любой') {
            this.sportType = ''
            return true
          }

          return value === this.sportType
        },
      },
      { text: 'Квалификация', value: 'qualification' },
      { text: 'Специализация', value: 'specification' },
      { text: 'Дата обследования', value: 'dateOfExamination' },
      { text: 'Место обследования', value: 'placeOfExamination' },
    ]
  }
}
</script>

<template>
  <v-app id="inspire">
  <v-card>
    <v-card-title>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="students"
      :search="search"
    ></v-data-table>
  </v-card>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class Home extends Vue {
  search = ''
  headers = [
    {
      text: 'ФИО',
      align: 'start',
      sortable: false,
      value: 'student',
    },
    { text: 'Дата рождения', value: 'dateOfBirth' },
    { text: 'Вид спорта', value: 'sportType' },
    { text: 'Квалификация', value: 'qualification' },
    { text: 'Специализация', value: 'specification' },
    { text: 'Дата обследования', value: 'dateOfExamination' },
    { text: 'Место обследования', value: 'placeOfExamination' },
  ]

  students = [
    {
      student: 'Зубенко Михаил Петрович',
      dateOfBirth: '14/12/1999',
      sportType: 'Футбол',
      qualification: '1-й разряд',
      specification: 'футбол',
      dateOfExamination: '21.11.2020',
      placeOfExamination: 'Медицинский центр "Волна"',
    },
    {
      student: 'Зубенко Михаил Петрович',
      dateOfBirth: '14/12/1999',
      sportType: 'Рукабол',
      qualification: '1-й разряд',
      specification: 'футбол',
      dateOfExamination: '21.11.2020',
      placeOfExamination: 'Медицинский центр "Волна"',
    },
    {
      student: 'Зубенко Михаил Петрович',
      dateOfBirth: '14/12/1999',
      sportType: 'Футбол',
      qualification: '2-й разряд',
      specification: 'футбол',
      dateOfExamination: '21.11.2020',
      placeOfExamination: 'Медицинский центр "Волна"',
    },
    {
      student: 'Зубенко Михаил Петрович',
      dateOfBirth: '14/12/1999',
      sportType: 'Рукабол',
      qualification: '2-й разряд',
      specification: 'футбол',
      dateOfExamination: '21.11.2020',
      placeOfExamination: 'Медицинский центр "Волна"',
    },
    {
      student: 'Зубенко Михаил Петрович',
      dateOfBirth: '14/12/1999',
      sportType: 'Футбол',
      qualification: '1-й разряд',
      specification: 'футбол',
      dateOfExamination: '21.11.2020',
      placeOfExamination: 'Медицинский центр "Волна"',
    },
  ]
}
</script>

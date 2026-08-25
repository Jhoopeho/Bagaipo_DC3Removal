<script setup>
import { ref } from 'vue'

const emit = defineEmits(['student-submitted'])

const name = ref('')
const studentId = ref('')
const course = ref('')
const yearLevel = ref('')
const email = ref('')

function submitStudent() {
  const studentInfo = {
    name: name.value,
    studentId: studentId.value,
    course: course.value,
    yearLevel: yearLevel.value,
    email: email.value
  }

  emit('student-submitted', studentInfo)

  name.value = ''
  studentId.value = ''
  course.value = ''
  yearLevel.value = ''
  email.value = ''
}
</script>

<template>
  <form @submit.prevent="submitStudent">
    <label>
      Student Name
      <input v-model="name" type="text" required>
    </label>

    <br>

    <label>
      Student ID
      <input v-model="studentId" type="text" required>
    </label>

    <br>

    <label>
      Course
      <select v-model="course" required>
        <option disabled value="">Select a course</option>
        <option value="BSIT">BSIT</option>
        <option value="BSCS">BSCS</option>
        <option value="BSIS">BSIS</option>
      </select>
    </label>

    <br>

    <label>Year Level</label>

    <input v-model="yearLevel" type="radio" value="1st Year" required>
    1st Year

    <input v-model="yearLevel" type="radio" value="2nd Year">
    2nd Year

    <input v-model="yearLevel" type="radio" value="3rd Year">
    3rd Year

    <input v-model="yearLevel" type="radio" value="4th Year">
    4th Year

    <br>

    <label>
      Email
      <input v-model="email" type="email" required>
    </label>

    <br>

    <button type="submit">Submit Student</button>
  </form>
</template>

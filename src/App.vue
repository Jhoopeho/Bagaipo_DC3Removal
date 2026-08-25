<script setup>
import { ref } from 'vue'
import StudentForm from './components/StudentForm.vue'
import StudentDisplay from './components/StudentDisplay.vue'

const student = ref()

function handleStudentSubmitted(studentInfo) {
  student.value = studentInfo
}
</script>

<template>
  <h1>Student Information System</h1>

  <StudentForm @student-submitted="handleStudentSubmitted" />

  <StudentDisplay :student="student" />
</template>

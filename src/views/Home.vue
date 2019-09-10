<template>
  <div class="schedule-course">
    <hi> Make a course schedule</hi>
    <get-course v-if="step== 1"></get-course>
  </div>
</template>

<script>
import HelloWorld from '../components/HelloWorld';
import GetCourse from './GetCourse';

export default {
  components: {
    GetCourse
  },
  data() {
    return {
      step: 1,
      selectedCourse: null
    }
  }
};
</script>

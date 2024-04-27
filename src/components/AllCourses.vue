<template>
    <div class="courses-list">
        <div class="course" v-for="course of courses" :key="course.course_code">
            <SingleCourse :course=course />
        </div>
        <hr />
    </div>
</template>
<script>
import SingleCourse from './SingleCourse.vue'

export default {
    name: 'AllCourses',
    props: {
        courses: Array
    },
    components: {
        SingleCourse
    }

}
</script>
<style scoped>
.courses-list {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
}

.courses-list .course {
    width: 100%;
    border-bottom: 1px solid #d1d7dc;
    margin-bottom: 0;
}
</style>

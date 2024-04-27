<template>
    <div class="course-card">
        <div class="img-div">
            <img width="260" height="150" :src="course.course_image" alt="">
        </div>
        <div class="course-details">
            <h4 class="course-name">{{ course.course_name }}</h4>
            <p class="description">{{ course.course_description }}</p>
            <div>
                <p class="instructor">{{ course.instructor }}</p>
                <p class="time">{{ course.time }} &#8226; {{ course.days }}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'SingleCourse',
    props: {
        course: Object
    }
}
</script>

<style scoped>


.course-name {
    margin: 2px;
    font-size: 18px;
    font-weight: bolder;
}
.description, .instructor, .time{
    margin: 15px 0;
    font-size: 14px;
}
.instructor {
    font-weight: bold;
}
.course-card {
    display: flex;
    padding: 30px;
    background-color: #fff;
}

.img-div {
    margin: 0 15px;
}

.course-details {
    margin: 0 15px;
}

@media screen and (max-width: 750px) {
    .course-card {
        flex-direction: column;
    }
}

@media screen and (max-width: 476px) {
    .course-card {
        width: 100% !important;
    }
}
</style>
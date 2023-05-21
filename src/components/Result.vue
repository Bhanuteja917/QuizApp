<script setup>
    import {RouterLink} from 'vue-router';

    const { quizQuestionsLength, noOfCorrectAnswers } = defineProps(['quizQuestionsLength', 'noOfCorrectAnswers'])
</script>

<template>
    <div class="results">
        <p>You Results...</p>
        <h1>
            {{noOfCorrectAnswers}}/{{ quizQuestionsLength }}
        </h1>
        <RouterLink to="/">Go Back</RouterLink>
    </div>
</template>

<style scoped>
    .results {
        text-align: center;
        padding: 100px 0;
    }

    p {
        font-size: 25px;
    }

    h1 {
        font-size: 80px;
    }
</style>
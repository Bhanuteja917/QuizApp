<script setup>
    import Question from "../components/Question.vue";
    import QuizHeader from "../components/QuizHeader.vue";

    import { useRoute } from "vue-router";
    import { ref, computed } from "vue";
    import quizzes from "../data/quizzes.json"

    const route = useRoute();
    const quizId = parseInt(route.params.id)
    const quiz = quizzes.find(q => q.id == quizId)
    const currentQuestionIndex = ref(0)   
    const noOfCorrectAnswers = ref(0)
    
    const questionStatus = computed(() => `${currentQuestionIndex.value}/${quiz.questions.length}`)
    const barPercentage = computed(() => `${currentQuestionIndex.value/quiz.questions.length*100}%`)
    const onOptionSelected = (isCorrect) => {
        if(isCorrect) {
            noOfCorrectAnswers.value++
        }
        currentQuestionIndex.value++
    }
</script>

<template>
    <div>
        <QuizHeader
            :questionStatus="questionStatus"
            :barPercentage="barPercentage"
        />
        <div>
            <Question 
                :question="quiz.questions[currentQuestionIndex]"
                @selectOption="onOptionSelected"
            />
        </div>
        <!-- <button @click="currentQuestionIndex++">Next Question</button> -->
    </div>
</template>

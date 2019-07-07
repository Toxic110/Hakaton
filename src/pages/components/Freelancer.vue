<template>
    <div class="">
      DSD
       
    </div>
</template>

<script>
import {
  Button
} from '@/components';
export default {
    components: {
    [Button.name]: Button
  },
    data() {
        return {
            questions: [
                {text: 'Вопрос 1'},
                {text: 'Вопрос 2'},
                {text: 'Вопрос 3'}
            ],
            questionIndex: 0
        }
    },
    methods: {
        nextQuestion() {
            this.questionIndex++;
        }
    }
}
</script>

<style lang="scss">
    .questions_wrap {
        button {
            margin: 0 10px;
        }
    }

</style>
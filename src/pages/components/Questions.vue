<template>
    <div class="questions_wrap">
         <div v-if="questions.length">
            <div class="question"  v-for="(question, index) in questions" :key="index" >
                <h3 v-show="index === questionIndex">{{ question.group }}</h3>
                <h2 v-show="index === questionIndex">{{question.text}}</h2>
                <n-button type="success" v-show="index === questionIndex" @click="nextQuestion">Да</n-button>
                <n-button type="info" v-show="index === questionIndex" @click="nextQuestion">Нет</n-button>
                <n-button type="danger" v-show="index === questionIndex" @click="nextQuestion">Пропустить</n-button>
            </div>
        </div>
        <div class="freelancers_wrappaer" v-show="questionIndex === questions.length">
            <div class="freelancers_wrap">
                <div class="freelancers" v-for="(frelancer, index) in freelancers" :key="index">
                    <div class="freelancer_avatar_wrapper"> 
                        <div class="freelancer_avatar">
                            <img class="rounded-circle" :src="frelancer.ava" alt="">
                        </div>
                    </div>
                    <div class="freelancer_info">
                        <div class="freelancer_info-name">
                            {{ frelancer.name }}
                        </div>
                        <div class="freelancer_info-direction">
                            Общее количество<br> отзывов <span class="text-success ">{{ frelancer.feedback }}</span>
                        </div>
                        <div class="freelancer_info-repa text-warning">
                            <i class="far fa-star"></i>
                            {{ frelancer.repa }} 
                        </div>
                    </div>
                </div>
            </div>
        </div>
       
    </div>
</template>

<script>
import {
  Button,
} from '@/components';
export default {
    components: {
    [Button.name]: Button,
  },
    data() {
        return {
            questions: [
                {group: 'Соблюдаются ли на объекте защиты проектные решения по:', text: 'Наличию системы обеспечения пожарной безопасности?'},
                {group: 'Соблюдаются ли на объекте защиты проектные решения по:', text: 'Противопожарным расстояниям между зданиями и сооружениями?'},
                {group: 'Соблюдаются ли на объекте защиты проектные решения по:', text: 'Наружному противопожарному водоснабжению?'},
                {group: 'Соблюдаются ли на объекте защиты проектные решения по:', text: 'Проездам и подъездам для пожарной техники?'},
                {group: 'Соблюдаются ли на объекте защиты проектные решения по:', text: 'Обеспечению безопасности пожарно-спасательных подразделений при ликвидации пожара?'}
            ],
            questionIndex: 0,
            freelancers: [
                {name: 'Ахушин Дмитрий Евпатович', repa: 4.0, feedback: 35, ava: require('@/assets/avatar/a1.jpg')},
                {name: 'Тестировка Тестир Затестович', repa: 3.5, feedback: 15, ava: require('@/assets/avatar/a2.jpg')},
                {name: 'Оттест Тест Тестович', repa: 4.2, feedback: 52, ava: require('@/assets/avatar/a3.jpg')},
                {name: 'Оттест Тест Тестович', repa: 3.9, feedback: 11, ava: require('@/assets/avatar/a4.jpg')},
                {name: 'Оттест Тест Тестович', repa: 4.1, feedback: 48, ava: require('@/assets/avatar/a1.jpg')}
            ]
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
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        margin-top: -80px;
        button {
            margin: 0 10px;
        }
    }

    .question {

        h2 {
            width: 600px;
            padding: 20px;
            margin: 0 auto;
            margin-bottom: 30px;
            background: #f96332;
            box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.15);
        }
    }

    .freelancers_wrappaer {
        height: 500px;
        margin-right: -15px;
        overflow: hidden;
    }

    .freelancers_wrap {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        height: 100%;
        margin-right: -20px;
        overflow-y: auto;
    }

    .freelancers {
        display: flex;
        align-items: center;
        padding: 20px;
        margin: 20px;
        height: 200px;
        width: 450px;
        box-sizing: border-box;
        background: #f96332;
        box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.15);

        .freelancer_info {
            margin: 0 auto;

            .freelancer_info-repa {
                font-size: 20px;
            }

            .freelancer_info-direction {
                font-size: 20px;
                margin-bottom: 5px;
            }

            .freelancer_info-name {
                font-size: 18px;
                margin-bottom: 5px;
            }
        }

        .freelancer_avatar {
            width: 100px;
            height: 100px;

            img {
                display: block;
                width: 100%;
            }
        }
    }
</style>

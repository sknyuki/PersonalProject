
<template>
<div>
        <header-view></header-view>
<v-container>
        <home-banner></home-banner>
        <br>
        <home-sell-list></home-sell-list>
        <br>
        <home-brand-check-list></home-brand-check-list>
        <br>
        <home-question-board :QuestionBoards="QuestionBoards"/>
        <br>
</v-container>
        <footer-view></footer-view>
</div>
</template>

<script>
import HeaderView from '../../components/home/headerView.vue'
import HomeBanner from '../../components/home/HomeBanner.vue'
import HomeSellList from '../../components/home/HomeSellList.vue'
import HomeBrandCheckList from '../../components/home/HomeBrandCheckList.vue'
import HomeQuestionBoard from '../../components/home/HomeQuestionboard.vue'
import { mapState, mapActions } from 'vuex'
import FooterView from '@/components/home/footerView.vue'

  export default {
    name: 'HomeView',

    components: {
        HeaderView,
        HomeBanner,
        HomeSellList,
        HomeBrandCheckList,
        HomeQuestionBoard,
        FooterView,
    },
 computed: {
        ...mapState(['QuestionBoards'])
    },
    mounted () {
        this.fetchQuestionBoardList()
    },
    methods: {
        ...mapActions(['fetchQuestionBoardList'])
    }

  }
</script>

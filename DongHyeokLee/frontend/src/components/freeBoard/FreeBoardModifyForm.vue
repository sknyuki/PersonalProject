<template>
    <div>
        <form @submit.prevent="onSubmit">
            <table>
                <tr>
                    <td>게시물 번호</td>
                    <td>
                        <input type="text" :value="freeBoard.boardNo" disabled/>
                    </td>
                </tr>
                <tr>
                    <td>제목</td>
                    <td>
                        <input type="text" v-model="title"/>
                    </td>
                </tr>
                <tr>
                    <td>작성자</td>
                    <td>
                        <input type="text" :value="freeBoard.writer" disabled/>
                    </td>
                </tr>
                <tr>
                    <td>등록일자</td>
                    <td>
                        <input type="text" :value="freeBoard.regDate" disabled/>
                    </td>
                </tr>
                <tr>
                    <td>본문</td>
                    <td>
                        <textarea cols="50" rows="20" v-model="content">
                        </textarea>
                    </td>
                </tr>
            </table>

            <div>
                <button type="submit">수정 완료</button>
                <router-link :to="{ name: 'FreeBoardReadPage',
                                    params: { boardNo: freeBoard.boardNo.toString() } }">
                    취소
                </router-link>
            </div>
        </form>
    </div>
</template>

<script>

export default {
    name: 'FreeBoardModifyForm',
    props: {
        freeBoard: {
            type: Object,
            required: true
        }
    },
    data () {
        return {
            title: '',
            content: ''
        }
    },
    methods: {
        onSubmit () {
            const { title, content } = this
            this.$emit('submit', { title, content })
        }
    },
    created () {
        this.title = this.freeBoard.title
        this.content = this.freeBoard.content
    }
}
</script>
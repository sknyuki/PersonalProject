<template>
    <div >
        <table border="1">
     
            <tr>
                <td>제목</td>
                <td>
                    <input type="text" :value="freeBoard.title" readonly/>
                </td>
            </tr>
            <tr>
                <td>작성자</td>
                <td>
                    <input type="text" :value="freeBoard.writer" readonly/>
                </td>
            </tr>
            <tr>
                <td>등록일자</td>
                <td>
                    <input type="text" :value="freeBoard.regDate" readonly/>
                </td>
            </tr>
            <tr>
                <td>본문</td>
                <td>
                    <textarea cols="50" rows="20" :value="freeBoard.content" readonly>
                    </textarea>
                </td>
            </tr>
        </table>
        
        <comments-register-page></comments-register-page>
    </div>
</template>

<script>


import CommentsRegisterPage from '@/views/comments/CommentsRegisterPage.vue'

export default {
    name: 'FreeBoardRead',
    props: {
        freeBoard: {
            type: Object,
            required: true
        }
    },
    components: {
       
        CommentsRegisterPage
    }
}
</script>

<style scoped>
    div {
        margin-left: 30%;
    }
    
  
</style>
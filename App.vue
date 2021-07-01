<template>
    <div>
        <d-puzzle v-bind="puzzleConfig[level]" @next="handleNext"/>
    </div>
</template>

<script>
    import DPuzzle from './Puzzle';
    export default {
        components: {
            DPuzzle
        },
        data () {
            return {
                level: 0,
                puzzleConfig: [
                    { row: 2, col: 2, img: './puzzleImg/zj.jpg' },
                    { row: 3, col: 3, img: './puzzleImg/zj.jpg' },
                    { row: 4, col: 4, img: './puzzleImg/zj.jpg' },
                    { row: 5, col: 5, img: './puzzleImg/zj.jpg' },
                    { row: 6, col: 6, img: './puzzleImg/zj.jpg' },
                    { row: 8, col: 8, img: './puzzleImg/zj.jpg' },
                ]
            }
        },
        methods: {
            handleNext () {
               if (++ this.level == this.puzzleConfig.length) {
                   const  answerFlag = window.confirm('已经是最后一关了，需要重新开始吗？');
                   if (answerFlag) {
                       this.level = 0;
                   }
               }
            }
        }
    }
</script>
<template>
    <div id = "container" v-if = "isDisplay">
        <div class = "ground" @click = "stopTimer"></div>
        <h3 class = "timer">{{ reaction }}ms</h3>
    </div>
</template>

<script>
    export default{
        name : "Playground",
        props : ["delay"],
        data(){
            return{
                isDisplay : false,
                timer : null,
                reaction : 0
            }
        },
        methods : {
            startTime(){
                this.timer = setInterval(() => {
                    this.reaction += 10
                }, 10)
            },
            stopTimer(){
                clearInterval(this.timer)
            }
        },
        mounted(){
            setTimeout(() => {
                this.isDisplay = true
                this.startTime()
            }, this.delay)
        }
    }
</script>

<style scoped>
    #container{
        max-width: 160px;
        margin: 40px auto;
    }

    .ground{
        background-color: darkgray;
        padding: 40px;
        width: 80px;
        height: 90px;
    }

    .timer{
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        color: #42b883 ;
    }
</style>

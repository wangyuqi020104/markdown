<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="./vue.js"></script>
    <style>
       .notebook,.input,.markdown{
           border: 1px solid red;
           height: 1000px;
       }

       .notebook{
           width: 20%;
           position: absolute;
           left: 0;
           top: 0;
           background-color: salmon;
       }
       .input{
           width: 40%;
           position: absolute;
           left: 20%;
           top: 0;
           background-color: seagreen;
       }

       .markdown{
           width: 40%;
           position: absolute;
           left: 60%;
           top: 0;
           background-color: skyblue;
       }
    </style>
</head>
<body>
    <div id="app">
        <div class="notebook">notebook</div>
        <div class="input">input</div>
        <div class="markdown"></div>
        </div>
        
    <div id="notebook">
        <div class="notebook">notebook</div>
        <div class="input">
            <textarea class="inputText" v-model="content">
            </textarea>
        </div>
        <div class="markdown">
        
        </div>
    </div>
    <script>
        const html=marked('**hello**')
        console.log(html)
        var vm =new Vue({
            el:"#notebook",
            data:{
                content:"hello world"
            },
            computed:{
                previewMarked(){
                    return marked(this.content)
                }
            }
        })
    </script>
</body>
</html>

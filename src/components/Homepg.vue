<template>
    <div class="homepg">
        <div class="chap">
            <h1>Let's create your resume</h1>
            <p>You can create your resume and download absolutely free.
                You will create your resume by editing this example of resume below.
                Let's do it and get a job!
            </p>
            <button>Create a Resume</button>
        </div>
        <div class="illust">
            <img src="../assets/resume.svg" alt="resume illustration">
        </div>
    </div>
</template>
<script>
export default {
    name: 'homepg'
}
</script>
<style scoped lang='less'> 
.homepg{
    width: 100vw;
    display: flex;
    padding: 100px 10px;
}
.chap{
    width: 50%;
    padding-top: 20px;
    padding-left: 50px;
     p{
    width: 30vw;
    font-size: 22px;
    padding: 0 10px;
    margin-top: -10px;
     }
}
.illust{
    width: 40%;
img{
    width: 45vw;
    height: auto;
    }
}
button{
    border-radius: 5px;
    border: none;
    outline: none;
    width: 130px;
    height: 35px;
    background-image: radial-gradient( circle farthest-corner at 10.2% 55.8%,  rgba(252,37,103,1) 0%, rgba(250,38,151,1) 46.2%, rgba(186,8,181,1) 90.1% );;
    color: honeydew;
    box-shadow:  2px 2px 5px rgba(250, 38, 151, 0.466),
             -2px -2px 5px rgba(186, 8, 180, 0.438);
    &:active{
    background: #fc2567;
    box-shadow: inset 5px 5px 10px #d61f58,
                inset -5px -5px 10px #ff2b76;
        }
    }
</style>
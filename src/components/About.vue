<template>
    <div>
        <div class="about">
            <div class="illust">
                <img src="../assets/about.svg" alt="">
            </div>
            <div class="ong">
                <h2>Learn tips to get a job sucessfully</h2>
                <p>
                    Getting that dream job can seem like an impossible task. We’re here to change that. Give yourself a real advantage with the best online resume maker: created by experts, improved by data, trusted by millions of professionals.</p>
                <button class="watch"><a href="https://www.youtube.com/watch?v=1IC0ybD-1TM" ><img src="../assets/watch.svg"/> <p> Watch a video</p></a></button>
                <button class="create"><img src="../assets/create.svg"/><p> Create a Resume</p></button>
            </div>
        </div>
        <div class="cont">
            <div class="result">
                <img src="../assets/icon1.png" alt="">
                <h3>Make a resume that wins interviews</h3>
                <p>Use our resume maker with its advanced creation 
                    tools to tell a professional story that engages 
                    recruiters, hiring managers and even CEOs.</p>
            </div>
            <div class="result">
                <img src="../assets/icon2.png" alt="">
                <h3>Resume writing made easy</h3>
                <p>Resume writing has never been this effortless.
                     Pre-generated text, visual designs and more - all 
                     already integrated into the resume maker.
                     Just fill in your details.</p>
            </div>
            <div class="result">
                <img src="../assets/icon3.png" alt="">
                <h3>A recruiter-tested CV maker tool</h3>
                <p>Our resume builder and its pre-generated content are 
                    tested by recruiters and IT experts. We help your CV become
                     truly competitive in the hiring process.</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'about'
}
</script>
<style scoped lang='less'>
.about{
    display: flex;
    padding: 30px 10px;
}
.illust{
    width: 50%;
}
.illust img{
    width: 35vw;
    margin-left: 70px;
}
.ong{
    width: 40%;
    padding: 20px 5px;
}

.ong p{
    padding: 0 5px;
}
.cont{
    display: flex;
    padding: 10px 20px;
    width: 90%;
    margin-left: 5%;
}
.watch{
    border-radius: 5px;
    width: 120px;
    border:none;
    outline: none;
    height: 50px;
    background-image: radial-gradient( circle farthest-corner at 10.2% 55.8%,  rgba(252,37,103,1) 0%, rgba(250,38,151,1) 46.2%, rgba(186,8,181,1) 90.1% );;
    color: honeydew;
    box-shadow:  2px 2px 5px rgba(250, 38, 151, 0.466),
             -2px -2px 5px rgba(186, 8, 180, 0.438);
    &:hover{
        background-image: radial-gradient( circle farthest-corner at 10.2% 55.8%,  rgb(207, 32, 85) 0%, rgb(197, 34, 121) 46.2%, rgba(148, 48, 145, 0.934) 90.1% );;
    }
    &:active{
    background: #fc2567;
    box-shadow: inset 5px 5px 10px #d61f58,
                inset -5px -5px 10px #ff2b76;
    }
    a{
        text-decoration:none;
    }
    a:link{
        color: honeydew;
    }
    a:visited{
        color: honeydew;
    }
    img{
        width: auto;
        height: 30px;
    }
}
.create{
    margin-left: 20px;
    border-radius: 5px;
    border: none;
    outline: none;
    width: 130px;
    height: 50px;
    border-radius: 5px;
    color: #fc2467;
    background: #f2f2f2;
    box-shadow:  5px 5px 10px #cecece,
                -5px -5px 10px #ffffff;
    &:hover{
        background-color: #e1e1e1;
    }
    &:active{
    background: #f2f2f2;
    box-shadow: inset 5px 5px 10px #cecece,
                inset -5px -5px 10px #ffffff;
    }
    img{
        width: auto;
        height: 30px;
    }
}
.cont > div{
    width: 32%;
    padding: 0 10px;
}
.result img{
    width: 50px;
    height: auto;
    margin-bottom: -20px;
}
.result h3{
    color: rgb(198, 38, 97);
    font-size: 1.3rem;
}
.result p{
    width: 75%;
    padding: 0 2px;
    margin-top: -20px;
    font-size: 17px;
}
.icons{
    font-size: 20px;
}
</style>
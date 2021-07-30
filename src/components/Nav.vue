<template>
     <ul>
         <li><img src="../assets/logo.png" alt="logo"></li> 
        <li>About</li>
        <li>Feedbacks</li>
        <li><button>About</button></li>
      </ul>
</template>
<script>
import About from './About.vue'
export default {
    name: 'Nav',
    components: {
        About
    }
}
</script>
<style scoped lang='less'>
ul{
    width: 100%;
    height: 70px;
    padding: 0;
    list-style: none;
    display: flex;
    justify-content: left;
    align-items: center;
}
li{
    font-size: 20px;
    padding: 0 10px;
    button{
    border-radius: 5px;
    border: none;
    outline: none;
    width: 130px;
    height: 25px;
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
   img{
    width: 150px;
    height: auto;
    } 
}
li:first-child{
    margin-right: 45%;
}

</style>
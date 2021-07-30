<template>
    <div id="app">
        <Nav/>
        <Homepg/>
        <About/>
        <Guide/>
        <div class="resume">
            <div class="left">
                <Brief :data="defaultData.Brief"/>
                <ContextList
                    title="CONTACT"
                    title-size="14px"
                    :icon="require('@/assets/title-contact.png')"
                >
                    <ListItemInfo
                        :title="item.value"
                        :image="item.icon"
                        slot="listItem"
                        v-for="item in defaultData.Contact"
                        :key="item.key"
                    />
                </ContextList>
                <ContextList
                    title="SOCIAL"
                    title-size="14px"
                    :icon="require('@/assets/title-contact.png')"
                >
                    <ListItemInfo
                        :title="item.value"
                        :image="item.icon"
                        slot="listItem"
                        v-for="item in defaultData.Social"
                        :key="item.key"
                    />
                </ContextList>
                <ContextList
                    title="Skill"
                    title-size="14px"
                    :icon="require('@/assets/title-contact.png')"
                >
                    <ListItemInfo
                        :title="item.value"
                        :image="item.icon"
                        slot="listItem"
                        v-for="item in defaultData.Skill"
                        :key="item.key"
                    />
                </ContextList>
            </div>
            <div class="right">
                <ContextList title="About me">
                    <ListItemAbout slot="listItem" :data="defaultData.AboutMe"/>
                </ContextList>
                <ContextList title="Education">
                    <ListItemEducation
                        slot="listItem"
                        :data="item"
                        v-for="item in defaultData.Education"
                        :key="item.school"
                    />
                </ContextList>
                <ContextList title="Working Experience">
                    <ListItemExperience
                        slot="listItem"
                        v-for="item in defaultData.WorkingExperience"
                        :data="item"
                        :key="item.compony"
                    />
                </ContextList>
            </div>
        </div>
        
        <div class="actions">
            <button @click="saveAsImage" class="image"><img src="./assets/pic.svg" alt=""><span>Save as PNG</span> </button>
            <!-- <button @click="saveAsPdf">Save as PDF</button> -->
            <button @click="print" class="print"><img src="./assets/download.svg" alt=""><span>Print as PDF</span></button>
        </div>
    </div>
</template>
<script>
import ContextList from '@/components/context-list'
import ListItemAbout from '@/components/list-item-about'
import ListItemSkill from '@/components/list-item-skill'
import ListItemEducation from '@/components/list-item-education'
import ListItemExperience from '@/components/list-item-experience'
import ListItemInfo from '@/components/list-item-info'
import html2canvas from '@/assets/js/html2canvas.js'
import FileSaver from 'file-saver'
import Brief from '@/components/brief'
import Guide from '@/components/guide'
import Nav from './components/Nav.vue'
import Homepg from './components/Homepg.vue'
import About from './components/About.vue'
// import GeneratePDF from './utils/generatePDF.js'
import defaultData from '@/config/data'
export default {
    name: 'app',
    components: {
        ContextList,
        ListItemAbout,
        ListItemSkill,
        ListItemEducation,
        ListItemExperience,
        ListItemInfo,
        Brief,
        Guide,
        Nav,
        Homepg,
        About
    },
    computed: {
        defaultData () {
            return defaultData
        }
    },
    methods: {
        // saveAsPdf () {
        //     const resume = document.querySelector('#resume')
        //     const pdf = new GeneratePDF(resume)
        //     pdf.generate()
        // },
        saveAsImage () {
            let resume = document.querySelector('.resume')
            html2canvas(resume).then(canvas => {
                canvas.toBlob(blob => {
                    FileSaver.saveAs(blob, 'Resume.png')
                })
            })
        },
        print () {
            window.print()
        }
    }
}
</script>
<style lang="less">
body {
    padding: 0;
    margin: 0;
}
ul {
    padding: 0;
    margin: 0;

    li {
        list-style: none;
    }
}

p {
    margin: 0 0 12px 0;
}

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
    color: #2c3e50;
    background:url('./assets/bg.png');
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    .resume {
        margin-top: 90px;
        position: relative;
        width: 790px;
        // height: 1754px;
        border-radius: 5px;
        background: #fff;
        box-shadow:  6px 6px 21px #c5cbd3,
                    -6px -6px 21px #ffffff;
        overflow: hidden;
        box-sizing: border-box;

        .left {
            width: 240px;
            height: 100%;
            box-sizing: border-box;
            float: left;
            background-color: #fdfefe;
            position: relative;
        }

        .right {
            box-sizing: border-box;
            width: calc(~'100% - 240px');
            float: left;
            padding: 25px 20px;
            border-left: 1px solid #dad8d7;

            p {
                font-size: 14px;
                line-height: 18px;
                color: #555;
                text-align: justify;
            }
        }
    }
    .image{
        border-radius: 5px;
        display: flex;
        width: 150px;
        border:none;
        outline: none;
        height: 40px;
        background-image: radial-gradient( circle farthest-corner at 10.2% 55.8%,  rgba(252,37,103,1) 0%, rgba(250,38,151,1) 46.2%, rgba(186,8,181,1) 90.1% );;
        color: honeydew;
        box-shadow:  2px 2px 5px rgba(250, 38, 151, 0.466),
                -2px -2px 5px rgba(186, 8, 180, 0.438);
        img{
            width: 30px;
        }
        span{
            padding:5px 2px;
            font-size: 15px;
        }
        &:hover{
        background-image: radial-gradient( circle farthest-corner at 10.2% 55.8%,  rgb(207, 32, 85) 0%, rgb(197, 34, 121) 46.2%, rgba(148, 48, 145, 0.934) 90.1% );;
        }
    }
    .actions {
        position: relative;
        padding: 20px 10px;
        display: flex;
        flex-direction: row;
        button {
            padding: 5px 10px;
            border-radius: 4px;
            background-color: white;
            border: 1px solid #dad8d7;
            margin-bottom: 5px;
            cursor: pointer;
            &:hover {
                background-color: #f8f8f8;
            }
        }
    }
    .print{
        color: rgb(198, 38, 97);
        margin-left: 20px;
        border-radius: 5px;
        display: flex;
        
        span{
            padding:5px 2px;
            font-size: 15px;
        }
    }
}
@page {
    size: auto;
    margin: 0cm;
    color: #ffffff;
    // -webkit-print-color-adjust: exact;
    // print-color-adjust: exact;
}
@media print {
    html,
    body,
    #app {
        font-size: 0 !important;
        min-height: auto !important;
        height: auto !important;
        // min-width: auto !important;
        // font-family: Microsoft YaHei, tahoma, arial, Hiragino Sans GB;
    }
    * {
        color: #000 !important;
        overflow: hidden !important;
    }
    .resume {
        // position: absolute;
        // top: 0;
        // left: 0;
        // width: 100%;
        margin-top: 0!important;
        // border: none!important;
    }
    .actions, .guide, .footer {
        display: none!important;
    }
}
</style>

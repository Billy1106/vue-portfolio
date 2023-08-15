<template>
     <v-app id="home">
        <NavBar/>
        <v-container fluid>
            <div class="head">
                <v-row>
                    <v-col cols="5">
                        <div style="position: relative;" class="mt-16">
                            <h1 class="text-black text-h3 font-weight-bold">Hello,</h1>
                            <h1 class="text-black text-h2 font-weight-bold">I'm Ryota Koda</h1>
                            <p class="mt-2 text-black text-h5">Software Developer</p>
                            <v-btn tile dark class="text-black mt-8" variant="outlined">Contact me</v-btn>
                        </div>
                    </v-col>
                    <v-col cols="2">
                        <div style="position: absolute;bottom:0;margin-left:auto;margin-right:auto;left:0;right:0;text-align: center">
                            <v-icon>fas fa-angle-double-down</v-icon>
                        </div>
                    </v-col>
                    <v-col cols="5">
                        <div style="position: relative;z-index:9999;" class="mt-16">
                            <v-img src="AI-profile.png" contain max-height="300"/>
                        </div>
                    </v-col>
                </v-row>
            </div>
            <v-col cols="12" class="mt-16" id="about" >
                <div>
                    <v-row>
                        <v-col cols="12" sm="6">
                            <div class="egg">
                                <v-img src="AI-profile.png" max-height="300" style="margin-right:50px"></v-img>
                            </div>
                        </v-col>
                        <v-col cols="12" sm="6">
                            <h5 class="mt-16">About Me</h5>
                            <div style="width: 120px">
                                <v-slider v-model="slider2" color="black">
                                    
                                </v-slider>
                            </div>
                            <h4 class="mt-n4">Something about myself</h4>
                            <p class="text-grey">I'm a Japanese Software Engineer based in Vancouver.I'm currently a senior Computer Science student at The University of British Columbia (UBC) and anticipated to graduate in May, 2024, looking for internship with passions in software engineering and solving problems.</p>
                            <br />
                            <p class="text-grey">Here are a Few Highlights:
                                <ul>
                                    <li>
                                        Well-Organized person, problem solver with high attention to detail
                                    </li>
                                    <li>
                                        Fan of Soccer, outdoor activities, games and Japanese pop culture
                                    </li>
                                    <li>
                                        High proficiency in English, Japanese, and elementary proficiency in Chinese and Korean
                                    </li>
                                </ul>
                            </p>
                            <v-btn tile dark color="black" class="mt-4">
                                Download Resume
                            </v-btn>
                        </v-col>
                    </v-row>
                </div>
            </v-col>
            <div class="text-center mt-4">
                <h2>What we do</h2>
                <div style="width: 120px; margin: 0 auto">
                    <v-slider v-model="slider" color="black"></v-slider>
                </div>
            </div> 
            <v-col cols="12" class="padd" id="portfolio">
                <div class="first" id="project">
                    <v-row>
                        <v-col cols="12">
                            <div class="child">
                                <v-btn icon="fas fa-laptop" color="#BEBDB8" class="text-white"></v-btn>
                                <h3 class="ml-3 mt-4">Web Design</h3>
                                <p class="text-grey ml-3 mt-4 text-caption">
                                    asdasdas asd as fasf asd asd
                                </p>
                            </div>
                            <div class="child">
                                <v-btn icon="fas fa-mobile-alt" color="#BEBDB8" class="text-white"></v-btn>
                                <h3 class="ml-3 mt-4">Web Design</h3>
                                <p class="text-grey ml-3 mt-4 text-caption">
                                    asdasdas asd as fasf asd asd
                                </p>
                            </div>
                            <div class="child">
                                <v-btn icon="fas fa-camera" color="#BEBDB8" class="text-white"></v-btn>
                                <h3 class="ml-3 mt-4">Web Design</h3>
                                <p class="text-grey ml-3 mt-4 text-caption">
                                    asdasdas asd as fasf asd asd
                                </p>
                            </div>
                        </v-col>
                        <v-divider></v-divider>
                        <v-col cols="12" sm="12" id="services">
                            <v-btn color="#BEBDB8" class="mr-2">All</v-btn>
                            <v-btn color="#BEBDB8" class="mr-2">Web Design</v-btn>
                            <v-btn color="#BEBDB8" class="mr-2">Web Design</v-btn>
                            <v-btn color="#BEBDB8" class="mr-2">Web Design</v-btn>
                            <v-btn variant="tonal">Illustration</v-btn>
                        </v-col>
                    </v-row>
                </div>
            </v-col>
            <v-col cols="12" class="imgHover">
                <v-row class="fill-height" align="center" justify="center">
                    <template v-for="(item,i) in items" :key="i" >
                        <v-col cols="12" md="4">
                            <v-hover v-slot="{isHovering, props}">
                                <v-card :elevation="isHovering ? 12: 2" :class="{'on-hover': IsHovering}" v-bind="props">
                                    <v-icon height="225px">fas fa-angle-double-down</v-icon>
                                </v-card>
                            </v-hover>
                        </v-col>
                    </template>
                </v-row>
            </v-col>
            <v-col cols="12" sm="12">
                <div class="d-flex justify-center mb-6">
                    <v-btn color="#BEBDB8" class="mt-4">Load more</v-btn>
                </div>
            </v-col>
            <v-col cols="12" id="history">
                <div class="d-flex justify-center mb-6 history" style="padding-top:20px;padding-bottom:20px">
                    <v-row class="fill-height" align="center" justify="center">
                        <h1>History</h1>
                        <v-timeline align="start">
                            <v-timeline-item v-for="(data) in myHistory" :key="data.id" dot-color="transparent" :icon="data.icon">
                            <v-hover v-slot="{isHovering, props}">
                                <v-card :elevation="isHovering ? 12: 2" :class="{'on-hover': IsHovering}" v-bind="props" class="timeline">
                                    <h3>{{data.organization}}</h3>
                                    <span class="text-subtitle-1">{{data.position}}</span>
                                    <span class="font-weight-light font-italic text-subtitle-2" style="text-align:right;">({{data.date}})</span>
                                    <p style="margin:10px 10px 10px 10px;text-align:left;">{{data.description}}</p>
                                </v-card>
                            </v-hover>
                            </v-timeline-item>
                        
                        </v-timeline>
                    </v-row>
                </div>
            </v-col>
            <v-col cols="12" sm="12" class="px-16" id="contact">
                <v-row>
                    <v-col cols="12" sm="4">
                        <div class="child">
                            <h1>Contact Info.</h1>
                            <v-btn icon="fas fa-map-marker-alt" class="mt-10" variant="outlined"></v-btn><br/>
                            <span class="text-caption">Tokyo, Japan</span><br/>
                            <span class="text-caption">Vancouver, Canada</span><br/>
                            <v-btn icon="fas fa-envelope" class="mt-10" variant="outlined"></v-btn><br/>
                            <span class="text-caption">ryotabilly@gmail.com</span>
                        </div>
                    </v-col>
                    <v-col cols="12" sm="8">
                        <h1 class="mt-8">Send your message</h1>
                        <v-divider> </v-divider>
                        <span class="text-caption">
                            If you are Interested in my profile, please contact me.
                        </span>
                        <v-row class="mt-10">
                            <v-col cols="12" sm="6">
                                <v-text-field label="Name" persistent-hint variant="outlined"></v-text-field>
                            </v-col>
                            <v-col cols="12" sm="6">
                                <v-text-field label="Email" persistent-hint variant="outlined"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-textarea label="Message" persistent-hint variant="outlined"></v-textarea>
                        <v-btn color="#BEBDB8" class="mt-2">Submit Now</v-btn>
                    </v-col>
                </v-row>
            </v-col>
        </v-container>
        <FooterView />
     </v-app>
</template>

<script>
import { defineComponent } from 'vue';
import NavBar from '@/components/NavBar.vue'
import FooterView from '@/components/FooterView.vue'
import {myHistory} from '@/assets/strings.js'

export default defineComponent({
    name: 'HomeView',
    setup() {
        return {
            slider2: 50,
            items : {
                img1: "",
                img2: "",
                img3: "",
                img4: "",
                img5: "",
                img6: "",
                img7: "",
            },
            myHistory
        }
    },
    components: {
        NavBar,
        FooterView
    }
})
</script>

<style scoped>
.v-container {
    padding: 16px 0;
}
.head {
    position: relative;
    text-align: center;
    padding: 12px;
    margin-bottom: 6px;
    height: 400px;
    width: 100%;
    color: white;
}
.head:before {
    content: " ";
    position: absolute;
    top:0;
    left: 0;
    height: 100%;
    width: 50%;
    background: #BEBDB8;
    transform: skew(0deg, 6deg)
}
.head:after {
    content: " ";
    position: absolute;
    top:0;
    right: 0;
    height: 100%;
    width: 50%;
    background: #BEBDB8;
    transform: skew(0deg, -6deg)
}

.egg {
    display: block;
    margin-left: 130px;
    margin-top:50px;
    width: 380px;
    height: 300px;
    background-color: #BEBDB8;
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 0%
}

.first {
    width: 100%;
    height: 280px;
    text-align: center;
    padding: 2rem 2rem;
}
.child {
    display: inline-block;
    padding: 2rem 1rem;
    vertical-align:middle;
    text-align:center;
    margin-right: 8px
}
.imgHover{
    padding: 0 200px;

}
.pre {
    width: 100%;
    height: 380px;
    text-align: center;
    padding: 0 200px;
    background-color: #f5f5f5;
}
.history {
    text-align: center;
    width: 100%;
    padding: 0 200px;
    background-color: #f5f5f5;
    margin-top: -24px
}
.timeline{
    width:80%;
    background-color:white;
    padding: 10px 10px 10px 10px;
    border-radius:10px;
}

</style>
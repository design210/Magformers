
<template>
    <div id="app">
        <div v-for="post in posts" :key="post.id">
        <div class="warning_tt">
            <h2 v-bind:class="selected">{{ post.txt25 }}</h2>								
        </div>
         <select v-model="selected" id="select">
            <option v-for="option in options" v-bind:value="option.value" :key="option.value">
                {{ option.text }}
            </option>
        </select>        
        <div class="clear"></div>  
            <div class="wan_title">
                <div v-bind:class="selected">
                    <span v-html="post.title">{{ post.title | nl2br }}</span>
                </div>
            </div>
            <div class="wan_img_area">
                <ul v-bind:class="selected">
                    <li>
                        <div><img src="../src/assets/wan01.jpg" /></div>
                        <div>
                            <span v-html="post.txt01">{{ post.txt01 | nl2br }}</span>                  
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan02.jpg" /></div>
                        <div>
                            <span v-html="post.txt02">{{ post.txt02 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan03.jpg" /></div>
                        <div>
                            <span v-html="post.txt03">{{ post.txt03 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan04.jpg" /></div>
                        <div>
                            <span v-html="post.txt04">{{ post.txt04 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan05.jpg" /></div>
                        <div>
                           <span v-html="post.txt05">{{ post.txt05 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan06.jpg" /></div>
                        <div>
                            <span v-html="post.txt06">{{ post.txt06 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan07.jpg" /></div>
                        <div>
                            <span v-html="post.txt07">{{ post.txt07 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan08.jpg" /></div>
                        <div>
                            <span v-html="post.txt08">{{ post.txt08 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan09.jpg" /></div>
                        <div>
                            <span v-html="post.txt09">{{ post.txt09 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan10.jpg" /></div>
                        <div>
                            <span v-html="post.txt10">{{ post.txt10 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan11.jpg" /></div>
                        <div>
                            <span v-html="post.txt11">{{ post.txt11 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan12.jpg" /></div>
                        <div>
                            <span v-html="post.txt12">{{ post.txt12 }}</span> 
                        </div>
                    </li>
                </ul>
            </div>
            <div class="wan_list">
                <ul v-bind:class="selected">
                    <li>
                        <span v-html="post.txt13">{{ post.txt13 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt14">{{ post.txt14 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt15">{{ post.txt15 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt16">{{ post.txt16 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt17">{{ post.txt17 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt18">{{ post.txt18 }}</span> 
                    </li>
                    <li>
                       <span v-html="post.txt19">{{ post.txt19 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt20">{{ post.txt20 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt21">{{ post.txt21 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt22">{{ post.txt22 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt23">{{ post.txt23 }}</span> 
                    </li>
                    <li>
                        <span v-html="post.txt24">{{ post.txt24 }}</span> 
                    </li>                   
                </ul>
            </div>   
                    
            <div class="wan_box">
                <div class="wan_box01">
                    <div v-bind:class="selected">                    
                        <span class="svg"><img src="/dist/ic_warning.svg"></span><span class="svg_title" v-html="post.txt25">{{ post.txt25 }}</span>
                    </div> 
                </div>
                <div class="wan_box03">
                    <div v-bind:class="selected"> 
                        <span v-html="post.txt26">{{ post.txt26 }}</span> 
                    </div>
                </div>
            </div> 
        </div>
    </div>
</template>

<script>
import axios from 'axios';


export default {
  data() {
    return {
        posts: [],
        errors: [],
        selected: 'English',
        options: [
            { text: 'English', value: 'English' },
            { text: 'Afrikaans', value: 'Afrikaans' },
            { text: 'Bahasa Indonesia', value: 'Indonesia' },
            { text: 'Català', value: 'Catal' },
            { text: 'Čeština', value: 'cestina' },
            { text: 'Dansk', value: 'Dansk' },
            { text: 'Deutsch', value: 'Deutsch' },
            { text: 'Eesti', value: 'Eesti' },
            { text: 'Español', value: 'Espanol' },
            { text: 'Íslenska', value: 'islenska' },
            { text: 'Polski', value: 'Polski' },
            { text: 'Latviešu', value: 'Latviesu' },
            { text: 'Français', value: 'Francais' },
            { text: 'Lietuvių kalba', value: 'Lietuviu' },
            { text: 'Italiano', value: 'Italiano' },
            { text: 'Magyar', value: 'Magyar' },
            { text: 'Nederlands', value: 'Nederlands' },
            { text: 'Norsk', value: 'Norsk' },
            { text: 'Português', value: 'Portugues' },
            { text: 'Slovenčina', value: 'Slovencina' },
            { text: 'Suomi', value: 'Suomi' },
            { text: 'Svenska', value: 'Svenska' },
            { text: 'iếng Việt', value: 'Viet' },
            { text: 'Монгол', value: 'Mongo' },
            { text: 'Русский', value: 'Russia' },
            { text: 'Українська мова', value: 'Ukraina' },
            { text: 'עברית', value: 'Hibri' },
            { text: 'ภาษาไทย', value: 'Tai' },
            { text: '日本語', value: 'Japanese' },
            { text: '中文(繁體)', value: 'Chaina1' },
            { text: '中文(简体)', value: 'Chaina2' },
            { text: '한국어', value: 'Korean' }
        ]
    }
  },   
  created() {
    axios({
        meghod: 'get',
        url: '/json/language.asp?TP=English'
    })
    .then(response => {       
        this.posts = response.data;       
        //this.posts[0].title=this.posts[0].title.replace(/(?:\r\n|\r|\n)/g, '<br />');       
    })
    .catch(e => {
        this.errors.push(e)
    });    
  },
  filters: {      
     nl2br (value) {
      return value.replace(/(?:\r\n|\r|\n)/g, '<br />');
    }
  },
  watch:{
    selected: function(data){
       axios.get('/json/language.asp?TP='+data)
        .then(response => {
            this.posts = response.data;
            
        })
        .catch(e => {
            this.errors.push(e)
        });
    }
  }
}



</script>


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
                    <nl2br tag="span" :text=post.title />
                </div>
            </div>
            <div class="wan_img_area">
                <ul v-bind:class="selected">
                    <li>
                        <div><img src="../src/assets/wan01.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt01 />                
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan02.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt02 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan03.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt03 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan04.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt04 />  
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan05.jpg" /></div>
                        <div>
                           <nl2br tag="span" :text=post.txt05 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan06.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt06 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan07.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt07 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan08.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt08 />  
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan09.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt09 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan10.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt10 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan11.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt11 /> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan12.jpg" /></div>
                        <div>
                            <nl2br tag="span" :text=post.txt12 /> 
                        </div>
                    </li>
                </ul>
            </div>
            <div class="wan_list">
                <ul v-bind:class="selected">
                    <li>
                        <nl2br tag="span" :text=post.txt13 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt14 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt15 /> 
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt16 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt17 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt18 />  
                    </li>
                    <li>
                       <nl2br tag="span" :text=post.txt19 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt20 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt21 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt22 /> 
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt23 />  
                    </li>
                    <li>
                        <nl2br tag="span" :text=post.txt24 /> 
                    </li>                   
                </ul>
            </div>   
                    
            <div class="wan_box">
                <div class="wan_box01">
                    <div v-bind:class="selected">                    
                        <span class="svg"><img src="/dist/ic_warning.svg"></span><nl2br  tag="span" :text=post.txt25 />
                    </div> 
                </div>
                <div class="wan_box03">
                    <div v-bind:class="selected"> 
                        <nl2br tag="span" :text=post.txt26 /> 
                    </div>
                </div>
            </div> 
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Nl2br from 'vue-nl2br';


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
    })
    .catch(e => {
        this.errors.push(e)
    });    
  },
  components:{
      'nl2br': Nl2br
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

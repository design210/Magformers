
<template>
    <div id="app">
        <div v-for="post in posts" :key="post.id">
        <div class="warning_tt">
            <h2>{{ post.txt25 }}</h2>								
        </div>        
        <div class="clear"></div>        
            <div class="wan_title">
                <span>{{ post.title }}</span>
            </div>
            <div class="wan_img_area">
                <ul>
                    <li>
                        <div><img src="../src/assets/wan01.jpg" /></div>
                        <div>
                            <span>{{ post.txt01 }}</span>                  
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan02.jpg" /></div>
                        <div>
                            <span>{{ post.txt02 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan03.jpg" /></div>
                        <div>
                            <span>{{ post.txt03 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan04.jpg" /></div>
                        <div>
                            <span>{{ post.txt04 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan05.jpg" /></div>
                        <div>
                           <span>{{ post.txt05 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan06.jpg" /></div>
                        <div>
                            <span>{{ post.txt06 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan07.jpg" /></div>
                        <div>
                            <span>{{ post.txt07 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan08.jpg" /></div>
                        <div>
                            <span>{{ post.txt08 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan09.jpg" /></div>
                        <div>
                            <span>{{ post.txt09 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan10.jpg" /></div>
                        <div>
                            <span>{{ post.txt10 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan11.jpg" /></div>
                        <div>
                            <span>{{ post.txt11 }}</span> 
                        </div>
                    </li>
                    <li>
                        <div><img src="../src/assets/wan12.jpg" /></div>
                        <div>
                            <span>{{ post.txt12 }}</span> 
                        </div>
                    </li>
                </ul>
            </div>
            <div class="wan_list">
                <ul>
                    <li>
                        <span>{{ post.txt13 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt14 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt15 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt16 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt17 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt18 }}</span> 
                    </li>
                    <li>
                       <span>{{ post.txt19 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt20 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt21 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt22 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt23 }}</span> 
                    </li>
                    <li>
                        <span>{{ post.txt24 }}</span> 
                    </li>                   
                </ul>
            </div>   
                    
            <div class="wan_box">
                <div class="wan_box01">                    
                    <span class="svg"><img src="/dist/ic_warning.svg"></span><span class="svg_title">{{ post.txt25 }}</span> 
                </div>
                <div class="wan_box03">
                    <span>{{ post.txt26 }}</span> 
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
        selected: 'English'
    }
  },
  created() {
    axios.get('/json/language.asp?TP=English')
    //axios.get('http://jsonplaceholder.typicode.com/posts')
    .then(response => {
        // JSON responses are automatically parsed.
        this.posts = response.data;
        
    })
    .catch(e => {
        this.errors.push(e)
    });    
  },
  watch:{
    selected: function(data){
       axios.get('/json/language.asp?TP='+data)
        //axios.get('http://jsonplaceholder.typicode.com/posts')
        .then(response => {
            // JSON responses are automatically parsed.
            this.posts = response.data;
            
        })
        .catch(e => {
            this.errors.push(e)
        });
    }
  }
}



</script>

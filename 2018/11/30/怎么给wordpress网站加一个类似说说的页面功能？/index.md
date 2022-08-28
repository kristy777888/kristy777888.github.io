# 

有的时候，想在自己的网站发布一些心情，或者，发布一些字数较少的内容，编辑成文章的话，既不美观也不方便，那么，就可以添加一个类似qq空间说说、或者新浪微博功能的页面，来弥补这一缺憾。

说说功能是什么样子的呢，直接上图，请看下方的效果图：

&nbsp;

<figure id="attachment_599" aria-describedby="caption-attachment-599" style="width: 863px" class="wp-caption aligncenter">[<img loading="lazy" class=" wp-image-599" src="http://www.zhangliguo.com/wp-content/uploads/2018/11/111111.jpg" alt="说说效果图" width="863" height="466" />]()<figcaption id="caption-attachment-599" class="wp-caption-text">说说效果图</figcaption></figure>

# 下面直接讲解，wordpress添加说说页面功能的实际操作方法步骤：

要想实现说说发布的功能，需要三个文件，新建shuoshuo.php，shuoshuo.css和修改当前主题functions.php（有的主题模块中可能是functions-theme.php）。

<div class="dp-highlighter">
  <h3 class="bar">
    functions.php文件里面添加如下代码：
  </h3>
  
  <div class="dp-highlighter collapsed">
    <div class="bar">
    </div>
    
    <ol class="dp-c" start="1">
      <li class="alt">
        /说说
      </li>
      <li class="">
         add_action(&#8216;init&#8217;, &#8216;my_custom_init&#8217;);
      </li>
      <li class="alt">
         <span class="keyword">function</span> my_custom_init()
      </li>
      <li class="">
         { <span class="vars">$labels</span> = <span class="keyword">array</span>( &#8216;name&#8217; => &#8216;说说&#8217;,
      </li>
      <li class="alt">
         &#8216;singular_name&#8217; => &#8216;singularname&#8217;,
      </li>
      <li class="">
         &#8216;add_new&#8217; => &#8216;发表说说&#8217;,
      </li>
      <li class="alt">
         &#8216;add_new_item&#8217; => &#8216;发表说说&#8217;,
      </li>
      <li class="">
         &#8216;edit_item&#8217; => &#8216;编辑说说&#8217;,
      </li>
      <li class="alt">
         &#8216;new_item&#8217; => &#8216;新说说&#8217;,
      </li>
      <li class="">
         &#8216;view_item&#8217; => &#8216;查看说说&#8217;,
      </li>
      <li class="alt">
         &#8216;search_items&#8217; => &#8216;搜索说说&#8217;,
      </li>
      <li class="">
         &#8216;not_found&#8217; => &#8216;暂无说说&#8217;,
      </li>
      <li class="alt">
         &#8216;not_found_in_trash&#8217; =>  &#8216;没有已遗弃的说说&#8217;,
      </li>
      <li class="">
         &#8216;parent_item_colon&#8217; => <span class="string">&#8221;</span>,
      </li>
      <li class="alt">
         &#8216;menu_name&#8217; => &#8216;说说&#8217; );
      </li>
      <li class="">
         <span class="vars">$args</span> = <span class="keyword">array</span>( &#8216;labels&#8217; => <span class="vars">$labels</span>,
      </li>
      <li class="alt">
         &#8216;<span class="keyword">public</span>&#8216; => true,
      </li>
      <li class="">
         &#8216;publicly_queryable&#8217; => true,
      </li>
      <li class="alt">
         &#8216;show_ui&#8217; => true,
      </li>
      <li class="">
         &#8216;show_in_menu&#8217; => true,
      </li>
      <li class="alt">
         &#8216;query_var&#8217; => true,
      </li>
      <li class="">
         &#8216;rewrite&#8217; => true,
      </li>
      <li class="alt">
         &#8216;capability_type&#8217; => &#8216;post&#8217;,
      </li>
      <li class="">
         &#8216;has_archive&#8217; => true, &#8216;hierarchical&#8217; => false,
      </li>
      <li class="alt">
         &#8216;menu_position&#8217; => null,
      </li>
      <li class="">
         &#8216;supports&#8217; => <span class="keyword">array</span>(&#8216;title&#8217;,&#8217;editor&#8217;,&#8217;author&#8217;) );
      </li>
      <li class="alt">
         register_post_type(&#8216;shuoshuo&#8217;,<span class="vars">$args</span>); }
      </li>
    </ol>
  </div>
  
  <h3>
    在你的网站主题根目录新建shuoshuo.php添加如下代码：
  </h3>
  
  <div class="dp-highlighter collapsed">
    <div class="bar">
    </div>
    
    <ol class="dp-c" start="1">
      <li class="alt">
        <?php
      </li>
      <li class="">
        get_header(); ?>
      </li>
      <li class="alt">
        <link href=<span class="string">&#8220;/wp-content/themes/xxxx/shuoshuo.css&#8221;</span> rel=<span class="string">&#8220;stylesheet&#8221;</span>>
      </li>
      <li class="">
        <div <span class="keyword">class</span>=<span class="string">&#8220;shuoshuo&#8221;</span>>
      </li>
      <li class="alt">
         <ul <span class="keyword">class</span>=<span class="string">&#8220;archives-monthlisting&#8221;</span>>
      </li>
      <li class="">
         <?php query_posts(<span class="string">&#8220;post_type=shuoshuo&post_status=publish&posts_per_page=-1&#8221;</span>);<span class="keyword">if</span> (have_posts()) : <span class="keyword">while</span> (have_posts()) : the_post(); ?>
      </li>
      <li class="alt">
         <li><span <span class="keyword">class</span>=<span class="string">&#8220;tt&#8221;</span>><?php the_time(&#8216;Y年n月j日G:i&#8217;); ?></span>
      </li>
      <li class="">
         <div <span class="keyword">class</span>=<span class="string">&#8220;shuoshuo-content&#8221;</span>><?php the_content(); ?><br/><div <span class="keyword">class</span>=<span class="string">&#8220;shuoshuo-meta&#8221;</span>><span >—<?php the_author() ?></span></div></div><?php <span class="keyword">endwhile</span>;<span class="keyword">endif</span>; ?></li>
      </li>
      <li class="alt">
         </ul>
      </li>
      <li class="">
        </div>
      </li>
      <li class="alt">
        <?php get_footer();?>
      </li>
    </ol>
  </div>
  
  <h3>
    然后新建shuoshuo.css的样式文件，在当前主题根目录或者是主题目录css文件夹里面，对应的路径要在上方的代码xxxx处修改一下，修改的路径就是你把shuoshuo.css放置的路径。
  </h3>
  
  <div class="dp-highlighter collapsed">
    <div class="bar">
    </div>
    
    <ol class="dp-css" start="1">
      <li class="alt">
        .shuoshuo {
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">relative</span>;
      </li>
      <li class="alt">
        <span class="keyword">margin</span>: <span class="string">50px</span> 0;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo li {
      </li>
      <li class="">
        <span class="keyword">padding</span>: <span class="string">8px</span> 0;
      </li>
      <li class="alt">
        <span class="keyword">display</span>: <span class="string">block</span>;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span> {
      </li>
      <li class="">
        box-shadow: 0 0 <span class="string">3px</span> RGBA(0,0,0,.15);
      </li>
      <li class="alt">
        <span class="keyword">background-color</span>: <span class="colors">#f8f8f8</span>;
      </li>
      <li class="">
        <span class="keyword">border</span>:<span class="string">1px</span> <span class="colors">#eee</span> <span class="string">solid</span>;
      </li>
      <li class="alt">
        <span class="keyword">border</span>-radius: <span class="string">4px</span>;
      </li>
      <li class="">
        <span class="keyword">font-size</span>: 1em;
      </li>
      <li class="alt">
        <span class="keyword">line-height</span>:2.3em;
      </li>
      <li class="">
        <span class="keyword">margin</span>:0 <span class="string">150px</span> 0 <span class="string">200px</span>;
      </li>
      <li class="alt">
        <span class="keyword">letter-spacing</span>: <span class="string">1px</span>;
      </li>
      <li class="">
        <span class="keyword">padding</span>: <span class="string">20px</span> <span class="string">20px</span> <span class="string">5px</span> <span class="string">30px</span>;
      </li>
      <li class="alt">
        <span class="keyword">color</span>: <span class="colors">#666</span>;
      </li>
      <li class="">
        <span class="keyword">min-height</span>:<span class="string">60px</span>;
      </li>
      <li class="alt">
        <span class="keyword">position</span>: <span class="string">relative</span>;
      </li>
      <li class="">
         <span class="string">white</span><span class="keyword">white-space</span>: <span class="string">pre</span>; <span class="comment">/* CSS 2.0 */</span>
      </li>
      <li class="alt">
         <span class="string">white</span><span class="keyword">white-space</span>: <span class="string">pre</span>-wrap; <span class="comment">/* CSS 2.1 */</span>
      </li>
      <li class="">
         <span class="string">white</span><span class="keyword">white-space</span>: <span class="string">pre</span>-line; <span class="comment">/* CSS 3.0 */</span>
      </li>
      <li class="alt">
         <span class="string">white</span><span class="keyword">white-space</span>: &#8211;<span class="string">pre</span>-wrap; <span class="comment">/* Opera 4-6 */</span>
      </li>
      <li class="">
         <span class="string">white</span><span class="keyword">white-space</span>: -o-<span class="string">pre</span>-wrap; <span class="comment">/* Opera 7 */</span>
      </li>
      <li class="alt">
         <span class="string">white</span><span class="keyword">white-space</span>: -moz-<span class="string">pre</span>-wrap; <span class="comment">/* Mozilla */</span>
      </li>
      <li class="">
         <span class="string">white</span><span class="keyword">white-space</span>: -hp-<span class="string">pre</span>-wrap; <span class="comment">/* HP Printers */</span>
      </li>
      <li class="alt">
         word-wrap: break-word; <span class="comment">/* IE 5+,  */</span>
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span> p{<span class="keyword">margin</span>:0;}
      </li>
      <li class="">
        <span class="comment">/**/</span>
      </li>
      <li class="alt">
        .shuoshuo-meta {
      </li>
      <li class="">
        <span class="keyword">text-align</span>: <span class="keyword">right</span><span class="string">right</span>;
      </li>
      <li class="alt">
        <span class="keyword">letter-spacing</span>: <span class="string">0px</span>;
      </li>
      <li class="">
        <span class="keyword">margin-top</span>:-<span class="string">85px</span>;
      </li>
      <li class="alt">
        }
      </li>
      <li class="">
        .toolbar{<span class="keyword">display</span>:<span class="string">none</span>}
      </li>
      <li class="alt">
        <span class="comment">/**/</span>
      </li>
      <li class="">
        <span class="comment">/*.shuoshuo .tt{margin: 35px 0 0 15px;float:left;font-size:0.9em;}*/</span>
      </li>
      <li class="alt">
        <span class="comment">/*.shuoshuo li em{float:left;background:url(&#8220;//www.100day.cc/wp-content/themes/frontopen2_v1.5.04.15/images/bolangxian.png&#8221;) no-repeat;width:50px;height:10px;margin:42px 0 0 28px;}*/</span>
      </li>
      <li class="">
        <span class="comment">/*.shuoshuo li:hover .tt {color:#0c0;font-weight:bold;} */</span>
      </li>
      <li class="alt">
        <span class="comment">/**/</span>
      </li>
      <li class="">
        .shuoshuo .zhutou{<span class="keyword">border</span>-radius: 50%;<span class="keyword">margin</span>: <span class="string">25px</span> <span class="string">35px</span> 0 <span class="string">5px</span>;<span class="keyword">float</span>:<span class="keyword">right</span><span class="string">right</span>;<span class="keyword">padding</span>: <span class="string">2px</span>;<span class="keyword">border</span>: <span class="string">1px</span> <span class="colors">#ddd</span> <span class="string">solid</span>;<span class="keyword">display</span>: <span class="string">block</span>;transition: .5s;<span class="keyword">width</span>: <span class="string">40px</span>;<span class="keyword">height</span>: <span class="string">40px</span>;<span class="keyword">overflow</span>:<span class="string">hidden</span>;}
      </li>
      <li class="alt">
        .shuoshuo li:hover .zhutou {
      </li>
      <li class="">
        transform: rotate(720deg);-webkit-transform: rotate(720deg);-moz-transform: rotate(720deg);<span class="keyword">border-color</span>: <span class="colors">#0c0</span>;}
      </li>
      <li class="alt">
        <span class="comment">/**/</span>
      </li>
      <li class="">
        .shuoshuo:before {
      </li>
      <li class="alt">
        <span class="keyword">height</span>: 100%;
      </li>
      <li class="">
        <span class="keyword">width</span>: <span class="string">2px</span>;
      </li>
      <li class="alt">
        <span class="keyword">background</span>: <span class="colors">#eee</span>;
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="alt">
        <span class="string">left</span>: <span class="string">164px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        <span class="string">top</span>:<span class="string">0px</span>;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span>:before {
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="alt">
        <span class="string">top</span>: <span class="string">40px</span>;
      </li>
      <li class="">
        <span class="keyword">bottom</span><span class="string">bottom</span>: <span class="string">0px</span>;
      </li>
      <li class="alt">
        <span class="string">left</span>: &#8211;<span class="string">42px</span>;
      </li>
      <li class="">
        <span class="keyword">background</span>: <span class="colors">#fff</span>;
      </li>
      <li class="alt">
        <span class="keyword">height</span>: <span class="string">12px</span>;
      </li>
      <li class="">
        <span class="keyword">width</span>: <span class="string">12px</span>;
      </li>
      <li class="alt">
        <span class="keyword">border</span>-radius: <span class="string">6px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        box-shadow: <span class="string">inset</span> 0 0 <span class="string">2px</span> <span class="colors">#0c0</span>;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span>:after {
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="alt">
        <span class="string">top</span>: <span class="string">42px</span>;
      </li>
      <li class="">
        <span class="keyword">bottom</span><span class="string">bottom</span>: <span class="string">0px</span>;
      </li>
      <li class="alt">
        <span class="string">left</span>: &#8211;<span class="string">40px</span>;
      </li>
      <li class="">
        <span class="keyword">background</span>: <span class="colors">#ccc</span>;
      </li>
      <li class="alt">
        <span class="keyword">height</span>: <span class="string">8px</span>;
      </li>
      <li class="">
        <span class="keyword">width</span>: <span class="string">8px</span>;
      </li>
      <li class="alt">
        <span class="keyword">border</span>-radius: <span class="string">6px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        }
      </li>
      <li class="">
        .shuoshuo li:hover .shuoshuo-<span class="keyword">content</span>:after {
      </li>
      <li class="alt">
        <span class="keyword">background</span>: <span class="colors">#0c0</span>;
      </li>
      <li class="">
        -webkit-transform: scale(1.3);
      </li>
      <li class="alt">
        -moz-transform: scale(1.3);
      </li>
      <li class="">
        -ms-transform: scale(1.3);
      </li>
      <li class="alt">
        -o-transform: scale(1.3);
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo li:hover .shuoshuo-<span class="keyword">content</span>:before {-webkit-transform: scale(1.3);
      </li>
      <li class="">
        -moz-transform: scale(1.3);
      </li>
      <li class="alt">
        -ms-transform: scale(1.3);
      </li>
      <li class="">
        -o-transform: scale(1.3);}
      </li>
      <li class="alt">
        <span class="comment">/**/</span>
      </li>
      <li class="">
        .shuoshuo:after {
      </li>
      <li class="alt">
        <span class="keyword">height</span>: 100%;
      </li>
      <li class="">
        <span class="keyword">width</span>: <span class="string">2px</span>;
      </li>
      <li class="alt">
        <span class="keyword">background</span>: <span class="colors">#eee</span>;
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="alt">
        <span class="keyword">right</span><span class="string">right</span>: <span class="string">100px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        <span class="string">top</span>:<span class="string">0px</span>;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        .shuoshuo-meta:before {
      </li>
      <li class="">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="alt">
        <span class="string">top</span>: <span class="string">42px</span>;
      </li>
      <li class="">
        <span class="keyword">bottom</span><span class="string">bottom</span>: <span class="string">0px</span>;
      </li>
      <li class="alt">
        <span class="keyword">right</span><span class="string">right</span>: &#8211;<span class="string">56px</span>;
      </li>
      <li class="">
        <span class="keyword">background</span>: <span class="colors">#fff</span>;
      </li>
      <li class="alt">
        <span class="keyword">height</span>: <span class="string">12px</span>;
      </li>
      <li class="">
        <span class="keyword">width</span>: <span class="string">12px</span>;
      </li>
      <li class="alt">
        <span class="keyword">border</span>-radius: <span class="string">6px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        <span class="keyword">z-index</span>:2;
      </li>
      <li class="">
        box-shadow: <span class="string">inset</span> 0 0 <span class="string">2px</span> <span class="colors">#0c0</span>;
      </li>
      <li class="alt">
        }
      </li>
      <li class="">
        .shuoshuo-meta:after {
      </li>
      <li class="alt">
        <span class="keyword">position</span>: <span class="string">absolute</span>;
      </li>
      <li class="">
        <span class="string">top</span>: <span class="string">44px</span>;
      </li>
      <li class="alt">
        <span class="keyword">bottom</span><span class="string">bottom</span>: <span class="string">0px</span>;
      </li>
      <li class="">
        <span class="keyword">right</span><span class="string">right</span>: &#8211;<span class="string">54px</span>;
      </li>
      <li class="alt">
        <span class="keyword">background</span>: <span class="colors">#ccc</span>;
      </li>
      <li class="">
        <span class="keyword">height</span>: <span class="string">8px</span>;
      </li>
      <li class="alt">
        <span class="keyword">width</span>: <span class="string">8px</span>;
      </li>
      <li class="">
        <span class="keyword">z-index</span>:2;
      </li>
      <li class="alt">
        <span class="keyword">border</span>-radius: <span class="string">6px</span>;
      </li>
      <li class="">
        <span class="keyword">content</span>: <span class="string">&#8220;&#8221;</span>;
      </li>
      <li class="alt">
        }
      </li>
      <li class="">
        .shuoshuo li:hover .shuoshuo-meta:after {
      </li>
      <li class="alt">
        <span class="keyword">background</span>: <span class="colors">#0c0</span>;
      </li>
      <li class="">
        }
      </li>
      <li class="alt">
        @media <span class="string">screen</span> and (<span class="keyword">min-width</span>:<span class="string">1080px</span>){
      </li>
      <li class="">
        .shuoshuo{<span class="keyword">width</span>:<span class="string">1060px</span>;<span class="keyword">margin</span>:<span class="string">50px</span> <span class="string">auto</span>}
      </li>
      <li class="alt">
        }
      </li>
      <li class="">
        @media <span class="string">screen</span> and (<span class="keyword">max-width</span>: <span class="string">800px</span>) {
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span> {<span class="keyword">margin</span>:0 <span class="string">60px</span> 0 <span class="string">70px</span>;<span class="keyword">padding</span>: <span class="string">10px</span> <span class="string">10px</span> <span class="string">5px</span> <span class="string">10px</span>;<span class="keyword">font-size</span>:0.9em;}
      </li>
      <li class="">
        .shuoshuo .tt{<span class="keyword">width</span>:<span class="string">30px</span>;<span class="keyword">font-weight</span>:<span class="string">bold</span>;<span class="keyword">margin</span>: <span class="string">30px</span> 0 0 <span class="string">1px</span>;<span class="keyword">font-size</span>:0.5em;<span class="keyword">height</span>: <span class="string">20px</span>;}
      </li>
      <li class="alt">
        .shuoshuo li:hover .tt {<span class="keyword">color</span>:<span class="colors">#0c0</span>;<span class="keyword">font-size</span>:0.5em;}
      </li>
      <li class="">
        .shuoshuo:before {<span class="string">left</span>: <span class="string">50px</span>;}
      </li>
      <li class="alt">
        .shuoshuo-<span class="keyword">content</span>:before {<span class="string">left</span>: &#8211;<span class="string">26px</span>;<span class="string">top</span>:<span class="string">30px</span>;}
      </li>
      <li class="">
        .shuoshuo-<span class="keyword">content</span>:after {<span class="string">left</span>: &#8211;<span class="string">24px</span>;<span class="string">top</span>:<span class="string">32px</span>;}
      </li>
      <li class="alt">
      </li>
      <li class="">
        .shuoshuo:after {<span class="keyword">right</span><span class="string">right</span>: <span class="string">27px</span>;}
      </li>
      <li class="alt">
        .shuoshuo-meta:before {<span class="keyword">right</span><span class="string">right</span>: &#8211;<span class="string">39px</span>;<span class="string">top</span>:<span class="string">33px</span>;}
      </li>
      <li class="">
        .shuoshuo-meta:after {<span class="keyword">right</span><span class="string">right</span>: &#8211;<span class="string">37px</span>;<span class="string">top</span>:<span class="string">35px</span>;}
      </li>
      <li class="alt">
      </li>
      <li class="">
        .shuoshuo .zhutou{<span class="keyword">margin</span>: <span class="string">17px</span> <span class="string">5px</span> 0 <span class="string">5px</span>;}
      </li>
      <li class="alt">
        .shuoshuo li em{<span class="keyword">float</span>:<span class="string">left</span>;<span class="keyword">width</span>:<span class="string">39px</span>;<span class="keyword">height</span>:<span class="string">10px</span>;<span class="keyword">margin</span>:<span class="string">34px</span> 0 0 &#8211;<span class="string">1px</span>;}
      </li>
      <li class="">
        }
      </li>
    </ol>
    
    <h3>
      当三个文件都修改建立上传完毕，就可以在wordpress后台-分类目录-新建一个名称为我的说说的页面，然后模版选择说说，至此功能也就大体完成了。
    </h3>
    
    <p>
      <span style="color: #ff0000;">TIPs：</span>
    </p>
    
    <p>
      <span style="color: #ff0000;">新建文件可以在网站后台添加，如果添加不了可以用FTP，或者可以直接登陆服务器中修改。</span>
    </p>
    
    <p>
      最终效果可以浏览 <a href="http://www.zhangliguo.com/shuoshuo"><strong>说说效果页面</strong></a>
    </p>
  </div>
</div>

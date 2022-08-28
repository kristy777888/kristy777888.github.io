# 【转载】GHOST操作系统盈利 【赚钱模式研究】

诺顿克隆精灵（Norton Ghost），英文名Ghost为General Hardware Oriented System Transfer（通用硬件导向系统转移）的首字母缩略字[1]，是硬盘克隆程序，由Binary Research公司编写，后来于1998年6月24日被赛门铁克公司收购，扩展名为gho；但赛门铁克于2003年9月23日收购PowerQuest公司，所以扩展名改为v2i。该软件能够完整而快速地复制备份、还原整个硬盘或单一分区。

GHOST就是快速安装系统 封装预打包的系统文件  
提供用户快速安装操作系统的ISO或者GHO的镜像

这个东西起源并且流行于XP时代,造就了雨林木风/番茄花园/深度系统等一堆团队和公司  
那时候他们都还很纯洁,只是做些预装软件,并且做很多优化,提高系统的易用性  
除盗版问题外有些地方还是值得肯定的

而现在这个Ghost成为一个什么情况?  
变牟利工具了,是的 从一个备份恢复的工具…..  
应该3到4年以前 我就中过标 给朋友安装系统 随便下载了一个  
而且还和朋友谈过是不是也做个,后来因为各种原因放弃了

**我来八一八这个行业**  
首先打开百度 搜索一些关键词  
[<img loading="lazy" class="alignnone size-full wp-image-4604" src="https://blog.cnlabs.net/wp-content/uploads/2016/06/baidu2.jpg" sizes="(max-width: 807px) 100vw, 807px" srcset="/wp-content/uploads/2016/06/baidu2.jpg 807w, /wp-content/uploads/2016/06/baidu2-300x219.jpg 300w, /wp-content/uploads/2016/06/baidu2-768x561.jpg 768w" alt="baidu2" width="807" height="590" />][1]  
[<img loading="lazy" class="alignnone size-large wp-image-4605" src="https://blog.cnlabs.net/wp-content/uploads/2016/06/baidu1.jpg" sizes="(max-width: 700px) 100vw, 700px" srcset="/wp-content/uploads/2016/06/baidu1.jpg 799w, /wp-content/uploads/2016/06/baidu1-300x199.jpg 300w, /wp-content/uploads/2016/06/baidu1-768x508.jpg 768w" alt="baidu1" width="700" height="463" />][2]

傻子都知道百度推广是收费的 这些Ghost系统 “免费下载 免费安装系统“  
还砸钱推广,这样承担被起诉盗版的风险 就为了人民服务?  
推广成本多少?

这个是百度推广这类关键词的价格  
[<img loading="lazy" class="alignnone size-full wp-image-4606" src="https://blog.cnlabs.net/wp-content/uploads/2016/06/baidukeyword.jpg" sizes="(max-width: 891px) 100vw, 891px" srcset="/wp-content/uploads/2016/06/baidukeyword.jpg 891w, /wp-content/uploads/2016/06/baidukeyword-300x273.jpg 300w, /wp-content/uploads/2016/06/baidukeyword-768x698.jpg 768w" alt="baidukeyword" width="891" height="810" />][3]  
不一觉得这个价格好低啊 才几毛? 那你又太年轻了  
这个价格是准入价 就是低于这个价格你根本不显示广告内容 你要加钱 5毛的加2倍 1块5 这个差不多有显示了  
问题在于 百度的尿性 这个不是每个点击都会下载安装啊 有点错的啊 有只是路过的啊….  
以我的经验计算 一个下载在转换成本约5-10块钱  
那么问题来了 这东西免费下载 免费安装 你装个系统 他还倒贴5-10块钱一个…  
无利不起早 那么钱哪里来? 当然羊毛出在羊身上了

**我说下整个流程**  
1. 编写各种后门程序

> 功能包括但是不限于  
> 远程安装软件  
> 远程监控软件  
> 各种键盘记录软件  
> 各种网银大盗  
> 各种数据猎手

做好免杀

如果你只打算赚点小钱,不用写后门程序  
和我发现的那个某个县的电脑店一样 直接安装个APACHE+PHP +个BAT定时任务  
定时下载hosts文件替换  
设置一堆  
1.1.1.1 www.taobao.com  
1.1.1.1 www.jd.com  
这种域名 强制指向 1.1.1.1  
这个1.1.1.1 是你的IP  
当然了 你的IP肯定没淘宝的网站 但是你可以跳转啊  
nginx可以这样

<div id="crayon-5996802a32565830286072" class="crayon-syntax crayon-theme-classic crayon-font-monaco crayon-os-pc print-yes notranslate" data-settings=" minimize scroll-mouseover">
  <div class="crayon-plain-wrap">
  </div>
  
  <div class="crayon-main">
    <table class="crayon-table">
      <tr class="crayon-row">
        <td class="crayon-nums " data-settings="show">
          <div class="crayon-nums-content">
            <div class="crayon-num" data-line="crayon-5996802a32565830286072-1">
              1
            </div>
            
            <div class="crayon-num crayon-striped-num" data-line="crayon-5996802a32565830286072-2">
              2
            </div>
            
            <div class="crayon-num" data-line="crayon-5996802a32565830286072-3">
              3
            </div>
            
            <div class="crayon-num crayon-striped-num" data-line="crayon-5996802a32565830286072-4">
              4
            </div>
          </div>
        </td>
        
        <td class="crayon-code">
          <div class="crayon-pre">
            <div id="crayon-5996802a32565830286072-1" class="crayon-line">
              <span class="crayon-e">server</span> <span class="crayon-sy">{</span>
            </div>
            
            <div id="crayon-5996802a32565830286072-2" class="crayon-line crayon-striped-line">
              <span class="crayon-e">server_name </span><span class="crayon-v">www</span><span class="crayon-sy">.</span><span class="crayon-v">taobao</span><span class="crayon-sy">.</span><span class="crayon-e ">com *</span><span class="crayon-sy">.</span><span class="crayon-v">taobao</span><span class="crayon-sy">.</span><span class="crayon-v">com</span><span class="crayon-sy">;</span>
            </div>
            
            <div id="crayon-5996802a32565830286072-3" class="crayon-line">
              <span class="crayon-v">rewrite</span> <span class="crayon-o">^</span><span class="crayon-o">/</span><span class="crayon-sy">(</span><span class="crayon-sy">.</span><span class="crayon-o">*</span><span class="crayon-sy">)</span><span class="crayon-sy">$</span> <span class="crayon-v">http</span><span class="crayon-o">:</span><span class="crayon-c">//www.alimama.com/?pid=11111 $1 permanent;</span>
            </div>
            
            <div id="crayon-5996802a32565830286072-4" class="crayon-line crayon-striped-line">
              <span class="crayon-sy">}</span>
            </div>
          </div>
        </td>
      </tr>
    </table>
  </div>
</div>

意思是访问www.taobao.com 转向到 www.alimama.com的推广链接  
其他比如 www.jd.com www.yihaodian.com www.dangdang.com 一致操作

毫无技术含量是吗?

更高级些的 就是DNS挟持方式了  
锁定操作系统的DNS IP, 默认DNS的IP是运营商下发的  
我们可以改为自己的 然后使用注册表锁定起来 不让修改  
这种是明挟持 还有种暗挟持,直接注入到操作系统的网络进程里  
target到DNS request就丢弃,然后强制转向到自己的DNS服务器  
DNS请求到自己的服务器 就好了啊  
用户访问 就变这样了  
[<img loading="lazy" class="alignnone size-full wp-image-4603" src="https://blog.cnlabs.net/wp-content/uploads/2016/06/dnssss.jpg" sizes="(max-width: 592px) 100vw, 592px" srcset="/wp-content/uploads/2016/06/dnssss.jpg 592w, /wp-content/uploads/2016/06/dnssss-300x208.jpg 300w" alt="dnssss" width="592" height="411" />][4]

2. 技术人员安装系统  
安装好一个操作系统,安装各种杀毒软件,比如QQ电脑管理,360杀毒等等  
把自己的后门程序,或者改hosts的文件 加入白名单  
然后卸载掉这些杀毒软件,但是卸载方式是保留配置文件  
这样用户的电脑 就算再次安装这些杀毒软件 白名单依然存在有效 不会干掉你的后门程序  
搞好以后  
开始  
封装各种型号硬件的驱动  
整合各种预订软件  
安装各种PPI推广计费的预装软件  
强制设置和锁定主页 到自己的导航站或者www.hao123.com的推广 1000次IP多少钱那种  
锁定DNS IP

全部搞完以后 Ghost封装为GHO文件  
重复重复在重复 封装XP Win7 Win8 Win10

全部一堆搞完了

好了 上百度钓鱼去吧

结论?  
**亲 要学会微软官方下载ISO镜像,并且要使用正版KEY激活系统啊!**  
**不然损失的可不是一个正版操作系统的钱哦**

 [1]: https://blog.cnlabs.net/wp-content/uploads/2016/06/baidu2.jpg
 [2]: https://blog.cnlabs.net/wp-content/uploads/2016/06/baidu1.jpg
 [3]: https://blog.cnlabs.net/wp-content/uploads/2016/06/baidukeyword.jpg
 [4]: https://blog.cnlabs.net/wp-content/uploads/2016/06/dnssss.jpg

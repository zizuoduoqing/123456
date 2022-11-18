## 墨鱼手记这已经不是一个适用于大多数人的项目，仅献给我的小伙伴// ==UserScript==
// @ConfigName        墨鱼自用的QX配置文件
// @Author            Cuttlefish
// @TgChannel         𝐡𝐭𝐭𝐩𝐬://𝐭.𝐦𝐞/𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟐𝟏
// @WechatID          公众号墨鱼手记
// @Feedback          💡请通过邮件反馈问题[其它方式一概无视]：𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟏𝟑@𝟏𝟔𝟑.𝐜𝐨𝐦 💡
// @UpdateTime        2022/11/13 11:10 UTC/GMT +8
// @Function          请参考对应的注释或Tag
// @Appreciate        https://shrtm.nu/hGk2
// @MainFunction      去开屏广告、超级VIP、智能分流、图标订阅、流媒体查询、Boxjs订阅、网易云解灰色Music、IOS更新屏蔽
// @ExpressThanks     @ddgksf2013,@Nick-workflow,@KOP-XIAO,@DivineEngine,@blackmatrix7,@Orz-3,@yjqiang,@O7Y0,@Peng-YM,@Neurogram-R,@id77,@NobyDa,@17mon
// @ConfigVersion     2.0 (V143)
// @ConfigURL         https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Profile/QuantumultX.conf
// ==/UserScript==

# 𝐂𝐮𝐭𝐭𝐥𝐞𝐟𝐢𝐬𝐡 𝐒𝐞𝐥𝐟-𝐮𝐬𝐞 𝐂𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐚𝐭𝐢𝐨𝐧 𝐂𝐡𝐚𝐧𝐠𝐞𝐥𝐨𝐠 𝐂𝐫𝐞𝐚𝐭𝐞𝐝 𝐛𝐲 𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟏𝟑
# [+]2022-03-01  1、QX小白配置2.0已全面更新，重点更新[rewrite_remote]内容  
# [+]2022-03-15  2、QX配置头增加网易云解锁指导、图标库、IOS屏蔽更新、旧版文档、Crack腾讯文档  
# [+]2022-03-26  3、增加[替换支付宝内淘票票评分为豆瓣评分]和[豆瓣添加便捷播放按钮&展示在映流媒体平台]  
# [+]2022-03-30  4、增加墨鱼专属VIPcrack订阅[请自行添加hostname]  
# [+]2022-03-30  5、新增QX的GeoIP自动更新Url链接[内容见header]  
# [+]2022-03-31  6、新增什么值得买APP去广告的引用@blackmatrix7  
# [+]2022-04-04  7、增加@Orz-3的big和mini图标链接  
# [+]2022-04-14  8、添加QX进阶版使用教程@kopshawn  
# [+]2022-04-14  9、添加魔法订阅，仅供临时使用  
# [+]2022-04-21 10、添加Siri与搜索2.0配置@VirgilClyne  
# [+]2022-04-26 11、添加微信解锁被屏蔽的URL@zZPiglet  
# [+]2022-04-30 12、对rewrite_remote进行分类，并添加Q-Search  
# [+]2022-05-02 13、更换魔法订阅链接，仅供临时使用[订阅来源于网络]  
# [+]2022-05-06 14、贴吧去广告更换为@app2smile的库链接，删除[server_local]下无用的网易云解锁节点 
# [-]2022-05-12 15、从实用性角度出发，小白2.0配置注释掉Siri搜索与油管字幕翻译，有需要者自行去掉注释  
# [+]2022-05-15 16、增加网易云的policy，替换网易云policy的图标url  
# [+]2022-05-28 17、微博油管去广告替换为原作者独有链接  
# [+]2022-06-09 18、建议网易云解锁订阅后加上[#checkurl=http://interface3.music.163.com]，添加喜马拉雅去广告  
# [+]2022-07-10 19、精简DNS，添加更多geo_location_checker选项  
# [-]2022-07-31 20、去除B站自动策略，有需要，请自行添加，精简配置头的部分说明
# [+]2022-08-05 21、新增节点响应时间限制server_check_timeout
# [+]2022-08-15 22、将geo_location_checker设置为disabled，删除几条通用去广告（与StartUp.conf有部分重复，也与知乎、值得买等有重复）
# [+]2022-08-17 23、将DivineEngine的更改为blackmatrix7的Advertising.conf，将未启用的重写放置QX界面最下端，
# [+]2022-08-21 24、添加dprefer-doh3(doh-server = https://223.5.5.5/dns-query, https://223.6.6.6/dns-query)QX1.0.30+
# [+]2022-09-19 25、将final分流绑定黑白名单policy，由用户自行选择直连或是代理，server_check_url响应地址改为http://www.gstatic.com/generate_204
# [+]2022-09-29 26、直连分流替换为VirgilClyne 的ASN.China.list，添加不mimt抖音、ios天气、google的host；更换header图标说明
# [+]2022-10-19 27、应群友邮件需求，墨鱼小白配置2.0中策略组新增自动选择，更新方法，可将policy部分进行替换
# [+]2022-10-22 28、策略组tolerance调整，自动选择的策略组自动排除网易云节点，油管去广告换回墨鱼整理的
# [+]2022-11-06 30、添加icloud、qq、tencent、weixin指定域名的DNS解析，并添加两个mitm域名排除
# [-]2022-11-13 31、删除QQ域名的DNS解析

# > 建议在「其他设置」里「GeoLite2」的「来源」填写使用下面链接「任选一个」，并开启「自动更新」
; https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb
; https://github.com/Hackl0us/GeoIP2-CN/raw/release/Country.mmdb


# > 解锁网易云灰色音乐，获取证书链接 
; https://raw.githubusercontent.com/nondanee/UnblockNeteaseMusic/master/ca.crt
# > 具体操作步骤可参考下面这篇《利用QuantumultX解锁网易云付费及非版权音乐》文章
; https://mp.weixin.qq.com/s/ca6U1O2FTfcqzL7TnJ04IQ


# > QuantumultX图标库订阅，打开以下URL，手机端点击图片即可快捷添加「1.0.30+」
; https://codeberg.org/ddgksf2013/Cuttlefish/src/branch/master/Icon/README.md


# > 推荐使用的旧版应用如下链接所示
; https://docs.qq.com/sheet/DYmRTQXpVY0hNcGls?tab=y6do1j
# > 利用描述文件屏蔽IOS更新提醒（兼容IOS13、14、15）
; https://app.initnil.com/tvOS.mobileconfig


# > 以上全部内容[1-70行]可自行在配置中删除，对使用并无影响

[general]

# > 用于节点延迟测试
server_check_url= http://www.gstatic.com/generate_204
# > 服务器测试超时时间 (毫秒)
server_check_timeout = 3000
# > 用于设置图标显示
profile_img_url=https://github.githubassets.com/images/modules/site/integrators/google.png
# > 用于Check节点IP地址(以下geo_location_checker任选一个即可)
geo_location_checker=disabled
;geo_location_checker=http://ip-api.com/json/?lang=zh-CN, https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/IP_API.js
# > 功能强大的解析器，用于引用资源的转换
resource_parser_url=https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/resource-parser.js
# > 下列路径将不经过QuanX的处理
excluded_routes=239.255.255.250/32, 24.105.30.129/32, 185.60.112.157/32, 185.60.112.158/32, 182.162.132.1/32
udp_whitelist=1-442, 444-65535
# > 第一个filter为4g模式开启规则分流，第二个filter为其他wifi下开启规则分流，第三个wifi1修改成你路由器翻墙的wifi名开启直连模式，第四个wifi2为你公司或者其他有路由器翻墙的WiFi名走直连）
# > 默认关闭根据wifi切换模式，如需开启，删除下方的"#"即可
#running_mode_trigger=filter, filter, wifi1:all_direct, wifi2: all_direct
# > dns_exclusion_list
dns_exclusion_list=*.cmpassport.com, *.jegotrip.com.cn, *.icitymobile.mobi, id6.me, *.pingan.com.cn, *.cmbchina.com



[task_local]

# > 请手动添加下面的订阅（流媒体Task订阅集合）
; https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/UI-Action.json
# > 流媒体解锁查询
event-interaction https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/streaming-ui-check.js, tag=流媒体解锁查询, img-url=arrowtriangle.right.square.system, enabled=true



[rewrite_local]



[rewrite_remote]

#>>>>>>>>>>>解锁会员
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/ForOwnUse.conf, tag=墨鱼专属VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/AdBlock/Bilibili.conf, tag=B站去广告+1080P高码率@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/UnlockVip/Spotify.conf, tag=Spotify音乐VIP@app2smile, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>软件增强
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/UnlockVip/BaiduCloud.conf, tag=百度网盘倍速@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/zZPiglet/Task/master/UnblockURLinWeChat.conf, tag=微信解锁被屏蔽的URL@zZPiglet, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/TikTok.conf, tag=Tiktok解锁[需旧版V21]@Orz-3, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/Netflix_ratings.conf, tag=Netflix评分@Orz-3, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>应用去广告
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/AdBlock/StartUp.conf, tag=应用去开屏广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/script/zhihu/zhihu_plus.qxrewrite, tag=知乎去广告及体验增强@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/script/smzdm/smzdm_remove_ads.qxrewrite, tag=什么值得买去广告@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://github.com/app2smile/rules/raw/master/module/tieba-qx.conf, tag=百度贴吧去广告@app2smile, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/AdBlock/Applet.conf, tag=微信小程序去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/AdBlock/YoutubeAds.conf, tag=油管去广告@DivineEngine, update-interval=86400, opt-parser=false, enabled=true
https://github.com/zmqcherish/proxy-script/raw/main/weibo.conf, tag=微博去广告@zmqcherish, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/AdBlock/Ximalaya.conf, tag=喜马拉雅去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>通用去广告
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rewrite/QuantumultX/Advertising/Advertising.conf, tag=去广告重写@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/General.conf, tag=神机重定向@DivineEngine, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>网页优化
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Html/WebAdBlock.conf, tag=影视网站去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/Function/Q-Search.conf, tag=Safari超级搜索@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>未启用的重写
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/UnlockVip/Rrtv.conf, tag=人人视频VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=false
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/UnlockVip/Kuwo.conf, tag=酷我音乐VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=false
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/JD_TB_price.conf, tag=比价脚本@Orz-3, update-interval=86400, opt-parser=false, enabled=false
https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Rewrite/Function/BilibiliAutoRegion.conf, tag=B站换区脚本[不会配置boxjs请勿勾选]@NobyDa, update-interval=86400, opt-parser=false, enabled=false
https://raw.githubusercontent.com/id77/QuantumultX/master/rewrite/Youtube_CC.conf#out=Hant, tag=油管字幕翻译@id77, update-interval=86400, opt-parser=false, enabled=false
https://raw.githubusercontent.com/chavyleung/scripts/master/box/rewrite/boxjs.rewrite.quanx.conf, tag=BoxJS商店版@chavyleung, update-interval=86400, opt-parser=false, enabled=false

[server_local]



[server_remote]
https://www.xingjiabijichang.com/api/v1/client/subscribe?token=c6629a19011b7e2538be7a79f3b5f3e5, tag=崽崽永远18, update-interval=172800, opt-parser=true, enabled=true

# > 为避免网易云解锁节点滥用，有需求的请去墨鱼手记公众号回复「网易云」获取

# > 魔法仅供临时使用
https://proxies.bihai.cf/vmess/sub?filter=r#emoji=2, tag=临时使用, update-interval=3600, opt-parser=true, enabled=false



[dns]

prefer-doh3
no-ipv6
no-system
server=223.5.5.5
server=119.29.29.29
server=114.114.114.114
doh-server = https://223.5.5.5/dns-query, https://223.6.6.6/dns-query
server=/*icloud.com/119.29.29.29
server=/*icloud.com.cn/119.29.29.29
server=/*tencent.com/119.29.29.29
server=/*weixin.com/119.29.29.29



[policy]

static=网易云音乐, direct, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Netease_Music_Unlock.png
static=全球加速, 自动选择, 香港节点, 台湾节点, 日本节点, 狮城节点, 美国节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Global.png
static=苹果服务, direct, 自动选择, 香港节点, 台湾节点, 美国节点, 日本节点, 狮城节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Apple.png
static=港台番剧, direct, 自动选择, 香港节点, 台湾节点, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/StreamingSE.png
static=国际媒体, 香港节点, 自动选择, 台湾节点, 日本节点, 美国节点, 狮城节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Streaming.png
static=兜底分流, 全球加速, direct, 自动选择, 香港节点, 台湾节点, 日本节点, 狮城节点, 美国节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Final.png

#默认设置10分钟测速一次
url-latency-benchmark=自动选择, server-tag-regex=^(.(?!(网易|墨鱼)))*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Auto.png
url-latency-benchmark=香港节点, server-tag-regex=(?=.*(港|HK|(?i)Hong))^((?!(台|日|韩|新|美)).)*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/HK.png
url-latency-benchmark=台湾节点, server-tag-regex=(?=.*(台|TW|(?i)Taiwan))^((?!(港|日|韩|新|美)).)*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/TW.png
url-latency-benchmark=日本节点, server-tag-regex=(?=.*(日|JP|(?i)Japan))^((?!(港|台|韩|新|美)).)*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/JP.png
url-latency-benchmark=狮城节点, server-tag-regex=(?=.*(新|狮|獅|SG|(?i)Singapore))^((?!(港|台|日|韩|美)).)*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/SG.png
url-latency-benchmark=美国节点, server-tag-regex=(?=.*(美|US|(?i)States|American))^((?!(港|台|日|韩|新)).)*$, check-interval=600, tolerance=0, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/US.png



[filter_remote]

https://codeberg.org/ddgksf2013/Cuttlefish/raw/branch/master/Filter/NeteaseMusic.list, tag=解锁网易云音乐, force-policy=网易云音乐, update-interval=172800, opt-parser=false, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Unbreak.list, tag=规则修正, force-policy=direct, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Advertising.list, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/AdvertisingPlus.list#type=domain-set, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/NobyDa/Script/master/Surge/AdRule.list, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/app2smile/rules/master/rule/tieba-ad-qx.list, tag=贴吧广告, force-policy=reject, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Hijacking.list, tag=运营劫持, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Privacy.list, tag=隐私保护, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Video/TikTok.list, tag=海外抖音, force-policy=全球加速, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Extra/Google/GoogleVoice.list, tag=Google Voice, force-policy=美国节点, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/HK.list, tag=流媒体HK, force-policy=香港节点, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/TW.list, tag=流媒体TW, force-policy=台湾节点, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/JP.list, tag=流媒体JP, force-policy=日本节点, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/US.list, tag=流媒体US, force-policy=美国节点, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Streaming.list, tag=国际媒体, force-policy=国际媒体, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/StreamingSE.list, tag=港台番剧, force-policy=港台番剧, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Global.list, tag=全球加速, force-policy=全球加速, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Extra/Apple/Apple.list, tag=苹果服务, force-policy=苹果服务, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/VirgilClyne/GetSomeFries/main/ruleset/ASN.China.list, tag=国内网站, force-policy=direct, update-interval=172800, opt-parser=true, enabled=true



[filter_local]

# > 知乎AD屏蔽,以下规则请放置在filter_local最顶部
DOMAIN,118.89.204.198,REJECT
DOMAIN-KEYWORD,118.89.204.198,REJECT
IP-CIDR,118.89.204.198/32,REJECT
DOMAIN,appcloud2.in.zhihu.com,REJECT
HOST,mqtt.zhihu.com,reject
HOST,sugar.zhihu.com,reject
USER-AGENT,AVOS*,REJECT

# > B站自动换区
ip-cidr, 203.107.1.1/24, reject

# > local
ip-cidr, 10.0.0.0/8, direct
ip-cidr, 127.0.0.0/8, direct
ip-cidr, 172.16.0.0/12, direct
ip-cidr, 192.168.0.0/16, direct
ip-cidr, 224.0.0.0/24, direct
ip-cidr, 182.254.116.0/24, direct
geoip, cn, direct
final, 兜底分流



[http_backend]

# > Boxjs设置，改为使用http backend方式，访问地址改为http://127.0.0.1:9999，更新配置后请长按风车-更新，然后重启代理
# > BoxJs相关教程参考 https://chavyleung.gitbook.io/boxjs/
https://raw.githubusercontent.com/chavyleung/scripts/master/chavy.box.js, host=boxjs.com, tag=BoxJS, path=^/, enabled=false



[mitm]
passphrase = AD63F607
p12 = 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

skip_validating_cert = true
force_sni_domain_name = false

hostname = -consumer.fcbox.com, -*huami.com, -weather-data.apple.com, -*amemv.com, -*snssdk.com, -www.google.com

# 🟢 passphrase和p12代为证书&主机名部分, 更新配置前可把旧的配置中passphrase和p12代码拷贝下来, 导入新的配置文件把内容粘贴在对应位置就不用重装证书

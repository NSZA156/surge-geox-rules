# ❤️ Surge Geox Rules
GeoX (GeoIP GeoSite)格式的规则集，为SurfBoard和Surge所作，便于使用GeoSite进行自定义的场景及作为订阅转换预配置。  
每天UTC时间22:30:00更新规则  

## 🙋‍♂️ 如何使用
切换至[release](https://github.com/NSZA156/surge-geox-rules/tree/release)分支查看规则  
引用规则：  
https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geoip/ + GeoIP规则.txt  
https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geosite/ + GeoSite规则.conf  
配置文件字段示例  
```
[Rule]
# GeoIP
RULE-SET,https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geoip/cn.txt,DIRECT
RULE-SET,https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geoip/cloudflare.txt,你的代理组
# GeoSite
RULE-SET,https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geosite/category-ads-all.conf,REJECT
RULE-SET,https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geosite/category-ai-!cn@ads.conf,REJECT
RULE-SET,https://github.com/NSZA156/surge-geox-rules/raw/refs/heads/release/geo/geosite/category-acg.conf,你的代理组
```

## 😘 说明
本项目规则集中GeoIP直接来自于[Loyalsoldier/GeoIP](https://github.com/Loyalsoldier/geoip)  
GeoSite上游来源为[Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat)  
若您对GeoSite内容有疑问且非本项目特有，请反馈问题至上游。  

### ✔️ 属性
本项目规则集支持原GeoSite中含属性字段，含属性规则集独立为 规则集@属性.conf  
关于GeoSite属性，详见 https://github.com/v2ray/domain-list-community  

### ❌ 正则类规则
原GeoSite支持以regex:开头的正则表达式匹配规则，然而，由于Surge本身不支持正则匹配域名，此类规则无法保留。    
（从Surge iOS 5.11.0 Surge Mac 5.7.0 开始，Surge支持了DOMAIN-WILDCARD类规则，使用通配符*和?匹配域名。  
然而通配符的表达能力不及正则表达式，若强行转换将可能导致大量误匹配，以category-porn中```regex:(^|\.)[a-z][1-9][0-9][a-z]\.com$```  
为例，此规则转换后成为```DOMAIN-WILDCARD,????.com```，将无差别匹配所有四位字符的.com域名，如fast.com，  
这显然是我们所不希望看到的，考虑到正则类规则较少，为了减少误匹配，不对其进行转换。）  

## 🫶 致谢
- [[@MetaCubeX/geo]](https://github.com/MetaCubeX/geo)超棒的Geo资源管理工具
- [[@LoyalSoldier/GeoIP]](https://github.com/Loyalsoldier/geoip)提供GeoIP规则
- [[@Loyalsoldier/v2ray-rules-dat]](https://github.com/Loyalsoldier/v2ray-rules-dat)GeoSite规则上游


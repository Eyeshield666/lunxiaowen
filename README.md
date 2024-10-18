![](https://photo-1318093525.cos.ap-guangzhou.myqcloud.com/photo/image-20241012144253381.png)

<h1 style="text-align: center">论小文AI写作开源版</h1>
<h4 style="text-align: center">只需输入论文标题，1分钟为您生成高质量学术论文，轻松提升写作效率！</h2>



## 1. 项目简介

💥💥💥 **论小文AI写作开源版**是一个强大的AI写作平台，旨在通过先进的自然语言处理技术帮助用户快速撰写学术论文。用户可以从4种论文品类（毕业论文、期刊论文、开题报告、职称论文）中选择一种，输入文章标题，系统会自动生成论文大纲，并根据大纲在1分钟内完成全文写作，大幅提升写作效率。

本项目使用前后端分离开发，前端使用Uniapp + Vue2，支持PC端、H5端、微信浏览器端和微信小程序端，后端使用PHP7.4。

体验地址：https://ai.lunxiaowen.cn/

**系统展示：**

![](https://photo-1318093525.cos.ap-guangzhou.myqcloud.com/photo/WX20241017-165618%402x.png)
## 2. 特性与优势

- **开源与灵活性**：采用MIT开源协议，全开源、无限制，允许任意二次开发，具有极大的灵活性。
- **多端支持**：基于稳定的技术架构（Uniapp和Vue2），支持PC、H5、微信浏览器及微信小程序4端使用，确保跨平台的无缝体验。
- **丰富的论文类型**：内置4种论文类型选择，涵盖毕业论文、期刊论文、开题报告、职称论文，满足不同学术需求。
- **操作简便**：界面设计直观，用户只需输入标题，便可轻松生成论文大纲，进而生成完整论文，无需复杂操作。
- **快速生成**：从生成大纲到完整论文，平均用时仅1分钟，大幅提升论文写作效率。

## 3. 使用方法

- 配置apikey（添加[客服微信](#10. 联系我们)免费获取）。
- 输入论文标题，生成论文大纲。
- 查看论文大纲，生成完整论文。
- 生成完成后下载论文。

## 4. 技术架构

论小文AI写作开源版采用成熟稳定的技术栈。

#### 前端架构

- **Uniapp**：多端开发框架，实现“一套代码，多端运行”，支持PC、H5、微信浏览器、微信小程序四端，减少开发和维护成本。
- **Vue2**：轻量且易于扩展的前端框架，提升开发效率，并确保界面的响应速度和用户体验。
- **UView 2.0**：基于Uniapp的UI组件库，提供丰富的UI组件，优化界面设计和交互效果，使用户操作简单直观。

#### 后端架构

- **PHP 7.4**：广泛应用的后端语言，兼具易用性与强大性能，保证系统稳定运行。
- **ThinkPHP 6.1.0**：高效的MVC框架，支持快速开发和易于维护，便于实现业务逻辑与数据管理的分离。

#### 架构优势

- **跨平台支持**：凭借Uniapp，项目可在多个终端无缝运行，为用户提供一致的体验。
- **高效开发与维护**：Uniapp和UView 2.0的组合，提升了开发速度并优化了用户界面。
- **后端性能可靠**：PHP与ThinkPHP结合，保证系统的响应速度和稳定性，即使在高并发情况下也能流畅运行。
- **可扩展性强**：整个系统采用模块化设计，便于二次开发和后续功能扩展。

## 5. 运行与部署

### (1) 项目目录介绍

``` 
- lunxiaowen
  -- public 项目打包后的文件，可直接部署到服务器
  -- lunxiaowen-uni 前端项目代码
  -- lunxiaowen 后端项目代码
```

### (2) 宝塔面板/服务器 快速部署

* 环境要求

  | 运行环境        | 要求版本 | 推荐版本 |
  | :-------------- | :------- | :------- |
  | PHP             | >=7.4    | 7.4      |
  | Mysql           | >=5.7    | 5.7      |
  | nginx 或 apache | 无限制   | -        |

  强烈正式环境推荐使用宝塔面板部署项目，让部署更方便，减少部署出现问题。

* 服务器环境设置

  * 点击【软件商店】-【运行环境】，安装Nginx、MySQL、PHP-8.0。其中Mysql选择5.7版本
    * 提示：安装软件时，使用极速安装，避免出现一些环境引起的问题。
  * 点击【软件商店】-【已安装】，找到php-7.4，点击【设置】-【安装扩展】，安装fileinfo扩展，安装redis扩展

* 站点部署

  * 下载  <项目名称>安装包，解压到宝塔/www/wwwroot目录



  * 点击【网站】-【PHP项目】-【添加站点】，【域名】项填好已解析到本服务器的域名，【根目录】选择上一步解压好的项目目录的server目录，数据库选择【MySQL】，【数据库帐号】项设置好帐号密码，【PHP版本】选择【PHP-74】，点击【提交】

  * 保存好数据库名、用户、密码，后续步骤需要用到

  * 找到网站，点击【设置】-【SSL】-【Let's Encrypt】-【文件验证】-【选择域名】-【申请】，申请SSL证书

  * 点击【网站目录】-【运行目录】选择"/public"，点击【保存】
  * 找到后端根目录下sql/init.sql,导入到新建的数据库中
  * 复制一个.example.env，并去掉.example  ，并填写对应的数据库信息

### (3) 后端项目本地运行

* 参考5.2中的环境要求，准备开发环境，并安装EServer

* 以EServer部署为例

  * 打开github拉取源码到本地

  * 打开EServer，点击启动nginx和php7.4 

  * 点击【网站】-【添加】，设置根目录为解压源码的public目录，同步hosts打开。

  * 找到后端根目录下sql/init.sql，导入到新建的数据库中

  * 复制一个.example.env，并去掉.example  ，并填写对应的数据库信息

    
    

> 提示：按照此条本地运行的时候，服务端地址为127.0.0.1:9090。
>

### (4) 前端项目本地运行

* 准备开发环境

  * NodeJs 18~20（推荐20.17.0）
  * 集成开发环境


* H5端项目运行

  ```
  npm run serve
  ```



## 6. 常见问题 (FAQ)

**Q：如何获取apikey？**

A：添加作者微信，向作者表明来意，客服将为您免费提供apikey。

**Q：如何调整生成的论文内容？**

A：论文内容与论文的标题和大纲有关，开源版暂不支持手动编辑大纲，您可以通过修改更精准的论文标题来调整生成的论文内容。同时AI生成具有随机性，您可以尝试多生成几篇，会产生不同的结果。

**Q：生成的论文是否符合学术格式要求？**

A：是的，生成的论文自动按照常见学术格式进行排版，用户无需额外调整。

**Q：生成的论文可以保存吗？**

A：在生成成功页面上，用户可以将生成的论文下载到本地，退出页面后论文将丢失，生成成功后请及时下载。

**Q：安装时遇到问题怎么办？**

A：请检查系统是否符合项目的系统要求，并确保按照操作步骤进行安装。如果问题仍未解决，您可以通过添加[客服微信](#10. 联系我们)获取实时支持。

**Q：如何升级到商业版**

A：点击链接查看[论小文AI写作商业版](#9. 论小文AI写作商业版)详细信息。

**Q：前端项目运行后页面红屏报错Unknown promise rejection reason怎么办？**

A：检查后端项目是否正常运行，正常运行则按5.4中的步骤，正确设置代理为后端项目运行地址，重新运行前端项目。

## 7. 贡献指南

欢迎大家为论小文AI写作开源版项目做出贡献！

* 提交需求或报告Bug请提交Issue，详细描述您的需求或您遇到的问题。

- 贡献代码请在充分测试后提交Pull Request，在描述中说明所做的更改、解决的问题或实现的新功能，必要时附上相关的截图或测试结果，我们会定期评估和更新。

## 8. 许可证

论小文AI写作开源版采用MIT开源许可证，允许自由二次开发和商业使用，无任何限制。

- **无限制使用**：可以免费获取源代码并进行修改或扩展，满足个人或企业的定制需求。
- **自由商业化**：无论是将其用于个人项目，还是集成到商业产品中，您都无需担心版权问题或额外费用。
- **社区支持**：鼓励开发者积极参与项目，贡献代码或改进功能，共同推动项目的进步。

## 9. 论小文AI写作商业版

🚀🚀🚀 尽管论小文写作系统开源版本功能已非常强大，若需要更高级的功能，欢迎使用我们的商业版产品，享受以下服务：

- **专属技术支持**：优先解决您的技术问题，确保高效稳定的使用体验。
- **专业的后台管理系统**：支持全面的用户管理、论文生成记录跟踪以及系统配置，方便企业或大规模用户进行高效的管理和运营。
- **安全性升级**：商业版提供更全面的数据保护和隐私保障，支持后台在线更新，适合企业及大规模应用场景。
- **功能更加丰富**：
  - **大纲可编辑**：用户可以根据个人需求对系统生成的论文大纲进行修改调整，以更好地匹配特定写作方向，生成更符合用户期望的文章。
  - **插入图表**：支持在论文任选章节插入图表，满足学术写作中对数据展示和视觉化的需求。
  - **具有支付系统**：集成了便捷的支付功能，为平台的收费服务和论文购买提供了流畅的交易体验。
  - **保存论文生成记录**：用户的所有论文生成记录包括大纲和正文都会自动保存，方便随时查看和下载，有效提升写作的连续性与管理效率。

论小文AI写作商业版体验地址：[https://ai.lunxiaowen.cn/](https://ai.lunxiaowen.cn/)

**详细功能对比如下：**

| 系统功能 | 开源版                                                     | 商业版                                                       |
| -------- | ---------------------------------------------------------- | ------------------------------------------------------------ |
| 是否开源 | 完全开源                                                   | 代码无加密无混淆，需绑定服务器ip，支持二次开发               |
| 产品定位 | 个人用户（学生、研究者）和开发者，寻求免费、高效工具       | 企业用户、高级用户（科研团队）、商业化运营者                 |
| 商业运营 | 不适合商业运营                                             | 具备专业的后台管理系统和完整的支付体系，完美支持商业运营     |
| 更新频次 | 社区驱动，不定期更新，修复漏洞、优化性能、社区贡献的新功能 | 定期更新，通常每季度一次，新功能扩展、安全更新、性能提升、技术支持                                                | 有详细的开发文档                                             |
| 论文品类 | 4种基本论文品类                                            | 11种常用论文品类，后续将逐步添加更多论文品类                 |
| 大纲编辑 | 不支持                                                     | 支持                                                         |
| 插入图表 | 不支持                                                     | 支持                                                         |
| 历史记录 | 无历史记录，退出网页后无法再次查看生成的大纲和正文         | 服务器保存历史记录，可以随时查看生成的大纲和正文             |

如果您对我们的商业版感兴趣，可以添加[客服微信](#10. 联系我们)详细了解。

## 10. 联系我们

如果您想了解更多信息或获取帮助，请添加我们的客服微信，享受以下专属福利：

- **系统体验**：免费获取apikey体验极速论文生成！
- **实时技术支持**：快速解决您在使用“论小文”过程中遇到的任何问题。
- **第一手更新通知**：优先获取系统更新、功能升级及新产品发布的信息。
- **专属优惠活动**：不定期推出的商业版优惠活动，帮助您以更优价格升级体验。
- **定制化解决方案**：根据您的需求，提供定制化的AI写作和学术支持服务。
![](https://photo-1318093525.cos.ap-guangzhou.myqcloud.com/photo/WX20241017-184810%402x.png)




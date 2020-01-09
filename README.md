# API_ML_AI_MUSEUM
|   发布时期  |   2019-12-17  |
| --- | --- |
| 史诗名称    | 趣味博物馆    |
|  文件现状   |  未完成  |
|  文件的主人   |  谭怡颖   |
|  领头设计者   |   谭怡颖  |
|  领头开发者   |  谭怡颖   |
|  领头测试者   |  谭怡颖   |  

###  (一）价值主张  
趣味博物馆app让用户既能沉浸于博物馆的文物知识熏陶中，又能感受博物馆的另一番趣味。本产品会通过定位的功能，得知用户当前所处在博物馆的哪个区域，为用户提供当前所处区域的内容讲解，满足用户个性化需求。为了满足用户更全面的需求，APP中也会提供展厅内所有文物的相关信息供用户阅读。那么为了让用户在博物馆内也能够感受到趣味性，APP还提供与名人合照的功能，用户只需要拍下想要合照的名人，APP会自动将人像抠图下来，用户就能够单独与名人同窗合照。同时还有拍照闯关的趣味游戏，用户只需要根据要求，拍摄相关的照片，APP就会自动识别图片中物体信息是否符合活动要求，满足要求后，用户就可以获得相应的博物馆纪念品/合作商礼品的奖励。
### （二）加值宣言  
使用高德的定位API，不管软件是处于前台还是后台都能够快速的帮用户定位手机当前的所在位置；使用百度的通用物体和场景识别API，根据用户拍摄的照片，自动识别图片中的物体信息；使用百度的人像分割API，识别图像中的人体轮廓，与背景进行分离，返回分割后的二值图、灰度图、前景人像图、透明背景人像前景图，实现像素级分割。
### （三）核心价值  
让用户既能根据自己的节奏了解文物，又能在安静甚至可能枯燥的博物馆中感受趣味。
### （四）用户痛点  
- 痛点一：注意力难以集中，想活动
- 痛点二：行走不便跟不上大部队，但又想听讲解。
- 痛点三：想和古人合照，但是他们都在展台里。
### （五）需求列表  
标题 | 用户案例 | 重要程度 
--- | --- | ---
 定位  |    小明想要一个人逛博物馆，但又想有人帮忙讲解一些重要文物      |    重要     
 人像分割合照  |   小明听了这个名人的风光记事后，想要和他进行合影，但是他却在展台的一张图片里       |    重要      
 物体识别  |   活动需要拍照上传3张文物上有鸟的图片       |    次重要      
 
### （六）人工智能概率性  
- **高德定位API**  
目前高德定位不论在室外、室内还是在高楼林立的城市峡谷，都可以实现精准的定位。因此该功能的使用对用户体验的负面影响不至于压过正面影响。
- **百度人像分割API**  
对于具有清晰人像轮廓的人像照片，百度人像分割功能基本能实现精准分割输出前景人像图。若人像照片背景颜色太深，返回的前景人像图中人体轮廓边缘会遗留些许未抠图前的背景色，但范围并不是很大，这方面可能只对于具有强迫症的人并不是很友好。
- **百度通用物体识别API**  
虽不能准确识别出该物体的具体类别，但能返回该物体所属的大类，满足我们产品活动中检索物体属性的基本需求。但若光线不足的情况下，会影响判断，并且若相框内同时出现多个物体，会同时返回每个物体的类别，影响我们后台对用户收集的统计，从而影响用户的情绪。为此，当用户在使用此项功能时，产品会提醒用户要在光线较亮的情况下进行扫描物体，并且要尽量保证镜头单独对准目标物体。
### （七）产品原型
[产品原型下载](https://github.com/ViTaSoyi/museum_prototype/)  
[产品原型交互](https://vitasoyi.github.io/museum_prototype/strat.html)

#### 核心功能页面
- **随你讲解**  
> 使用流程：进入随你讲解页面 —— 选择男声/女声 —— 播放当前定位展厅的讲解 —— 点击定位 —— 搜索/选择定位 —— 播放选择展厅的讲解  
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E8%AE%B2%E8%A7%A3.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E5%AE%9A%E4%BD%8D.png)  

- **活动**  
> 使用流程：进入活动页面 —— 选择任一活动浏览/参加 —— 点击扫描 —— 扫描目标物体 —— 返回审核结果  
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E6%B4%BB%E5%8A%A8.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E6%B4%BB%E5%8A%A8%E8%AF%A6%E6%83%85.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E7%89%A9%E4%BD%93%E6%89%AB%E6%8F%8F.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E6%89%AB%E6%8F%8F%E7%BB%93%E6%9E%9C.png)  

- **与古人合照**  
> 使用流程：进入与古人合照页面 —— 选择拍照 —— 拍摄目标人物 —— 返回抠图后的效果图 —— 与ta合拍 —— 返回合拍后的图片  
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E5%90%88%E7%85%A7.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E4%BA%BA%E5%83%8F%E5%88%86%E5%89%B2%E6%8B%8D%E7%85%A7.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E4%BA%BA%E5%83%8F%E5%88%86%E5%89%B2%E7%BB%93%E6%9E%9C.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E4%BA%BA%E5%83%8F%E5%90%88%E6%8B%8D.png)
[](https://github.com/ViTaSoyi/API_ML_AI_MUSEUM/blob/master/images/%E5%90%88%E6%8B%8D%E8%BF%94%E5%9B%9E%E7%BB%93%E6%9E%9C.png)

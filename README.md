# 博物馆人脸识别智能开柜小程序
|发布日期|2019/12/xx|   
|  ----  |  ----  | 
|产品名称|博物馆人脸识别开柜小程序|     
|文件状态|已完成|   
|文档所有者|陈咏琴|   
|设计师|陈咏琴|   
|开发人员|陈咏琴|   
   

## 价值主张设计

### PRD1.加值宣言 3%

1. **可在无网络环境下离线使用**      
运用人脸离线识别SDK技术，可在无网络环境下离线使用，避免不良网络环境对通行效率的影响。   
2. **减少工作时间，提高工作效率**   
工作人员不需要用手/钥匙打开展柜门，储存藏品的仓库门，通过人脸离线识别可直接开启门，尤其是工作人员在搬运藏品腾不出手时。
3. **安全性能高**   
通过人脸离线采集SDK，收集博物馆相关工作人员的人脸到人脸库中，在开门时有活体检测与人脸识别，准确率高达99%。   
4. **数据化管理与监督**   
记录展柜门的开启关闭次数、时间、谁开的门、取走和放入的展品是什么等数据，高效管理与监督博物馆内物品与人员流动，提高藏品在博物馆内的安全性。对于管理者来说。

### PRD2.核心价值 3%
**最小可行性产品：**   
博物馆通过人脸离线采集SDK，采集相关工作人员的人脸，入到人脸库。博物馆藏品在搬运过程中，有特殊权限的工作人员通过人脸搜索API和人脸识别API技术，实现无手与钥匙就可开启展柜门与藏品储存门。减少搬运藏品的工作时间，提高工作效率。可记录展柜门与藏品储存门被开启的次数、以及是谁开启的等数据，实现数据化管理与监管，提高藏品在博物馆内的安全性。

### PRD3.核心价值与用户痛点 3%
- 目标用户：博物馆的管理层人员  
**用户痛点：**    
1. 搬运藏品需要频繁关闭开启展柜门、藏品储存的仓库门，增加了工作人员的工作时间，降低效率。   

2. 藏品在搬运过程中工作人员没办法腾出手来开门，只能放下藏品再开门，藏品有碰损的机率。   
   
3. 博物馆的藏品众多且贵重，藏品流动又大，不好管理与监督。       

博物馆人脸识别智能开柜针对以上用户痛点，提出以下解决方案：
1. 人脸离线SDK识别，自动开门。   

2. 数据化管理监督，提高藏品在博物馆内的安全性。


### PRD4.人工智能概率性与用户痛点 3%   
[百度AI人脸搜索：](https://ai.baidu.com/tech/face/search)    
万级别人脸库首选,识别率高达99%以上   
[百度AI活体检测：](https://ai.baidu.com/tech/face/faceliveness)    
低功耗、低CPU占用率，平衡资源使用，99.9% SLA保障      

人脸识别技术现已运用在很多领域，如人脸付款、人脸识别开户等。

### PRD5.需求列表与人工智能API加值 3%

|技术|用户需求|功能|重要程度|
|---|---|---|---|
|人脸离线采集SDK|有权限开门的工作人员|在人脸检测及追踪过程中，完成人脸图片采集，并输出预设条件的人脸图片|很重要|
|活体检测|保障业务安全性，提高安全性|识别业务场景中的用户是否为 「真人」，有效抵御照片、视频、3D模具等作弊行为|很重要|
|人脸搜索|工作人员人脸开门|用户身份识别和核验|很重要|

综合起来，人脸离线识别SDK：
提供设备端本地化的人脸采集、活体检测、人脸对比与识别能力，可在无网络环境下离线使用

可参考：

[人脸闸机](https://ai.baidu.com/solution/facegate)百度AI方案（离线）：
在设备端离线完成人脸注册和识别全过程，无需网络连接，闸机实时响应，无感知急速放行。避免不良网络环境对通行效率的影响，支持3种离线活体检测能力，高精度抵御作弊行为。
人脸离线识别SDK

![离线方案](https://upload-images.jianshu.io/upload_images/11043770-2eb84ff1e5d3716b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 原型 20%

# [原型文档查看](https://172018051.github.io/museum/)   

![产品架构](https://upload-images.jianshu.io/upload_images/11043770-0b74ffebcd911063.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   
   
### 人脸识别

![人脸识别](https://upload-images.jianshu.io/upload_images/11043770-ba4b31b0b8f4f645.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 数据化管理与监督
![数据管理监督](https://upload-images.jianshu.io/upload_images/11043770-866a0d61fc4ab5bb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 代码输入、输出   
### 人脸识别　　　

![例子](https://upload-images.jianshu.io/upload_images/11043770-ae680d8b7c658050.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 输入   
> import requests   
import json
subscription_key = 'key'
assert subscription_key
face_api_url = 'https://westcentralus.api.cognitive.microsoft.com/face/v1.0/detect'
image_url = 'http://qimg.hxnews.com/2019/0428/1556419954977.jpg'
headers = {'Ocp-Apim-Subscription-Key': subscription_key}
params = {
    'returnFaceId': 'true',
    'returnFaceLandmarks': 'false',
    'returnFaceAttributes': 'age,gender,headPose,smile,facialHair,glasses,emotion,hair,makeup,occlusion,accessories,blur,exposure,noise',
}
response = requests.post(face_api_url, params=params,
                         headers=headers, json={"url": image_url})
print(json.dumps(response.json()))

### 输出      
>[{"faceId": "77a3bd37-b63c-419a-97e5-2783a29101c3", "faceRectangle": {"top": 73, "left": 217, "width": 92, "height": 92}, "faceAttributes": {"smile": 0.0, "headPose": {"pitch": -17.5, "roll": -2.8, "yaw": -1.1}, "gender": "male", "age": 43.0, "facialHair": {"moustache": 0.6, "beard": 0.6, "sideburns": 0.1}, "glasses": "NoGlasses", "emotion": {"anger": 0.313, "contempt": 0.004, "disgust": 0.001, "fear": 0.0, "happiness": 0.0, "neutral": 0.677, "sadness": 0.001, "surprise": 0.002}, "blur": {"blurLevel": "low", "value": 0.05}, "exposure": {"exposureLevel": "goodExposure", "value": 0.38}, "noise": {"noiseLevel": "low", "value": 0.0}, "makeup": {"eyeMakeup": false, "lipMakeup": false}, "accessories": [], "occlusion": {"foreheadOccluded": false, "eyeOccluded": false, "mouthOccluded": false}, "hair": {"bald": 0.14, "invisible": false, "hairColor": [{"color": "black", "confidence": 1.0}, {"color": "gray", "confidence": 0.87}, {"color": "brown", "confidence": 0.53}, {"color": "other", "confidence": 0.47}, {"color": "blond", "confidence": 0.02}, {"color": "red", "confidence": 0.0}]}}}]   




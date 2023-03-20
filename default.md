# 博客api文档


**简介**:博客api文档


**HOST**:https://www.talkxj.com


**联系人**:风丶宇


**Version**:1.0


**接口路径**:/v2/api-docs


[TOC]






# 分类模块


## 查看后台分类列表


**接口地址**:`/admin/categories`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«CategoryBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«CategoryBackDTO»|PageResult«CategoryBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|CategoryBackDTO|
|&emsp;&emsp;&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;&emsp;&emsp;categoryName||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleCount": 0,
				"categoryName": "",
				"createTime": "",
				"id": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 添加或修改分类


**接口地址**:`/admin/categories`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "categoryName": "",
  "id": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|categoryVO|分类|body|true|CategoryVO|CategoryVO|
|&emsp;&emsp;categoryName|分类名||true|string||
|&emsp;&emsp;id|分类id||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除分类


**接口地址**:`/admin/categories`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|categoryIdList|categoryIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 搜索文章分类


**接口地址**:`/admin/categories/search`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«CategoryOptionDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|CategoryOptionDTO|
|&emsp;&emsp;categoryName||string||
|&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"categoryName": "",
			"id": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 查看分类列表


**接口地址**:`/categories`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«CategoryDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«CategoryDTO»|PageResult«CategoryDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|CategoryDTO|
|&emsp;&emsp;&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;&emsp;&emsp;categoryName||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleCount": 0,
				"categoryName": "",
				"id": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


# 博客信息模块


## 查看博客信息


**接口地址**:`/`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«BlogHomeInfoDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||BlogHomeInfoDTO|BlogHomeInfoDTO|
|&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;categoryCount||integer||
|&emsp;&emsp;pageList||array|PageVO|
|&emsp;&emsp;&emsp;&emsp;id|页面id|integer||
|&emsp;&emsp;&emsp;&emsp;pageCover|页面封面|string||
|&emsp;&emsp;&emsp;&emsp;pageLabel|页面标签|string||
|&emsp;&emsp;&emsp;&emsp;pageName|页面名称|string||
|&emsp;&emsp;tagCount||integer||
|&emsp;&emsp;viewsCount||string||
|&emsp;&emsp;websiteConfig||WebsiteConfigVO|WebsiteConfigVO|
|&emsp;&emsp;&emsp;&emsp;alipayQRCode|支付宝二维码|string||
|&emsp;&emsp;&emsp;&emsp;articleCover|文章封面|string||
|&emsp;&emsp;&emsp;&emsp;gitee|gitee|string||
|&emsp;&emsp;&emsp;&emsp;github|github|string||
|&emsp;&emsp;&emsp;&emsp;isChatRoom|是否打赏|integer||
|&emsp;&emsp;&emsp;&emsp;isCommentReview|是否评论审核|integer||
|&emsp;&emsp;&emsp;&emsp;isEmailNotice|是否邮箱通知|integer||
|&emsp;&emsp;&emsp;&emsp;isMessageReview|是否留言审核|integer||
|&emsp;&emsp;&emsp;&emsp;isMusicPlayer|是否开启音乐|integer||
|&emsp;&emsp;&emsp;&emsp;isReward|是否打赏|integer||
|&emsp;&emsp;&emsp;&emsp;qq|qq|string||
|&emsp;&emsp;&emsp;&emsp;socialLoginList|社交登录列表|array|string|
|&emsp;&emsp;&emsp;&emsp;socialUrlList|社交url列表|array|string|
|&emsp;&emsp;&emsp;&emsp;touristAvatar|游客头像|string||
|&emsp;&emsp;&emsp;&emsp;userAvatar|用户头像|string||
|&emsp;&emsp;&emsp;&emsp;websiteAuthor|网站作者|string||
|&emsp;&emsp;&emsp;&emsp;websiteAvatar|网站头像|string||
|&emsp;&emsp;&emsp;&emsp;websiteCreateTime|网站创建时间|string||
|&emsp;&emsp;&emsp;&emsp;websiteIntro|网站介绍|string||
|&emsp;&emsp;&emsp;&emsp;websiteName|网站名称|string||
|&emsp;&emsp;&emsp;&emsp;websiteNotice|网站公告|string||
|&emsp;&emsp;&emsp;&emsp;websiteRecordNo|网站备案号|string||
|&emsp;&emsp;&emsp;&emsp;websocketUrl|websocket地址|string||
|&emsp;&emsp;&emsp;&emsp;weiXinQRCode|微信二维码|string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleCount": 0,
		"categoryCount": 0,
		"pageList": [
			{
				"id": 0,
				"pageCover": "",
				"pageLabel": "",
				"pageName": ""
			}
		],
		"tagCount": 0,
		"viewsCount": "",
		"websiteConfig": {
			"alipayQRCode": "",
			"articleCover": "",
			"gitee": "",
			"github": "",
			"isChatRoom": 0,
			"isCommentReview": 0,
			"isEmailNotice": 0,
			"isMessageReview": 0,
			"isMusicPlayer": 0,
			"isReward": 0,
			"qq": "",
			"socialLoginList": [],
			"socialUrlList": [],
			"touristAvatar": "",
			"userAvatar": "",
			"websiteAuthor": "",
			"websiteAvatar": "",
			"websiteCreateTime": "",
			"websiteIntro": "",
			"websiteName": "",
			"websiteNotice": "",
			"websiteRecordNo": "",
			"websocketUrl": "",
			"weiXinQRCode": ""
		}
	},
	"flag": true,
	"message": ""
}
```


## 查看关于我信息


**接口地址**:`/about`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 查看后台信息


**接口地址**:`/admin`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«BlogBackInfoDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||BlogBackInfoDTO|BlogBackInfoDTO|
|&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;articleRankDTOList||array|ArticleRankDTO|
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;viewsCount||integer||
|&emsp;&emsp;articleStatisticsList||array|ArticleStatisticsDTO|
|&emsp;&emsp;&emsp;&emsp;count||integer||
|&emsp;&emsp;&emsp;&emsp;date||string||
|&emsp;&emsp;categoryDTOList||array|CategoryDTO|
|&emsp;&emsp;&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;&emsp;&emsp;categoryName||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;messageCount||integer||
|&emsp;&emsp;tagDTOList||array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagName||string||
|&emsp;&emsp;uniqueViewDTOList||array|UniqueViewDTO|
|&emsp;&emsp;&emsp;&emsp;day||string||
|&emsp;&emsp;&emsp;&emsp;viewsCount||integer||
|&emsp;&emsp;userCount||integer||
|&emsp;&emsp;viewsCount||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleCount": 0,
		"articleRankDTOList": [
			{
				"articleTitle": "",
				"viewsCount": 0
			}
		],
		"articleStatisticsList": [
			{
				"count": 0,
				"date": ""
			}
		],
		"categoryDTOList": [
			{
				"articleCount": 0,
				"categoryName": "",
				"id": 0
			}
		],
		"messageCount": 0,
		"tagDTOList": [
			{
				"id": 0,
				"tagName": ""
			}
		],
		"uniqueViewDTOList": [
			{
				"day": "",
				"viewsCount": 0
			}
		],
		"userCount": 0,
		"viewsCount": 0
	},
	"flag": true,
	"message": ""
}
```


## 修改关于我信息


**接口地址**:`/admin/about`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "aboutContent": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|blogInfoVO|博客信息|body|true|BlogInfoVO|BlogInfoVO|
|&emsp;&emsp;aboutContent|关于我内容||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 上传博客配置图片


**接口地址**:`/admin/config/images`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|图片|formData|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 获取网站配置


**接口地址**:`/admin/website/config`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«WebsiteConfigVO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||WebsiteConfigVO|WebsiteConfigVO|
|&emsp;&emsp;alipayQRCode|支付宝二维码|string||
|&emsp;&emsp;articleCover|文章封面|string||
|&emsp;&emsp;gitee|gitee|string||
|&emsp;&emsp;github|github|string||
|&emsp;&emsp;isChatRoom|是否打赏|integer||
|&emsp;&emsp;isCommentReview|是否评论审核|integer||
|&emsp;&emsp;isEmailNotice|是否邮箱通知|integer||
|&emsp;&emsp;isMessageReview|是否留言审核|integer||
|&emsp;&emsp;isMusicPlayer|是否开启音乐|integer||
|&emsp;&emsp;isReward|是否打赏|integer||
|&emsp;&emsp;qq|qq|string||
|&emsp;&emsp;socialLoginList|社交登录列表|array|string|
|&emsp;&emsp;socialUrlList|社交url列表|array|string|
|&emsp;&emsp;touristAvatar|游客头像|string||
|&emsp;&emsp;userAvatar|用户头像|string||
|&emsp;&emsp;websiteAuthor|网站作者|string||
|&emsp;&emsp;websiteAvatar|网站头像|string||
|&emsp;&emsp;websiteCreateTime|网站创建时间|string||
|&emsp;&emsp;websiteIntro|网站介绍|string||
|&emsp;&emsp;websiteName|网站名称|string||
|&emsp;&emsp;websiteNotice|网站公告|string||
|&emsp;&emsp;websiteRecordNo|网站备案号|string||
|&emsp;&emsp;websocketUrl|websocket地址|string||
|&emsp;&emsp;weiXinQRCode|微信二维码|string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"alipayQRCode": "",
		"articleCover": "",
		"gitee": "",
		"github": "",
		"isChatRoom": 0,
		"isCommentReview": 0,
		"isEmailNotice": 0,
		"isMessageReview": 0,
		"isMusicPlayer": 0,
		"isReward": 0,
		"qq": "",
		"socialLoginList": [],
		"socialUrlList": [],
		"touristAvatar": "",
		"userAvatar": "",
		"websiteAuthor": "",
		"websiteAvatar": "",
		"websiteCreateTime": "",
		"websiteIntro": "",
		"websiteName": "",
		"websiteNotice": "",
		"websiteRecordNo": "",
		"websocketUrl": "",
		"weiXinQRCode": ""
	},
	"flag": true,
	"message": ""
}
```


## 更新网站配置


**接口地址**:`/admin/website/config`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "alipayQRCode": "",
  "articleCover": "",
  "gitee": "",
  "github": "",
  "isChatRoom": 0,
  "isCommentReview": 0,
  "isEmailNotice": 0,
  "isMessageReview": 0,
  "isMusicPlayer": 0,
  "isReward": 0,
  "qq": "",
  "socialLoginList": [],
  "socialUrlList": [],
  "touristAvatar": "",
  "userAvatar": "",
  "websiteAuthor": "",
  "websiteAvatar": "",
  "websiteCreateTime": "",
  "websiteIntro": "",
  "websiteName": "",
  "websiteNotice": "",
  "websiteRecordNo": "",
  "websocketUrl": "",
  "weiXinQRCode": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|websiteConfigVO|网站配置|body|true|WebsiteConfigVO|WebsiteConfigVO|
|&emsp;&emsp;alipayQRCode|支付宝二维码||true|string||
|&emsp;&emsp;articleCover|文章封面||true|string||
|&emsp;&emsp;gitee|gitee||true|string||
|&emsp;&emsp;github|github||true|string||
|&emsp;&emsp;isChatRoom|是否打赏||true|integer||
|&emsp;&emsp;isCommentReview|是否评论审核||true|integer||
|&emsp;&emsp;isEmailNotice|是否邮箱通知||true|integer||
|&emsp;&emsp;isMessageReview|是否留言审核||true|integer||
|&emsp;&emsp;isMusicPlayer|是否开启音乐||true|integer||
|&emsp;&emsp;isReward|是否打赏||true|integer||
|&emsp;&emsp;qq|qq||true|string||
|&emsp;&emsp;socialLoginList|社交登录列表||true|array|string|
|&emsp;&emsp;socialUrlList|社交url列表||true|array|string|
|&emsp;&emsp;touristAvatar|游客头像||true|string||
|&emsp;&emsp;userAvatar|用户头像||true|string||
|&emsp;&emsp;websiteAuthor|网站作者||true|string||
|&emsp;&emsp;websiteAvatar|网站头像||true|string||
|&emsp;&emsp;websiteCreateTime|网站创建时间||true|string||
|&emsp;&emsp;websiteIntro|网站介绍||true|string||
|&emsp;&emsp;websiteName|网站名称||true|string||
|&emsp;&emsp;websiteNotice|网站公告||true|string||
|&emsp;&emsp;websiteRecordNo|网站备案号||true|string||
|&emsp;&emsp;websocketUrl|websocket地址||true|string||
|&emsp;&emsp;weiXinQRCode|微信二维码||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## report


**接口地址**:`/report`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 上传语音


**接口地址**:`/voice`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|avatar|用户头像|query|true|string||
|content|聊天内容|query|true|string||
|createTime|创建时间|query|true|string(date-time)||
|file|文件|query|true|file||
|ipAddress|用户登录ip|query|true|string||
|ipSource|ip来源|query|true|string||
|nickname|用户昵称|query|true|string||
|type|消息类型|query|true|integer(int32)||
|userId|用户id|query|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


# 友链模块


## 查看后台友链列表


**接口地址**:`/admin/links`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«FriendLinkBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«FriendLinkBackDTO»|PageResult«FriendLinkBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|FriendLinkBackDTO|
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;linkAddress||string||
|&emsp;&emsp;&emsp;&emsp;linkAvatar||string||
|&emsp;&emsp;&emsp;&emsp;linkIntro||string||
|&emsp;&emsp;&emsp;&emsp;linkName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"createTime": "",
				"id": 0,
				"linkAddress": "",
				"linkAvatar": "",
				"linkIntro": "",
				"linkName": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 保存或修改友链


**接口地址**:`/admin/links`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "linkAddress": "",
  "linkAvatar": "",
  "linkIntro": "",
  "linkName": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|friendLinkVO|友链|body|true|FriendLinkVO|FriendLinkVO|
|&emsp;&emsp;id|友链id||false|integer||
|&emsp;&emsp;linkAddress|友链头像||true|string||
|&emsp;&emsp;linkAvatar|友链头像||true|string||
|&emsp;&emsp;linkIntro|友链头像||true|string||
|&emsp;&emsp;linkName|友链名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除友链


**接口地址**:`/admin/links`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|linkIdList|linkIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查看友链列表


**接口地址**:`/links`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«FriendLinkDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|FriendLinkDTO|
|&emsp;&emsp;id||integer||
|&emsp;&emsp;linkAddress||string||
|&emsp;&emsp;linkAvatar||string||
|&emsp;&emsp;linkIntro||string||
|&emsp;&emsp;linkName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"id": 0,
			"linkAddress": "",
			"linkAvatar": "",
			"linkIntro": "",
			"linkName": ""
		}
	],
	"flag": true,
	"message": ""
}
```


# 文章模块


## 查看后台文章


**接口地址**:`/admin/articles`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«ArticleBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«ArticleBackDTO»|PageResult«ArticleBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|ArticleBackDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;categoryName||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;isDelete||integer||
|&emsp;&emsp;&emsp;&emsp;isTop||integer||
|&emsp;&emsp;&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;&emsp;&emsp;status||integer||
|&emsp;&emsp;&emsp;&emsp;tagDTOList||array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;tagName||string||
|&emsp;&emsp;&emsp;&emsp;type||integer||
|&emsp;&emsp;&emsp;&emsp;viewsCount||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleCover": "",
				"articleTitle": "",
				"categoryName": "",
				"createTime": "",
				"id": 0,
				"isDelete": 0,
				"isTop": 0,
				"likeCount": 0,
				"status": 0,
				"tagDTOList": [
					{
						"id": 0,
						"tagName": ""
					}
				],
				"type": 0,
				"viewsCount": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 添加或修改文章


**接口地址**:`/admin/articles`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "articleContent": "",
  "articleCover": "",
  "articleTitle": "",
  "categoryName": "",
  "id": 0,
  "isTop": 0,
  "originalUrl": "",
  "status": 0,
  "tagNameList": [],
  "type": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleVO|文章|body|true|ArticleVO|ArticleVO|
|&emsp;&emsp;articleContent|文章内容||true|string||
|&emsp;&emsp;articleCover|文章缩略图||false|string||
|&emsp;&emsp;articleTitle|文章标题||true|string||
|&emsp;&emsp;categoryName|文章分类||false|string||
|&emsp;&emsp;id|文章id||false|integer||
|&emsp;&emsp;isTop|是否置顶||false|integer||
|&emsp;&emsp;originalUrl|原文链接||false|string||
|&emsp;&emsp;status|文章状态||false|integer||
|&emsp;&emsp;tagNameList|文章标签||false|array|string|
|&emsp;&emsp;type|文章类型||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 恢复或删除文章


**接口地址**:`/admin/articles`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "idList": [],
  "isDelete": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|deleteVO|逻辑删除|body|true|DeleteVO|DeleteVO|
|&emsp;&emsp;idList|id列表||true|array|integer|
|&emsp;&emsp;isDelete|删除状态||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 物理删除文章


**接口地址**:`/admin/articles`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleIdList|articleIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 导出文章


**接口地址**:`/admin/articles/export`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleIdList|文章id|body|true|List<Integer>|List<Integer>|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«string»»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [],
	"flag": true,
	"message": ""
}
```


## 上传文章图片


**接口地址**:`/admin/articles/images`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|文章图片|formData|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 导入文章


**接口地址**:`/admin/articles/import`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|file|formData|false|file||
|type|type|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 修改文章置顶


**接口地址**:`/admin/articles/top`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "isTop": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleTopVO|文章置顶|body|true|ArticleTopVO|ArticleTopVO|
|&emsp;&emsp;id|||false|integer||
|&emsp;&emsp;isTop|||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 根据id查看后台文章


**接口地址**:`/admin/articles/{articleId}`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleId|文章id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«ArticleVO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||ArticleVO|ArticleVO|
|&emsp;&emsp;articleContent|文章内容|string||
|&emsp;&emsp;articleCover|文章缩略图|string||
|&emsp;&emsp;articleTitle|文章标题|string||
|&emsp;&emsp;categoryName|文章分类|string||
|&emsp;&emsp;id|文章id|integer||
|&emsp;&emsp;isTop|是否置顶|integer||
|&emsp;&emsp;originalUrl|原文链接|string||
|&emsp;&emsp;status|文章状态|integer||
|&emsp;&emsp;tagNameList|文章标签|array|string|
|&emsp;&emsp;type|文章类型|integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleContent": "",
		"articleCover": "",
		"articleTitle": "",
		"categoryName": "",
		"id": 0,
		"isTop": 0,
		"originalUrl": "",
		"status": 0,
		"tagNameList": [],
		"type": 0
	},
	"flag": true,
	"message": ""
}
```


## 查看首页文章


**接口地址**:`/articles`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«ArticleHomeDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|ArticleHomeDTO|
|&emsp;&emsp;articleContent||string||
|&emsp;&emsp;articleCover||string||
|&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;categoryId||integer||
|&emsp;&emsp;categoryName||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;isTop||integer||
|&emsp;&emsp;tagDTOList||array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagName||string||
|&emsp;&emsp;type||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"articleContent": "",
			"articleCover": "",
			"articleTitle": "",
			"categoryId": 0,
			"categoryName": "",
			"createTime": "",
			"id": 0,
			"isTop": 0,
			"tagDTOList": [
				{
					"id": 0,
					"tagName": ""
				}
			],
			"type": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 查看文章归档


**接口地址**:`/articles/archives`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«ArchiveDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«ArchiveDTO»|PageResult«ArchiveDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|ArchiveDTO|
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleTitle": "",
				"createTime": "",
				"id": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 根据条件查询文章


**接口地址**:`/articles/condition`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«ArticlePreviewListDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||ArticlePreviewListDTO|ArticlePreviewListDTO|
|&emsp;&emsp;articlePreviewDTOList||array|ArticlePreviewDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;categoryId||integer||
|&emsp;&emsp;&emsp;&emsp;categoryName||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagDTOList||array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;tagName||string||
|&emsp;&emsp;name||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articlePreviewDTOList": [
			{
				"articleCover": "",
				"articleTitle": "",
				"categoryId": 0,
				"categoryName": "",
				"createTime": "",
				"id": 0,
				"tagDTOList": [
					{
						"id": 0,
						"tagName": ""
					}
				]
			}
		],
		"name": ""
	},
	"flag": true,
	"message": ""
}
```


## 搜索文章


**接口地址**:`/articles/search`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«ArticleSearchDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|ArticleSearchDTO|
|&emsp;&emsp;articleContent||string||
|&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;isDelete||integer||
|&emsp;&emsp;status||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"articleContent": "",
			"articleTitle": "",
			"id": 0,
			"isDelete": 0,
			"status": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 根据id查看文章


**接口地址**:`/articles/{articleId}`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleId|文章id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«ArticleDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||ArticleDTO|ArticleDTO|
|&emsp;&emsp;articleContent||string||
|&emsp;&emsp;articleCover||string||
|&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;categoryId||integer||
|&emsp;&emsp;categoryName||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;lastArticle||ArticlePaginationDTO|ArticlePaginationDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;newestArticleList||array|ArticleRecommendDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;nextArticle||ArticlePaginationDTO|ArticlePaginationDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;originalUrl||string||
|&emsp;&emsp;recommendArticleList||array|ArticleRecommendDTO|
|&emsp;&emsp;&emsp;&emsp;articleCover||string||
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;tagDTOList||array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagName||string||
|&emsp;&emsp;type||integer||
|&emsp;&emsp;updateTime||string||
|&emsp;&emsp;viewsCount||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleContent": "",
		"articleCover": "",
		"articleTitle": "",
		"categoryId": 0,
		"categoryName": "",
		"createTime": "",
		"id": 0,
		"lastArticle": {
			"articleCover": "",
			"articleTitle": "",
			"id": 0
		},
		"likeCount": 0,
		"newestArticleList": [
			{
				"articleCover": "",
				"articleTitle": "",
				"createTime": "",
				"id": 0
			}
		],
		"nextArticle": {
			"articleCover": "",
			"articleTitle": "",
			"id": 0
		},
		"originalUrl": "",
		"recommendArticleList": [
			{
				"articleCover": "",
				"articleTitle": "",
				"createTime": "",
				"id": 0
			}
		],
		"tagDTOList": [
			{
				"id": 0,
				"tagName": ""
			}
		],
		"type": 0,
		"updateTime": "",
		"viewsCount": 0
	},
	"flag": true,
	"message": ""
}
```


## 点赞文章


**接口地址**:`/articles/{articleId}/like`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|articleId|文章id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 日志模块


## 查看操作日志


**接口地址**:`/admin/operation/logs`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«OperationLogDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«OperationLogDTO»|PageResult«OperationLogDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|OperationLogDTO|
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;&emsp;&emsp;ipSource||string||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;optDesc||string||
|&emsp;&emsp;&emsp;&emsp;optMethod||string||
|&emsp;&emsp;&emsp;&emsp;optModule||string||
|&emsp;&emsp;&emsp;&emsp;optType||string||
|&emsp;&emsp;&emsp;&emsp;optUrl||string||
|&emsp;&emsp;&emsp;&emsp;requestMethod||string||
|&emsp;&emsp;&emsp;&emsp;requestParam||string||
|&emsp;&emsp;&emsp;&emsp;responseData||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"createTime": "",
				"id": 0,
				"ipAddress": "",
				"ipSource": "",
				"nickname": "",
				"optDesc": "",
				"optMethod": "",
				"optModule": "",
				"optType": "",
				"optUrl": "",
				"requestMethod": "",
				"requestParam": "",
				"responseData": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 删除操作日志


**接口地址**:`/admin/operation/logs`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|logIdList|logIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 标签模块


## 查询后台标签列表


**接口地址**:`/admin/tags`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«TagBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«TagBackDTO»|PageResult«TagBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|TagBackDTO|
|&emsp;&emsp;&emsp;&emsp;articleCount||integer||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleCount": 0,
				"createTime": "",
				"id": 0,
				"tagName": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 添加或修改标签


**接口地址**:`/admin/tags`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "tagName": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|tagVO|标签对象|body|true|TagVO|TagVO|
|&emsp;&emsp;id|标签id||false|integer||
|&emsp;&emsp;tagName|标签名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除标签


**接口地址**:`/admin/tags`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|tagIdList|tagIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 搜索文章标签


**接口地址**:`/admin/tags/search`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«TagDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|TagDTO|
|&emsp;&emsp;id||integer||
|&emsp;&emsp;tagName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"id": 0,
			"tagName": ""
		}
	],
	"flag": true,
	"message": ""
}
```


## 查询标签列表


**接口地址**:`/tags`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«TagDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«TagDTO»|PageResult«TagDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|TagDTO|
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;tagName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"id": 0,
				"tagName": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


# 照片模块


## 根据相册id获取照片列表


**接口地址**:`/admin/photos`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«PhotoBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«PhotoBackDTO»|PageResult«PhotoBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|PhotoBackDTO|
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;photoDesc||string||
|&emsp;&emsp;&emsp;&emsp;photoName||string||
|&emsp;&emsp;&emsp;&emsp;photoSrc||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"id": 0,
				"photoDesc": "",
				"photoName": "",
				"photoSrc": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 保存照片


**接口地址**:`/admin/photos`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "albumId": 0,
  "photoIdList": [],
  "photoUrlList": []
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|photoVO|照片|body|true|PhotoVO|PhotoVO|
|&emsp;&emsp;albumId|相册id||true|integer||
|&emsp;&emsp;photoIdList|照片id列表||true|array|integer|
|&emsp;&emsp;photoUrlList|照片列表||true|array|string|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 更新照片信息


**接口地址**:`/admin/photos`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "photoDesc": "",
  "photoName": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|photoInfoVO|照片信息|body|true|PhotoInfoVO|PhotoInfoVO|
|&emsp;&emsp;id|照片id||true|integer||
|&emsp;&emsp;photoDesc|照片描述||false|string||
|&emsp;&emsp;photoName|照片名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除照片


**接口地址**:`/admin/photos`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|photoIdList|photoIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 移动照片相册


**接口地址**:`/admin/photos/album`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "albumId": 0,
  "photoIdList": [],
  "photoUrlList": []
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|photoVO|照片|body|true|PhotoVO|PhotoVO|
|&emsp;&emsp;albumId|相册id||true|integer||
|&emsp;&emsp;photoIdList|照片id列表||true|array|integer|
|&emsp;&emsp;photoUrlList|照片列表||true|array|string|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 更新照片删除状态


**接口地址**:`/admin/photos/delete`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "idList": [],
  "isDelete": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|deleteVO|逻辑删除|body|true|DeleteVO|DeleteVO|
|&emsp;&emsp;idList|id列表||true|array|integer|
|&emsp;&emsp;isDelete|删除状态||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 根据相册id查看照片列表


**接口地址**:`/albums/{albumId}/photos`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|albumId|path|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PhotoDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PhotoDTO|PhotoDTO|
|&emsp;&emsp;photoAlbumCover||string||
|&emsp;&emsp;photoAlbumName||string||
|&emsp;&emsp;photoList||array|string|
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"photoAlbumCover": "",
		"photoAlbumName": "",
		"photoList": []
	},
	"flag": true,
	"message": ""
}
```


# 用户信息模块


## 修改用户禁用状态


**接口地址**:`/admin/users/disable`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "isDisable": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userDisableVO|用户禁用状态|body|true|UserDisableVO|UserDisableVO|
|&emsp;&emsp;id|||false|integer||
|&emsp;&emsp;isDisable|||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查看在线用户


**接口地址**:`/admin/users/online`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«UserOnlineDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«UserOnlineDTO»|PageResult«UserOnlineDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|UserOnlineDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;browser||string||
|&emsp;&emsp;&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;&emsp;&emsp;ipSource||string||
|&emsp;&emsp;&emsp;&emsp;lastLoginTime||string||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;os||string||
|&emsp;&emsp;&emsp;&emsp;userInfoId||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"browser": "",
				"ipAddress": "",
				"ipSource": "",
				"lastLoginTime": "",
				"nickname": "",
				"os": "",
				"userInfoId": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 修改用户角色


**接口地址**:`/admin/users/role`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "nickname": "",
  "roleIdList": [],
  "userInfoId": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userRoleVO|用户权限|body|true|UserRoleVO|UserRoleVO|
|&emsp;&emsp;nickname|昵称||false|string||
|&emsp;&emsp;roleIdList|角色id集合||false|array|integer|
|&emsp;&emsp;userInfoId|用户信息id||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 下线用户


**接口地址**:`/admin/users/{userInfoId}/online`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userInfoId|userInfoId|path|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 更新用户头像


**接口地址**:`/users/avatar`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|用户头像|formData|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 绑定用户邮箱


**接口地址**:`/users/email`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "code": "",
  "email": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|emailVO|绑定邮箱|body|true|EmailVO|EmailVO|
|&emsp;&emsp;code|邮箱验证码||true|string||
|&emsp;&emsp;email|用户名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 更新用户信息


**接口地址**:`/users/info`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "intro": "",
  "nickname": "",
  "webSite": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userInfoVO|用户信息对象|body|true|UserInfoVO|UserInfoVO|
|&emsp;&emsp;intro|介绍||false|string||
|&emsp;&emsp;nickname|昵称||false|string||
|&emsp;&emsp;webSite|个人网站||false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 用户账号模块


## 查询后台用户列表


**接口地址**:`/admin/users`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«UserBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«UserBackDTO»|PageResult«UserBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|UserBackDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;&emsp;&emsp;ipSource||string||
|&emsp;&emsp;&emsp;&emsp;isDisable||integer||
|&emsp;&emsp;&emsp;&emsp;lastLoginTime||string||
|&emsp;&emsp;&emsp;&emsp;loginType||integer||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;roleList||array|UserRoleDTO|
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;roleName||string||
|&emsp;&emsp;&emsp;&emsp;status||integer||
|&emsp;&emsp;&emsp;&emsp;userInfoId||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"createTime": "",
				"id": 0,
				"ipAddress": "",
				"ipSource": "",
				"isDisable": 0,
				"lastLoginTime": "",
				"loginType": 0,
				"nickname": "",
				"roleList": [
					{
						"id": 0,
						"roleName": ""
					}
				],
				"status": 0,
				"userInfoId": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 获取用户区域分布


**接口地址**:`/admin/users/area`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«UserAreaDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|UserAreaDTO|
|&emsp;&emsp;name||string||
|&emsp;&emsp;value||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"name": "",
			"value": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 修改管理员密码


**接口地址**:`/admin/users/password`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "newPassword": "",
  "oldPassword": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|passwordVO|密码|body|true|PasswordVO|PasswordVO|
|&emsp;&emsp;newPassword|新密码||true|string||
|&emsp;&emsp;oldPassword|旧密码||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 用户注册


**接口地址**:`/register`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "code": "",
  "password": "",
  "username": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|user|用户账号|body|true|UserVO|UserVO|
|&emsp;&emsp;code|邮箱验证码||true|string||
|&emsp;&emsp;password|密码||true|string||
|&emsp;&emsp;username|用户名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 发送邮箱验证码


**接口地址**:`/users/code`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|username|用户名|query|true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## qq登录


**接口地址**:`/users/oauth/qq`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "accessToken": "",
  "openId": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|qqLoginVO|qq登录信息|body|true|QQLoginVO|QQLoginVO|
|&emsp;&emsp;accessToken|qq accessToken||true|string||
|&emsp;&emsp;openId|qq openId||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«UserInfoDTO»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||UserInfoDTO|UserInfoDTO|
|&emsp;&emsp;articleLikeSet||array|object|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;commentLikeSet||array|object|
|&emsp;&emsp;email||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;intro||string||
|&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;ipSource||string||
|&emsp;&emsp;lastLoginTime||string||
|&emsp;&emsp;loginType||integer||
|&emsp;&emsp;nickname||string||
|&emsp;&emsp;talkLikeSet||array|object|
|&emsp;&emsp;userInfoId||integer||
|&emsp;&emsp;username||string||
|&emsp;&emsp;webSite||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleLikeSet": [],
		"avatar": "",
		"commentLikeSet": [],
		"email": "",
		"id": 0,
		"intro": "",
		"ipAddress": "",
		"ipSource": "",
		"lastLoginTime": "",
		"loginType": 0,
		"nickname": "",
		"talkLikeSet": [],
		"userInfoId": 0,
		"username": "",
		"webSite": ""
	},
	"flag": true,
	"message": ""
}
```


## 微博登录


**接口地址**:`/users/oauth/weibo`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "code": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|weiBoLoginVO|weiBoLoginVO|body|true|WeiboLoginVO|WeiboLoginVO|
|&emsp;&emsp;code|qq openId||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«UserInfoDTO»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||UserInfoDTO|UserInfoDTO|
|&emsp;&emsp;articleLikeSet||array|object|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;commentLikeSet||array|object|
|&emsp;&emsp;email||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;intro||string||
|&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;ipSource||string||
|&emsp;&emsp;lastLoginTime||string||
|&emsp;&emsp;loginType||integer||
|&emsp;&emsp;nickname||string||
|&emsp;&emsp;talkLikeSet||array|object|
|&emsp;&emsp;userInfoId||integer||
|&emsp;&emsp;username||string||
|&emsp;&emsp;webSite||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"articleLikeSet": [],
		"avatar": "",
		"commentLikeSet": [],
		"email": "",
		"id": 0,
		"intro": "",
		"ipAddress": "",
		"ipSource": "",
		"lastLoginTime": "",
		"loginType": 0,
		"nickname": "",
		"talkLikeSet": [],
		"userInfoId": 0,
		"username": "",
		"webSite": ""
	},
	"flag": true,
	"message": ""
}
```


## 修改密码


**接口地址**:`/users/password`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "code": "",
  "password": "",
  "username": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|user|用户账号|body|true|UserVO|UserVO|
|&emsp;&emsp;code|邮箱验证码||true|string||
|&emsp;&emsp;password|密码||true|string||
|&emsp;&emsp;username|用户名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 留言模块


## 查看后台留言列表


**接口地址**:`/admin/messages`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«MessageBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«MessageBackDTO»|PageResult«MessageBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|MessageBackDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;ipAddress||string||
|&emsp;&emsp;&emsp;&emsp;ipSource||string||
|&emsp;&emsp;&emsp;&emsp;isReview||integer||
|&emsp;&emsp;&emsp;&emsp;messageContent||string||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"createTime": "",
				"id": 0,
				"ipAddress": "",
				"ipSource": "",
				"isReview": 0,
				"messageContent": "",
				"nickname": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 删除留言


**接口地址**:`/admin/messages`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|messageIdList|messageIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 审核留言


**接口地址**:`/admin/messages/review`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "idList": [],
  "isReview": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|reviewVO|审核|body|true|ReviewVO|ReviewVO|
|&emsp;&emsp;idList|id列表||true|array|integer|
|&emsp;&emsp;isReview|删除状态||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查看留言列表


**接口地址**:`/messages`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«MessageDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|MessageDTO|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;messageContent||string||
|&emsp;&emsp;nickname||string||
|&emsp;&emsp;time||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"avatar": "",
			"id": 0,
			"messageContent": "",
			"nickname": "",
			"time": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 添加留言


**接口地址**:`/messages`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "avatar": "",
  "messageContent": "",
  "nickname": "",
  "time": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|messageVO|留言|body|true|MessageVO|MessageVO|
|&emsp;&emsp;avatar|头像||true|string||
|&emsp;&emsp;messageContent|留言内容||true|string||
|&emsp;&emsp;nickname|昵称||true|string||
|&emsp;&emsp;time|弹幕速度||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 相册模块


## 查看后台相册列表


**接口地址**:`/admin/photos/albums`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«PhotoAlbumBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«PhotoAlbumBackDTO»|PageResult«PhotoAlbumBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|PhotoAlbumBackDTO|
|&emsp;&emsp;&emsp;&emsp;albumCover||string||
|&emsp;&emsp;&emsp;&emsp;albumDesc||string||
|&emsp;&emsp;&emsp;&emsp;albumName||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;photoCount||integer||
|&emsp;&emsp;&emsp;&emsp;status||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"albumCover": "",
				"albumDesc": "",
				"albumName": "",
				"id": 0,
				"photoCount": 0,
				"status": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 保存或更新相册


**接口地址**:`/admin/photos/albums`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "albumCover": "",
  "albumDesc": "",
  "albumName": "",
  "id": 0,
  "status": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|photoAlbumVO|相册|body|true|PhotoAlbumVO|PhotoAlbumVO|
|&emsp;&emsp;albumCover|相册封面||true|string||
|&emsp;&emsp;albumDesc|相册描述||false|string||
|&emsp;&emsp;albumName|相册名||true|string||
|&emsp;&emsp;id|相册id||true|integer||
|&emsp;&emsp;status|状态值||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 上传相册封面


**接口地址**:`/admin/photos/albums/cover`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|相册封面|formData|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 获取后台相册列表信息


**接口地址**:`/admin/photos/albums/info`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«PhotoAlbumDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|PhotoAlbumDTO|
|&emsp;&emsp;albumCover||string||
|&emsp;&emsp;albumDesc||string||
|&emsp;&emsp;albumName||string||
|&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"albumCover": "",
			"albumDesc": "",
			"albumName": "",
			"id": 0
		}
	],
	"flag": true,
	"message": ""
}
```


## 根据id删除相册


**接口地址**:`/admin/photos/albums/{albumId}`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 根据id获取后台相册信息


**接口地址**:`/admin/photos/albums/{albumId}/info`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PhotoAlbumBackDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PhotoAlbumBackDTO|PhotoAlbumBackDTO|
|&emsp;&emsp;albumCover||string||
|&emsp;&emsp;albumDesc||string||
|&emsp;&emsp;albumName||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;photoCount||integer||
|&emsp;&emsp;status||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"albumCover": "",
		"albumDesc": "",
		"albumName": "",
		"id": 0,
		"photoCount": 0,
		"status": 0
	},
	"flag": true,
	"message": ""
}
```


## 获取相册列表


**接口地址**:`/photos/albums`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«PhotoAlbumDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|PhotoAlbumDTO|
|&emsp;&emsp;albumCover||string||
|&emsp;&emsp;albumDesc||string||
|&emsp;&emsp;albumName||string||
|&emsp;&emsp;id||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"albumCover": "",
			"albumDesc": "",
			"albumName": "",
			"id": 0
		}
	],
	"flag": true,
	"message": ""
}
```


# 菜单模块


## 查看菜单列表


**接口地址**:`/admin/menus`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«MenuDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|MenuDTO|
|&emsp;&emsp;children||array|MenuDTO|
|&emsp;&emsp;component||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;icon||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;isDisable||integer||
|&emsp;&emsp;isHidden||integer||
|&emsp;&emsp;name||string||
|&emsp;&emsp;orderNum||integer||
|&emsp;&emsp;path||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"children": [
				{
					"children": [
						{}
					],
					"component": "",
					"createTime": "",
					"icon": "",
					"id": 0,
					"isDisable": 0,
					"isHidden": 0,
					"name": "",
					"orderNum": 0,
					"path": ""
				}
			],
			"component": "",
			"createTime": "",
			"icon": "",
			"id": 0,
			"isDisable": 0,
			"isHidden": 0,
			"name": "",
			"orderNum": 0,
			"path": ""
		}
	],
	"flag": true,
	"message": ""
}
```


## 新增或修改菜单


**接口地址**:`/admin/menus`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "component": "",
  "icon": "",
  "id": 0,
  "isHidden": 0,
  "name": "",
  "orderNum": 0,
  "parentId": 0,
  "path": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|menuVO|菜单|body|true|MenuVO|MenuVO|
|&emsp;&emsp;component|组件||false|string||
|&emsp;&emsp;icon|菜单icon||false|string||
|&emsp;&emsp;id|菜单id||false|integer||
|&emsp;&emsp;isHidden|是否隐藏||false|integer||
|&emsp;&emsp;name|菜单名||false|string||
|&emsp;&emsp;orderNum|排序||false|integer||
|&emsp;&emsp;parentId|父id||false|integer||
|&emsp;&emsp;path|路径||false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除菜单


**接口地址**:`/admin/menus/{menuId}`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|menuId|menuId|path|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查看角色菜单选项


**接口地址**:`/admin/role/menus`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«LabelOptionDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|LabelOptionDTO|
|&emsp;&emsp;children||array|LabelOptionDTO|
|&emsp;&emsp;id||integer||
|&emsp;&emsp;label||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"children": [
				{
					"children": [
						{}
					],
					"id": 0,
					"label": ""
				}
			],
			"id": 0,
			"label": ""
		}
	],
	"flag": true,
	"message": ""
}
```


## 查看当前用户菜单


**接口地址**:`/admin/user/menus`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«UserMenuDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|UserMenuDTO|
|&emsp;&emsp;children||array|UserMenuDTO|
|&emsp;&emsp;component||string||
|&emsp;&emsp;hidden||boolean||
|&emsp;&emsp;icon||string||
|&emsp;&emsp;name||string||
|&emsp;&emsp;path||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"children": [
				{
					"children": [
						{}
					],
					"component": "",
					"hidden": true,
					"icon": "",
					"name": "",
					"path": ""
				}
			],
			"component": "",
			"hidden": true,
			"icon": "",
			"name": "",
			"path": ""
		}
	],
	"flag": true,
	"message": ""
}
```


# 角色模块


## 保存或更新角色


**接口地址**:`/admin/role`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "menuIdList": [],
  "resourceIdList": [],
  "roleLabel": "",
  "roleName": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|roleVO|角色|body|true|RoleVO|RoleVO|
|&emsp;&emsp;id|用户id||false|integer||
|&emsp;&emsp;menuIdList|菜单列表||true|array|integer|
|&emsp;&emsp;resourceIdList|资源列表||true|array|integer|
|&emsp;&emsp;roleLabel|标签名||true|string||
|&emsp;&emsp;roleName|角色名||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查询角色列表


**接口地址**:`/admin/roles`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«RoleDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«RoleDTO»|PageResult«RoleDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|RoleDTO|
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;isDisable||integer||
|&emsp;&emsp;&emsp;&emsp;menuIdList||array|integer|
|&emsp;&emsp;&emsp;&emsp;resourceIdList||array|integer|
|&emsp;&emsp;&emsp;&emsp;roleLabel||string||
|&emsp;&emsp;&emsp;&emsp;roleName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"createTime": "",
				"id": 0,
				"isDisable": 0,
				"menuIdList": [],
				"resourceIdList": [],
				"roleLabel": "",
				"roleName": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 删除角色


**接口地址**:`/admin/roles`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|roleIdList|roleIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查询用户角色选项


**接口地址**:`/admin/users/role`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«UserRoleDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|UserRoleDTO|
|&emsp;&emsp;id||integer||
|&emsp;&emsp;roleName||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"id": 0,
			"roleName": ""
		}
	],
	"flag": true,
	"message": ""
}
```


# 评论模块


## 查询后台评论


**接口地址**:`/admin/comments`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«CommentBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«CommentBackDTO»|PageResult«CommentBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|CommentBackDTO|
|&emsp;&emsp;&emsp;&emsp;articleTitle||string||
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;commentContent||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;isReview||integer||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;replyNickname||string||
|&emsp;&emsp;&emsp;&emsp;type||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"articleTitle": "",
				"avatar": "",
				"commentContent": "",
				"createTime": "",
				"id": 0,
				"isReview": 0,
				"nickname": "",
				"replyNickname": "",
				"type": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 删除评论


**接口地址**:`/admin/comments`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|commentIdList|commentIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 审核评论


**接口地址**:`/admin/comments/review`


**请求方式**:`PUT`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "idList": [],
  "isReview": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|reviewVO|审核|body|true|ReviewVO|ReviewVO|
|&emsp;&emsp;idList|id列表||true|array|integer|
|&emsp;&emsp;isReview|删除状态||true|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查询评论


**接口地址**:`/comments`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|commentContent|评论内容|query|true|string||
|parentId|评论父id|query|false|integer(int32)||
|replyUserId|回复用户id|query|false|integer(int32)||
|topicId|主题id|query|false|integer(int32)||
|type|评论类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«CommentDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«CommentDTO»|PageResult«CommentDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|CommentDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;commentContent||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;replyCount||integer||
|&emsp;&emsp;&emsp;&emsp;replyDTOList||array|ReplyDTO|
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;commentContent||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;parentId||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;replyNickname||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;replyUserId||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;replyWebSite||string||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;userId||integer||
|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;webSite||string||
|&emsp;&emsp;&emsp;&emsp;userId||integer||
|&emsp;&emsp;&emsp;&emsp;webSite||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"commentContent": "",
				"createTime": "",
				"id": 0,
				"likeCount": 0,
				"nickname": "",
				"replyCount": 0,
				"replyDTOList": [
					{
						"avatar": "",
						"commentContent": "",
						"createTime": "",
						"id": 0,
						"likeCount": 0,
						"nickname": "",
						"parentId": 0,
						"replyNickname": "",
						"replyUserId": 0,
						"replyWebSite": "",
						"userId": 0,
						"webSite": ""
					}
				],
				"userId": 0,
				"webSite": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 添加评论


**接口地址**:`/comments`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "commentContent": "",
  "parentId": 0,
  "replyUserId": 0,
  "topicId": 0,
  "type": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|commentVO|评论|body|true|CommentVO|CommentVO|
|&emsp;&emsp;commentContent|评论内容||true|string||
|&emsp;&emsp;parentId|评论父id||false|integer||
|&emsp;&emsp;replyUserId|回复用户id||false|integer||
|&emsp;&emsp;topicId|主题id||false|integer||
|&emsp;&emsp;type|评论类型||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 评论点赞


**接口地址**:`/comments/{commentId}/like`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|commentId|commentId|path|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查询评论下的回复


**接口地址**:`/comments/{commentId}/replies`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|commentId|评论id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«ReplyDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|ReplyDTO|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;commentContent||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;nickname||string||
|&emsp;&emsp;parentId||integer||
|&emsp;&emsp;replyNickname||string||
|&emsp;&emsp;replyUserId||integer||
|&emsp;&emsp;replyWebSite||string||
|&emsp;&emsp;userId||integer||
|&emsp;&emsp;webSite||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"avatar": "",
			"commentContent": "",
			"createTime": "",
			"id": 0,
			"likeCount": 0,
			"nickname": "",
			"parentId": 0,
			"replyNickname": "",
			"replyUserId": 0,
			"replyWebSite": "",
			"userId": 0,
			"webSite": ""
		}
	],
	"flag": true,
	"message": ""
}
```


# 说说模块


## 查看后台说说


**接口地址**:`/admin/talks`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«TalkBackDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«TalkBackDTO»|PageResult«TalkBackDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|TalkBackDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;content||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;images||string||
|&emsp;&emsp;&emsp;&emsp;imgList||array|string|
|&emsp;&emsp;&emsp;&emsp;isTop||integer||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|&emsp;&emsp;&emsp;&emsp;status||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"content": "",
				"createTime": "",
				"id": 0,
				"images": "",
				"imgList": [],
				"isTop": 0,
				"nickname": "",
				"status": 0
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 保存或修改说说


**接口地址**:`/admin/talks`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "content": "",
  "id": 0,
  "images": "",
  "isTop": 0,
  "status": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|talkVO|说说对象|body|true|TalkVO|TalkVO|
|&emsp;&emsp;content|说说内容||false|string||
|&emsp;&emsp;id|说说id||false|integer||
|&emsp;&emsp;images|说说图片||false|string||
|&emsp;&emsp;isTop|置顶状态||false|integer||
|&emsp;&emsp;status|说说状态||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除说说


**接口地址**:`/admin/talks`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|talkIdList|talkIdList|body|true|array|integer|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 上传说说图片


**接口地址**:`/admin/talks/images`


**请求方式**:`POST`


**请求数据类型**:`multipart/form-data`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|file|说说图片|formData|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«string»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": "",
	"flag": true,
	"message": ""
}
```


## 根据id查看后台说说


**接口地址**:`/admin/talks/{talkId}`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|talkId|说说id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«TalkBackDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||TalkBackDTO|TalkBackDTO|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;content||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;images||string||
|&emsp;&emsp;imgList||array|string|
|&emsp;&emsp;isTop||integer||
|&emsp;&emsp;nickname||string||
|&emsp;&emsp;status||integer||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"avatar": "",
		"content": "",
		"createTime": "",
		"id": 0,
		"images": "",
		"imgList": [],
		"isTop": 0,
		"nickname": "",
		"status": 0
	},
	"flag": true,
	"message": ""
}
```


## 查看首页说说


**接口地址**:`/home/talks`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«string»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [],
	"flag": true,
	"message": ""
}
```


## 查看说说列表


**接口地址**:`/talks`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«PageResult«TalkDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||PageResult«TalkDTO»|PageResult«TalkDTO»|
|&emsp;&emsp;count|总数|integer||
|&emsp;&emsp;recordList|分页列表|array|TalkDTO|
|&emsp;&emsp;&emsp;&emsp;avatar||string||
|&emsp;&emsp;&emsp;&emsp;commentCount||integer||
|&emsp;&emsp;&emsp;&emsp;content||string||
|&emsp;&emsp;&emsp;&emsp;createTime||string||
|&emsp;&emsp;&emsp;&emsp;id||integer||
|&emsp;&emsp;&emsp;&emsp;images||string||
|&emsp;&emsp;&emsp;&emsp;imgList||array|string|
|&emsp;&emsp;&emsp;&emsp;isTop||integer||
|&emsp;&emsp;&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;&emsp;&emsp;nickname||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"count": 0,
		"recordList": [
			{
				"avatar": "",
				"commentCount": 0,
				"content": "",
				"createTime": "",
				"id": 0,
				"images": "",
				"imgList": [],
				"isTop": 0,
				"likeCount": 0,
				"nickname": ""
			}
		]
	},
	"flag": true,
	"message": ""
}
```


## 根据id查看说说


**接口地址**:`/talks/{talkId}`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|talkId|说说id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«TalkDTO»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||TalkDTO|TalkDTO|
|&emsp;&emsp;avatar||string||
|&emsp;&emsp;commentCount||integer||
|&emsp;&emsp;content||string||
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;images||string||
|&emsp;&emsp;imgList||array|string|
|&emsp;&emsp;isTop||integer||
|&emsp;&emsp;likeCount||integer||
|&emsp;&emsp;nickname||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {
		"avatar": "",
		"commentCount": 0,
		"content": "",
		"createTime": "",
		"id": 0,
		"images": "",
		"imgList": [],
		"isTop": 0,
		"likeCount": 0,
		"nickname": ""
	},
	"flag": true,
	"message": ""
}
```


## 点赞说说


**接口地址**:`/talks/{talkId}/like`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|talkId|说说id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


# 资源模块


## 查看资源列表


**接口地址**:`/admin/resources`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|albumId|相册id|query|false|integer(int32)||
|categoryId|分类id|query|false|integer(int32)||
|current|页码|query|false|integer(int64)||
|endTime|结束时间|query|false|string(date-time)||
|isDelete|是否删除|query|false|integer(int32)||
|isReview|是否审核|query|false|integer(int32)||
|keywords|搜索内容|query|false|string||
|size|条数|query|false|integer(int64)||
|startTime|开始时间|query|false|string(date-time)||
|status|状态|query|false|integer(int32)||
|tagId|标签id|query|false|integer(int32)||
|type|登录类型|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«ResourceDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|ResourceDTO|
|&emsp;&emsp;children||array|ResourceDTO|
|&emsp;&emsp;createTime||string||
|&emsp;&emsp;id||integer||
|&emsp;&emsp;isAnonymous||integer||
|&emsp;&emsp;isDisable||integer||
|&emsp;&emsp;requestMethod||string||
|&emsp;&emsp;resourceName||string||
|&emsp;&emsp;url||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"children": [
				{
					"children": [
						{}
					],
					"createTime": "",
					"id": 0,
					"isAnonymous": 0,
					"isDisable": 0,
					"requestMethod": "",
					"resourceName": "",
					"url": ""
				}
			],
			"createTime": "",
			"id": 0,
			"isAnonymous": 0,
			"isDisable": 0,
			"requestMethod": "",
			"resourceName": "",
			"url": ""
		}
	],
	"flag": true,
	"message": ""
}
```


## 新增或修改资源


**接口地址**:`/admin/resources`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "isAnonymous": 0,
  "parentId": 0,
  "requestMethod": "",
  "resourceName": "",
  "url": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|resourceVO|资源|body|true|ResourceVO|ResourceVO|
|&emsp;&emsp;id|资源id||true|integer||
|&emsp;&emsp;isAnonymous|是否匿名访问||true|integer||
|&emsp;&emsp;parentId|父资源id||true|integer||
|&emsp;&emsp;requestMethod|资源路径||true|string||
|&emsp;&emsp;resourceName|资源名||true|string||
|&emsp;&emsp;url|资源路径||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除资源


**接口地址**:`/admin/resources/{resourceId}`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|resourceId|resourceId|path|true|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 查看角色资源选项


**接口地址**:`/admin/role/resources`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«LabelOptionDTO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|LabelOptionDTO|
|&emsp;&emsp;children||array|LabelOptionDTO|
|&emsp;&emsp;id||integer||
|&emsp;&emsp;label||string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"children": [
				{
					"children": [
						{}
					],
					"id": 0,
					"label": ""
				}
			],
			"id": 0,
			"label": ""
		}
	],
	"flag": true,
	"message": ""
}
```


# 页面模块


## 获取页面列表


**接口地址**:`/admin/pages`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«List«PageVO»»|
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||array|PageVO|
|&emsp;&emsp;id|页面id|integer||
|&emsp;&emsp;pageCover|页面封面|string||
|&emsp;&emsp;pageLabel|页面标签|string||
|&emsp;&emsp;pageName|页面名称|string||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": [
		{
			"id": 0,
			"pageCover": "",
			"pageLabel": "",
			"pageName": ""
		}
	],
	"flag": true,
	"message": ""
}
```


## 保存或更新页面


**接口地址**:`/admin/pages`


**请求方式**:`POST`


**请求数据类型**:`application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
{
  "id": 0,
  "pageCover": "",
  "pageLabel": "",
  "pageName": ""
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|pageVO|页面|body|true|PageVO|PageVO|
|&emsp;&emsp;id|页面id||true|integer||
|&emsp;&emsp;pageCover|页面封面||true|string||
|&emsp;&emsp;pageLabel|页面标签||true|string||
|&emsp;&emsp;pageName|页面名称||true|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|201|Created||
|401|Unauthorized||
|403|Forbidden||
|404|Not Found||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```


## 删除页面


**接口地址**:`/admin/pages/{pageId}`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|pageId|页面id|path|true|ref||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Result«object»|
|204|No Content||
|401|Unauthorized||
|403|Forbidden||


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|code||integer(int32)|integer(int32)|
|data||object||
|flag||boolean||
|message||string||


**响应示例**:
```javascript
{
	"code": 0,
	"data": {},
	"flag": true,
	"message": ""
}
```
# 又拍云Yii2插件
![build](https://travis-ci.org/upyun/php-sdk.svg)

又拍云存储Yii2插件，基于 [又拍云存储PHP SDK](https://github.com/upyun/php-sdk)开发。
- [更新说明](#update instructions)
- [使用说明](#use instructions)
  - [安装](#install)
  - [初始化UpYun](#init)
- [示例](#usage)
  - [上传文件](#upload file)
  - [其他方法](#other method)


<a name="use instructions"></a>
## 使用说明

<a name="install"></a>
### 安装
推荐使用 `composer` 安装
```
composer require lucasguo/yii2-upyun
```

<a name="init"></a>
### 初始化UpYun
将UpYun注册为yii2组件
```php
//在config/web.php配置文件中定义component配置信息
'components' => [
  .....
  'upyun' => [
    'class' => 'lucasguo\upyun\UpYun',
    'bucketname' => '空间名称，必填',
    'username' => '操作员账号，必填',
    'password' => '操作员密码，必填',
    'timeout' => '上传请求超时时间，整数，单位秒，选填，默认30',
    'endpoint' => '接入点，选填，选填，默认UpYun::ED_AUTO',
    'basePath' => '上传文件文件夹，如/uploads/，选填，默认/',
    'useOwnDomain' => false;(影响upload方法的返回值，云存储则设为false，自主源则为true)
  ]
  ....
]

```

更多配置说明，详见https://github.com/upyun/php-sdk

<a name="upload file"></a>
### 上传文件

**上传从form中获取的UploadedFile:**
```php
$fileUrl = Yii::$app->upyun->upload($file); 
```
<a name="other method"></a>
### 其他方法

其他可用方法，请参考https://github.com/upyun/php-sdk

Yii2 UpYun基于 MIT 开源协议

<http://www.opensource.org/licenses/MIT>


# tencentyun-cos-php
基于cos-php-sdk-v4，稍作包装，便于使用

### 封装自[cos-php-sdk-v4](https://github.com/tencentyun/cos-php-sdk-v4)

### 增加接口
* 上传整个目录

### 用法

安装：composer require "mclxly/tencentyun-cos-php:dev-master"
```php
use QCloud\Cos\Api as CosApi;
...
    $appID = env('QCLOUD_APPID','');
    $secretID = env('QCLOUD_SECRET_ID','');
    $secretKey = env('QCLOUD_SECRET_KEY','');
    $bucket = 'asset';

    $config = array(
      'app_id' => $appID,
      'secret_id' => $secretID,
      'secret_key' => $secretKey,
      'region' => 'gz',
      'timeout' => 60
    );
    $cosApi = new CosApi($config);

    // 上传文件夹
    $srcDir = public_path().'/css';
    // bucket回源地址的实际路径，用于生成目标相对路径
    $bucketBaseDir = public_path();
    $ret = $cosApi->uploadFolder($bucket, $srcDir, $bucketBaseDir);
    var_dump($ret);
```

# LLP-ExpressPay-PHP

欢迎来到连连快捷收款的PHP仓库， 本仓库包含使用PHP接入快捷收款网页版的示例代码及必要的说明。

其中， ```Web```目录下为快捷收款PC端页面的示例工程；```H5```目录下为快捷收款移动端页面的示例工程。

## 主要内容

[前置要求](#前置要求)

[快捷收款测试商户号信息](#快捷收款测试商户号信息)

[使用说明](#使用说明)

[文档说明](#文档说明)

## 前置要求

PHP版本为5.6及5.6以上

## 快捷收款测试商户号信息

测试商户号: 201408071000001539

PKCS1格式私钥(供```PHP```使用): 

```text
-----BEGIN RSA PRIVATE KEY-----
MIICXAIBAAKBgQCmRl6Zn4MmtoBoelHRT6j6ounts/x1+GiJTB9/eBTl01cBK50h
mOUtGBcOVrJCa0C1NkR8BYgOT/WLfFT8cICw6XSJtf2uzZco71jbwXfFe8MiEx/L
XiQNQHuclpkUa1hXFUUo6Qat8X8L++pVZfjav40dPKf7oFWCYLWBCDOdyQIDAQAB
AoGANe0mqz4/o+OWu8vIE1F5pWgG5G/2VjBtfvHwWUARzwP++MMzX/0dfsWMXLsj
b0UnpF3oUizdFn86TLXTPlgidDg6h0RbGwMZou/OIcwWRzgMaCVePT/D1cuhyD7Y
V8YkjVHGnErfxyia1COswAqcpiS4lcTG/RqkAMsdwSZe640CQQDRvkQ7M2WJdydc
9QLQ9FoIMnKx9mDge7+aN6ijs9gEOgh1gKUjenLr6hcGlLRyvYDKQ4b1kes22FUT
/n+AMaEPAkEAyvH05KRzax3NNdRPI45N1KuT1kydIwL3KpOK6mWuHlffed2EiWLS
dhZNiZy9wWuwFPqkrZ8g+jL0iKcCD0mjpwJBAKbWxWmeCZ+eY3ZjAtl59X/duTRs
ekU2yoN+0KtfLG64RvBI45NkHLQiIiy+7wbyTNcXfewrJUIcNRjRcVRkpesCQEM8
BbX6BYLnTKUYwV82NfLPJRtKJoUC5n/kgZFGPnkvA4qMKOybIL6ehPGiS/tYge1x
XD1pCrPZTco4CiambuECQDNtlC31iqzSKmgSWmA5kErqVJB0f1i+a0CbQLlaPGYN
/qwa7TE13yByaUdDDaTIEUrDyuqWd5+IvlbwuVsSlMw=
-----END RSA PRIVATE KEY-----
```

其公钥已上传至商户站。有关您真实商户号的公私钥配置， 请参考[连连开放平台 - 公私钥配置](https://open.lianlianpay-inc.com/docs/development/signature-key-generation)。

> 测试商户号是连连正式环境的商户号， 需要使用真实信息进行测试， 测试时建议将订单金额设置到```0.01```元(CNY)。使用测试商户号时， 建议使用独特的用户唯一标识```user_id```及独特的商户订单号```no_order```以免与其他商户的测试信息冲突。

## 使用说明

使用时必须开启```curl```服务， 修改服务器中```php.ini```文件的设置，找到```php_curl.dll```去掉注释即可。

示例工程代码文件结构如下:

```text
llpay
  │
  ├lib┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈类文件夹
  │  │
  │  ├llpay_core.function.php ┈┈┈┈┈┈连连支付接口公用函数文件
  │  │
  │  ├llpay_notify.class.php┈┈┈┈┈┈┈连连支付通知处理类文件
  │  │
  │  ├llpay_submit.class.php┈┈┈┈┈┈┈连连支付各接口请求提交类文件
  │  │
  │  └llpay_md5.function.php┈┈┈┈┈┈┈连连支付接口MD5函数文件
  │  │
  │  └llpay_cls_json.function.php┈ 连连支付接口JSON函数文件
  │
  ├log.txt┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈日志文件
  │
  ├llpay.config.php┈┈┈┈┈┈┈┈┈┈┈┈基础配置类文件
  │
  ├llpayapi.php┈┈┈┈┈┈┈┈┈┈┈┈┈┈连连支付接口入口文件
  │
  ├notify_url.php ┈┈┈┈┈┈┈┈┈┈┈┈┈服务器异步通知页面文件
  │
  └return_url.php ┈┈┈┈┈┈┈┈┈┈┈┈┈页面跳转同步通知文件
```

## 文档说明

有关快捷收款的详细介绍及请求参数说明， 请参考[连连开放平台 - 快捷收款](https://open.lianlianpay-inc.com/docs/receive-money/express/overview)。
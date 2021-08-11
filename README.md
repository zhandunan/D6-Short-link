# PHP版本 短链接


本短链接系统基于  Thinkphp V5.0.24 开发，PHP版本仅测试了PHP 5.4版本

**一、API接口：**

1.生成短链接 

GET请求接口：http://d.d6sy.com/add.php

上送参数：url=http://www.baidu.com

示例：http://d.d6sy.com/add.php?url=http://www.baidu.com



返回值：url对应的数据库记录的ID（id为主键自增长），ID会进行一层加密处理，如：1 转换为：MqQw



2.访问短链接

GET请求接口：http://d.d6sy.com/MqQw

程序内通过302跳转重定向至：http://www.baidu.com




**二、注意事项：**

网站运行目录：dl/public（需配置根目录为public）

数据库配置路径：dl/application/database.php




**三、数据库表：**

CREATE TABLE `c_dl`  (
  `id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'ID',
  `url` varchar(255) CHARACTER SET utf8 COLLATE utf8_unicode_ci NOT NULL COMMENT '链接',
  PRIMARY KEY (`id`) USING BTREE
) ENGINE = MyISAM AUTO_INCREMENT = 1 CHARACTER SET = utf8 COLLATE = utf8_unicode_ci ROW_FORMAT = Dynamic;


# yii2-routes
获取yii2项目所有路由，方便权限控制

#安装说明
php composer.phar require xinnianq/yii2-routes @dev

使用：

use xinnianq\yii2Routes\Routes;

$yiiRoutes = Routes::getAppRoutes();

var_dump($yiiRoutes);


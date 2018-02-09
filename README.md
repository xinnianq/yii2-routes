# yii2-routes
获取yii2项目所有路由，方便权限控制

#安装说明
php composer.phar require xinnianq/yii2-routes dev-master

使用：

use xinnainq\yii2Routes\yii2Routes;

$yiiRoutes = yii2Routes::getAppRoutes();

var_dump($yiiRoutes);


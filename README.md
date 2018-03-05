# yii2-routes
获取yii2项目所有路由，方便权限控制

## 安装说明
php composer.phar require xinnianq/yii2-routes @dev

### 使用1(获取所有路由)：
<pre><code>
use xinnianq\yii2Routes\Routes;

$yiiRoutes = Routes::getAppRoutes();

var_dump($yiiRoutes);
</code></pre>
### 使用2（获取单个module）：
<pre><code>
use xinnianq\yii2Routes\Routes;

$yiiRoutes = Routes::getAppRoutes('gii');

var_dump($yiiRoutes);
</code></pre>
### 注意：
* 1、如果结果为空白，请查看runtime log ;看是否是哪个控制器代码写错了
* 2、为了获取好看的描述 代码如下：
<pre><code>
namespace app\controllers;

use Yii;
use yii\web\Controller;

/**
 * 你好控制器
 * @package app\controllers
 * @author fengqiquan
 */
class NihaoController extends Controller
{

    /**
     * 你好index方法
     * @return string
     */
    public function actionIndex()
    {
        return $this->render('index');
    }

}
</code></pre>

### 返回结果：
<pre><code>
array(2) {
  ["/nihao/"]=>
  array(2) {
    ["controllerDescription"]=>
    string(15) "你好控制器"
    ["route"]=>
    array(1) {
      ["/nihao/index"]=>
      array(2) {
        [0]=>
        string(12) "/nihao/index"
        [1]=>
        string(17) "你好index方法"
      }
    }
  }
  ["/site/"]=>
  array(2) {
    ["controllerDescription"]=>
    string(0) ""
    ["route"]=>
    array(5) {
      ["/site/index"]=>
      array(2) {
        [0]=>
        string(11) "/site/index"
        [1]=>
        string(18) "Displays homepage."
      }
      ["/site/login"]=>
      array(2) {
        [0]=>
        string(11) "/site/login"
        [1]=>
        string(13) "Login action."
      }
      ["/site/logout"]=>
      array(2) {
        [0]=>
        string(12) "/site/logout"
        [1]=>
        string(14) "Logout action."
      }
      ["/site/contact"]=>
      array(2) {
        [0]=>
        string(13) "/site/contact"
        [1]=>
        string(22) "Displays contact page."
      }
      ["/site/about"]=>
      array(2) {
        [0]=>
        string(11) "/site/about"
        [1]=>
        string(20) "Displays about page."
      }
    }
  }
}
</code></pre>
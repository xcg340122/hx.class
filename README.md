# hx.class
环信PHP扩展操作类
```php
//1.先将该方法贴到类中
/**
 * 返回环信实例
 * @return HxController|bool
 */
static public function ReturnHx(){
    //载入环信扩展
    extend('Hx.class.php');
    //读取配置文件信息
    $Config = APP::$app->get('Config')->get('Hx');
    //实例化环信
    $Hx = new \Hx($Config['HxConfig']);
    //返回实例
    return is_object($Hx) ? $Hx : false;
}

//2.新建配置文件，名称叫Hx.cfg.php，配置文件内容：
/**
 * 环信配置项
 */
return [
    'HxConfig'=>array(

        'client_id'=>'',

        'client_secret'=>'',

        'org_name'=>'',

        'app_name'=>''
    ),
];

//3.使用方法
$Hx = self::ReturnHx();
$rows = $Hx->createUser('zhangsan','123456');
```

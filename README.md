# hx.class
环信PHP扩展操作类
```
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

//使用方法
$Hx = self::ReturnHx();
$rows = $Hx->createUser('zhangsan','123456');

//配置文件内容：
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
```

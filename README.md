# fasthessian
比官方hessian快速5倍以上的hessian解析框架;
官方的Hessian框架性能有问题，在返回数据量比较大的情况下，响应时间明显增加，我们测试发现，返回数据超过100条时，响应时间超过5秒，有的甚至要20几秒，
使用此框架后，响应时间不超过1秒；

以下为示例代码：

$options = array();
$url = 'http://127.0.0.1:8888/HelloWorldService?anyhost=true&protocol=hessian&revision=1.0-SNAPSHOT&server=jetty&side=consumer&timestamp=1454299178118&version=1.0.0';

$client = new HessianClient($url, $options);
$res = call_user_func_array(array($client, 'sayHelloWorld'), array('123'));
var_dump($res);

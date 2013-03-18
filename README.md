yii-kissmetrics
===============

[KISSMetrics](https://www.kissmetrics.com/) is a paid SAAS analytics product designed to track event occurring in your application.  This extension wraps around their open-source [PHP library](https://github.com/kissmetrics/KISSmetrics/blob/master/km.php) and makes it a little easier to use with Yii.

##Requirements

 * Yii 1.1.12+ 
 * An account with KISSMetrics

##Usage

 1. Place the `metrics` folder into your extensions.
 2. Add the following to your `components` block in your config file.

````[php]
'metrics' => array(
    'class' => 'ext.metrics.Metrics',
    'enabled' => true,
    'key' => "", // secret key for your KISSmetrics account
    'log_dir' => dirname(__FILE__).DIRECTORY_SEPARATOR.'../runtime/',
    'to_stderr' => true,
    'use_cron' => false,
),
````
 
 3. To record an event, simply call `Yii::app()->metrics->record(...)` as you would `KM::record(...)`, but with an additional optional parameter for your user identity flag.

````[php]
Yii::app()->metrics->record('myEventId', array(
    'myEventKey1' => 'myEventValue1',
    'myEventKey2' => 'myEventValue2',
    ...
));
````

##Resources

 * [Github repo](https://github.com/ajsharma/yii-kissmetrics)

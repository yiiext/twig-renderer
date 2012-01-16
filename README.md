Twig view renderer
==================

This extension allows you to use [Twig](http://twig.sensiolabs.org) templates in Yii.

###Resources
* [This extension](https://github.com/yiiext/twig-renderer)
* [Twig](https://github.com/fabpot/twig)
* [Discuss](http://www.yiiframework.com/forum/index.php?/topic/4919-twig-view-renderer/)
* [Report a bug](https://github.com/yiiext/twig-renderer/issues)

###Requirements
* Yii 1.0 or above

###Installation
* Extract the release file under `protected/extensions`.
* [Download](http://twig.sensiolabs.org/installation) and extract all Twig files from `fabpot-Twig-______.zip\fabpot-Twig-______\lib\Twig\` under `protected/vendors/Twig`.
* Add the following to your config file 'components' section:

```php
<?php

    'viewRenderer' => array(
        'class' => 'ext.ETwigViewRenderer',

        // All parameters below are optional, change them to your needs
        'fileExtension' => '.twig',
        'options' => array(
            'autoescape' => true,
        ),
        'extensions' => array(
            'My_Twig_Extension',
        ),
        'globals' => array(
            'html' => 'CHtml'
        ),
        'functions' => array(
            'rot13' => 'str_rot13',
        ),
        'filters' => array(
            'jencode' => 'CJSON::encode',
        ),
        // Change template syntax to Smarty-like (not recommended)
        'lexerOptions' => array(
            'tag_comment'  => array('{*', '*}'),
            'tag_block'    => array('{', '}'),
            'tag_variable' => array('{$', '}')
        ),
    ),
```

###Usage
* See [Twig syntax](http://twig.sensiolabs.org/doc/templates.html).
* Current controller properties are accessible via {{this.pageTitle}}.
* Yii::app() object is accessible via {{App}}.
* Yii's core static classes (for example, CHtml) are accessible via {{C.ClassNameWithoutFirstC.Method}} (example: {{C.Html.textField(name,'value')}})
* To call functions or methods which return non-string result wrap these calls with 'void' function: {{void(App.clientScript.registerScriptFile(...))}}

###Widgets usage example
```html
<div id="mainmenu">
    {{ this.widget('zii.widgets.CMenu',{
        'items':[
            {'label':'Home', 'url':['/site/index']},
            {'label':'About', 'url':{0:'/site/page', 'view':'about'} },
            {'label':'Contact', 'url':['/site/contact']},
            {'label':'Login', 'url':['/site/login'], 'visible':App.user.isGuest},
            {'label':'Logout ('~App.user.name~')', 'url':['/site/logout'], 'visible':not App.user.isGuest}
        ]
    }, true) }}
</div><!-- mainmenu -->
```
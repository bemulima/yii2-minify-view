Yii 2 Minify View Component
===========================

[![Latest Stable Version](https://poser.pugx.org/mirocow/yii2-minify-view/v/stable)](https://packagist.org/packages/mirocow/yii2-minify-view) [![Latest Unstable Version](https://poser.pugx.org/mirocow/yii2-minify-view/v/unstable)](https://packagist.org/packages/mirocow/yii2-minify-view) [![Total Downloads](https://poser.pugx.org/mirocow/yii2-minify-view/downloads)](https://packagist.org/packages/mirocow/yii2-minify-view) [![License](https://poser.pugx.org/mirocow/yii2-minify-view/license)](https://packagist.org/packages/mirocow/yii2-minify-view)

Installation
------------
The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

### Add github repository


```json
    "repositories": [
        {
            "type": "git",
            "url": "https://github.com/mirocow/yii2-minify-view.git"
        }
    ]
```

and then

```
php composer.phar require --prefer-dist "mirocow/yii2-minify-view" "*"
```

or add

```json
"mirocow/yii2-minify-view" : "*"
```

to the require section of your application's `composer.json` file.

Configure
-----
```php
<?
return [
	// ...
	'components' => [
		// ...
    'view' => [
      'class' => '\mirocow\minify\View',
      'base_path' => '@app/web', // path alias to web base
      'minify_path' => '@app/web/minify', // path alias to save minify result
      'minify_css' => true,
      'minify_js' => true,
      'minify_html' => true,
      'js_len_to_minify' => 1000, // Больше этого размера inlinejs будет сжиматься и упаковываться в файл
      'force_charset' => 'UTF-8', // charset forcibly assign, otherwise will use all of the files found charset
      'expand_imports' => true, // whether to change @import on content
      //'css_linebreak_pos' => false,
      
      // Theming
      'theme' => [
        'basePath' => '@app/themes/myapp',
        'baseUrl' => '@app/themes/myapp',
        'pathMap' => [ 
          '@app/modules' => '@app/themes/myapp/modules',
          /*'@app/views' => [ 
            '@webroot/themes/myapp/views',
          ]*/
        ],
      ],          
      
    ],
	]
];
```

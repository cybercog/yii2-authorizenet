YII2 Authorizenet Gateway Extensions
====================================
YII2 Authorizenet Gateway Extension

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist tenbulls/yii2-authorizenet "*"
```

or add

```
"tenbulls/yii2-authorizenet": "*"
```

to the require section of your `composer.json` file.


How to call?
-----	
You just have to include these lines in your code before using it and other code you can use exactly the same as authorizenet PHP SDK.

	use tenbulls\authorizenet\Api;
	Api::init();
	


Usage Examples
-----
Once the extension is installed, simply use it in your code by  :

````php
	use tenbulls\authorizenet\Api;
	Api::init();
	define("AUTHORIZENET_API_LOGIN_ID", "752tVh6FXc");
	define("AUTHORIZENET_TRANSACTION_KEY", "72PWU2Xd7g4a7m46");
	define("AUTHORIZENET_SANDBOX", true);

	$sale = new AuthorizeNetAIM;
	$sale->amount = "5.99";
	$sale->card_num = '4111111111111111';
	$sale->exp_date = '0418';
	$response = $sale->authorizeAndCapture();
	if ($response->approved) {
	echo "Success! Transaction ID:" . $response->transaction_id;
	} else {
	echo "ERROR:" . $response->error_message;
	}	
````

For more examples visit https://github.com/AuthorizeNet/sdk-php	
	
## License

**yii2-authorizenet** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.	
	

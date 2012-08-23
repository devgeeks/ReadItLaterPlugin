ReadItLaterPlugin
============

#### NOTE: This plugin is a bit pointless as Read It Later has changed to [Pocket](http://getpocket.com) now. 


Installation
------------

This plugin allows you to save a URL to [Read It Later](http://readitlaterlist.com) from your app.

Add the plugin much like any other:

1.	Add the ReadItLaterPlugin.h and VolumeSlider.m classes to your Plugins folder in Xcode (use "Create groups for any added folders")
2.	Add the ReadItLaterPlugin.js file to your www folder
3.	Add the ReadItLaterPlugin.js to your html file. eg: `<script type="text/javascript" charset="utf-8" src="ReadItLaterPlugin.js"></script>`
4.	Add the plugin to the PhoneGap.plist under Plugins (key: "ReadItLaterPlugin" value: "ReadItLaterPlugin")

Next, get the Read It Later API iPhone Library and add it to your project:

1.	[Download the library from Read It Later](http://readitlaterlist.com/api/libraries-iphone#download)
2. 	Unzip the library and examples
3.	Copy these four files into your Xcode project under the Plugins folder (again, use "Create groups for any added folders")
	* `ReadItLaterLite.h`
	* `ReadItLaterLite.m`
	* `ReadItLaterFull.h`
	* `ReadItLaterFull.m`
4.	[Get an API Key](http://readitlaterlist.com/api/signup/) from Read It Later for your app
5.	Add your shiny new API key to the top of the `ReadItLaterLite.m` file you copied in above
	* `static NSString *apikey = @"<api key here>";`
6.	Add the name of your app (as you entered it to get your API key above) as well
	* `static NSString *nameOfYourApp = @"<name of your app here>";`

Finally, call the `saveToReadItLater()` method using a success callback and an object containing a url and a title:

### Example
```javascript
function onDeviceReady()
{
	var readItLaterPlugin = window.plugins.readItLaterPlugin;
	readItLaterPlugin.saveToReadItLater(
		function(){
			console.log("Successfully saved to Read It Later");
		}, 
		{ 
			url: "http://github.com/devgeeks", 
			title: "Devgeeks on GitHub"
		}
	);
}
```

## License

The MIT License

Copyright (c) 2011 Tommy-Carlos Williams (http://github.com/devgeeks)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

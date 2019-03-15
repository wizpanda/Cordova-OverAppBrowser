OverAppBrowser
==================

Render a webview over your cordova webview (ios and android).

Difference with the original repository
------------

There are few difference/changes as compared to the original version

1. Clearing & closing the WebView after exiting the OverAppBrowser to prevent memory link in Android
2. A method to toggle the hardware back button `toggleHardwareBack`
3. Changed id of the plugin

Installation
------------

To install from **command line**:

    cordova plugin add com.lesfrancschatons.cordova.plugins.overappbrowser


Documentation
-------------

    //function(strUrl, originx, originy, width, height, isAutoFadeIn)
    oab = new OverAppBrowser('http://www.google.fr', 0, 100, 320, 320, true);

    //Events : loadstop, loadstart, exit, loaderror
    oab.addEventListener('loadstop', function(){
        //insert inline style
        oab.insertCSS({code:'#hplogoo {-webkit-transform: rotate(180deg);}'});

        //insert css file
        oab.insertCSS({file:'http://domain.com/style.css'});

        //execute javascript code
        oab.executeScript({code:'window.alert("test");'});

        //insert javascript file
        oab.executeScript({file:'http://domain.com/script.js'});
    });

    //Fade the webview
    oab.fade(toAlpha, duration);

    //Resize the webview
    oab.resize(originx, originy, width, height);

    //Close the webview
    oab.close();


This loads `http://google.fr` over your html app at x=0, y=100, width=320, height=320 and rotates the homepage logo

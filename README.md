# maidbook

It is simple webview app of flutter with below features

<b>Features:</b> </br>
- Back Button
- Forward Button
- Refresh Widget
- Add Cache
- Clear Cache
- Add Cookie
- Clear Cookie
- Check User agent

## Must Look
-----------------------
Please have a look to pubspec.yaml some minor configuration i did, you will get the idea.

# You
-----------------------
You can change the flutter website URL to yours which can be seen inside maidbook\lib\home_page.dart at line no# 66 and 75, have look to code:

return WebView(
  initialUrl: 'https://flutter.dev/',
  javascriptMode: JavascriptMode.unrestricted,
  onWebViewCreated: (WebViewController webViewController){
    _controller.complete(webViewController);
  },
  javascriptChannels: 
  <JavascriptChannel>[snackbarJavascriptChannel(context),
  ].toSet(),
  navigationDelegate: (NavigationRequest request){
    if(request.url.startsWith("https://flutter.dev/")){
      print('Blocking navigation');
      return NavigationDecision.prevent;
    }
    return NavigationDecision.navigate;
  },
);


If you get any error feel free to open issue i will be solving it for you!

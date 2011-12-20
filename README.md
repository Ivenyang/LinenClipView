**LinenClipView** provides subclasses of `NSClipView` for `NSScrollView` and `WebView` 
that displays a linen pattern in the clip views like many of Apple's Lion apps.

``` obj-c
- (void)awakeFromNib{
    [LNClipView setupWithScrollView:self.tableScrollView];
    
    [LNWebClipView setupWithWebView:self.webView];
}
```

By default LNClipView uses an image in the main bundle named *Linen*. To use a different image call `[LNClipView setBackgroundImage:]`. The background image is stored statically to improve drawing performance so it can only be set once and must be set before setting up any clip views.

    [LNClipView setBackgroundImage:[NSImage imageNamed:@"linen_background"]];

This repository contains a sample app demonstrating how to use `LNClipView` with a `NSTableView` and `WebView`.

![](https://github.com/InScopeApps/LinenClipView/raw/master/Screenshot.png)

Special thanks to [@Dimillian](https://twitter.com/#!/dimillian) for figuring out how to keep the 
pattern stationary(`[NSGraphicsContext setPatternPhase:]`).

## Apps using LinenClipView

* [Play by Play](http://playbyplayapp.com)
* [Raven](http://raven.io)
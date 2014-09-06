# HipChat Colors

HipChat 3.0 really screwed up the color scheme, particularly when it comes to system messages (like webhooks messages received from external APIs). Luckily, the UI is styled via standard CSS that is easily accessible inside the HipChat package on OSX, so I immediately reverted the colors to the 2.x styles (well, close enough).

You can see the original HipChat 3.0 colors on the left, and the reverted version that you'll get with this file on the right:

![](https://github.com/bmoeskau/hipchat-colors/blob/master/hipchat-colors.jpg)

Other tweaks (so far):

- Switched the "you" name block to a slightly darker gray
- Switched the "me" message blocks back to a proper blue
- Reduced the overall message font size and padding slightly to tighten things up
- Fixed code blocks (switched to the standard Github code font list: `font-family: Consolas, "Liberation Mono", Menlo, Courier, monospace;` and lightened up the background color)

![](https://github.com/bmoeskau/hipchat-colors/blob/master/hipchat-colors2.jpg)

These styles could definitely be improved upon further (knock yourself out!), but I just wanted a quick fix so I can get back to work, and I was perfectly happy with the old colors.

## "Installation"

**NOTE: This only applies to the OSX version**

1. Quit HipChat (it will not refresh styles while it's open)
2. Locate the HipChat app file in `/Applications`
2. Right-click the app icon in Finder and select "Show Package Contents"
3. Navigate to `/Applications/Hipchat/Contents/Resources/` where you'll find mostly image files, plus a few css files
4. If you want to play it safe (recommended) back up or rename `chat.css` and `chat-osx.css`
5. Copy `chat.css` and `chat-osx.css` from this repo into that folder and restart HipChat
6. Get back to enjoying your chats

## A Note About Font Size
The `chat-osx.css` seems to override a few things, although it's unclear to me why it's a separate file. The important thing is that the overall font size is specified there as a percentage, allowing for `⌘ +`, `⌘ -` and `⌘ 0` to increase, decrease and reset the font size dynamically in the UI. You should stick to adjusting this percentage rather than hard-coding fonts in `px` if you care about such things.
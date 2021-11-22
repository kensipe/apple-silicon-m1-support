# MacOS Monterey

There are a number of experiences happening at roughly the same time... a move to M1 and the use of Monterey.   It seems useful to cover developer issues regarding Monterey in this repo.

## Ports

This isn't really an M1 issue.  Closely tied to M1's release is the release of macOS Monterey Version 12.  Apple has decided to enable Macs to be an "AirPlay Receiver" in addition to being a "producer". The port used for years for AirPlay is port `5000` which is a common development port. 

You can move to another port.. or turn off the "AirPlay Reciever" in the "Sharing" tab of system properties.

More details: https://developer.apple.com/forums/thread/682332

## Fn Key

The lowest left hand side of the keyboard is the `Fn` key, which on the new MBP also shows the world symbol.  Often used for accessing function keys such as F1, F2... 

Fn pressed in isolation results in a keyboard pop-up which allows for selecting of an emoji or symbol. I have no idea why I keep hitting it.. likely a side hit when trying to hit the ctrl key..  however the popup is too frequent to be tolerated. Most online help seems confusing as the help is with the F# like F1 key and assumes people are confused with the lack of touchbar.   

The solution is simple.  System Properties -> Keyboard -> Keyboard.  It's tricky as in the middle there is a "Press {symbol} to" followed by a dropped that by default is "Show Emoji & Symbols". Here instead of calling it the `Fn` key, we have a symbol that isn't pronoucable or recordable (other than by image) :(  For a visual walk here's a [reference](https://www.howtogeek.com/708537/how-to-disable-the-mac-keyboards-emoji-shortcut/).
** I was even more disappointed that the symbol used isn't in the list of options in the pop-up.
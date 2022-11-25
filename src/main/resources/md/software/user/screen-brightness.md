# Screen Brightness

I use [Lunar](https://lunar.fyi) to change the brightness of my external displays in conjunction with my MacBook Pro. It also supports brightness offsets which come in handy because my external displays are much brighter than my internal display at equivalent levels of screen brightness as the macOS UI displays it. I offset the external displays to -20 so that they are more aligned to the internal one.

For some reason, though, the screen brightness buttons on my Magic Keyboard (i.e. F1, F2) modify one of the **external** displays. I have to use [MonitorControl](https://github.com/MonitorControl/MonitorControl) to intercept those events and change its settings to have it only update the internal display. If I have it update all the displays, then it causes the screens to flash brightly before Lunar can kick in. I find this annoying. Lunar eases the transition.

I also tried out [ExternalDisplayBrightness](https://www.nesveda.com/projects/ExternalDisplayBrightness/). However, it has one pesky issue. It [does not survive sleep cycles](https://github.com/fnesveda/ExternalDisplayBrightness/issues/19).

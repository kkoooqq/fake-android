# 🐭 Fake Android, all for bots 🤖

------

😎 Join the discussion and let's discover fun things together: [All-For-Bots](https://discord.gg/VMUhnUe2)

------

Reverse engineering is not easy, and I would appreciate if you could give a ⭐!

------

## Technical details

My goal is not to be detected by the anti-bot system / risk control system, but after the device is rooted, the target app can easily get the underlying system information and detect whether it is being injected, and the common xposed-like hook solution definitely cannot bypass the detection.

**So we can only choose non-rooted system.** 

After a lot of testings, I found that the [UI-automator](https://developer.android.com/training/testing/ui-automator) comes with Android system can reach my requirements well and can't be identified.

I have made many changes and integrated the following open source libraries:

|repo|details|
|----|----|
|[uiautomator2](https://github.com/openatx/uiautomator2)|Wrapping uiautomator interface using python. I modified this code to make the communication much more efficient and to make it support remote connections.|
|[atx-agent](https://github.com/openatx/atx-agent)|Android-side service program. I made it possible to run on non-root devices and support remote command calls.|
|[weditor](https://github.com/alibaba/web-editor)|Desktop side control interface for easy recording of control scripts. I made it support remote device control.|
|[sekiro](https://github.com/virjar/sekiro)|Implement NAT traversal. I use this framework, combined with gRPC to complete the group control feature of remote devices.|


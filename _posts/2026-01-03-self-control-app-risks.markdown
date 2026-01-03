---
layout: post
title: Useful productivity tool or borderline ransomware?
---
**To be clear, I am not saying the app I'm describing is actually ransomware, it is not. I'm just giving a hypothetical scenario where the app could be turned into ransomware.**

Recently, I've been thinking about how I can use my phone less and be less reliant on it, possibly by switching to a dumbphone. This reminded me of when I saw someone using a self-control Android app that tries to help with this by fully locking you out of your phone for a set time period. This happened some time ago, a while before this blog existed. At that time, I didn't think you could make a third-party Android app that blocks you using your phone that doesn't require a friend / parent to monitor, doesn't have a trivial bypass and doesn't require root access. Surprisingly, I found that this app ticks all those boxes, but I am not sure that's a good thing.

I ended up installing this self-control app (which I won't name) on a test phone just to see how easy it would be to get around the restrictions, and I have to say I have very strongly mixed feelings about this app. On one hand, it serves its intended purpose ridiculously well. On the other hand, it is probably one line of code away from being ransomware. Let me explain.

When you first install this app, it asks you for permission to access the Android [Device Administration API](https://developer.android.com/work/device-admin). This is an API primarily designed for companies to use on phones they give to their employees to make the phones more secure and protect sensitive company data. For instance, this API can require stronger PIN codes or give the employer the ability to remotely wipe the device. The Device Administrator API does not require root to use it and can be requested by any app, but you should be extremely weary of apps that do this. This specific app only asks for one permission from this API: the permission to lock the screen. A consequence of requesting this permission is that the app cannot be uninstalled until you go into the device's settings and manually revoke this permission. 

Once you have granted this permission the app takes you to a screen where you can lock the device for a specific amount of time, during which you won't be able to access your phone. After testing this functionality out I realised that the way it works is really simple. If the timer hasn't run out and you unlock the phone, the app immediately locks the phone again (using the device admin permission). Conveniently, this method means you can still take phone calls and access anything on the lock screen, as long as it doesn't require unlocking the phone.

I then tried to bypass the app's mechanism. None of the basic things I tried worked. I found the phone re-locks too quickly after an unlock for any touch inputs to go through, and after a reboot the app starts back up immediately without a long enough delay for inputs. You can't kill the app with ADB either, since ADB usually requires the phone to be unlocked to work. My test phone had an unlocked bootloader and custom recovery so you could obviously use that to delete the app but I won't count this as a valid bypass. Most Android phones have locked bootloaders and don't allow you to delete apps from the stock recovery so this method won't work in most cases.

I am honestly quite impressed with how effectively the app serves its purpose. I literally can't think of anything reasonable that would unlock the phone before the timer runs out. The only method I can think of for stock Android devices is factory resetting the device from recovery mode, which would work but would delete everything on your phone, which would probably be enough of a deterrent from doing this. If the device didn't have a working recovery mode, then I honestly don't know if there is any bypass which wouldn't involve physically opening up the phone.

So why did I say this app is possibly one line of code away from being ransomware? Well, it's because of one additional feature the app offers. If you can't resist the urge to check your phone before the timer runs out, then you can pay money to the developers(s)  via an in-app purchase (you can set the amount to be paid). This is certainly a unique way of monetising an app and I'm not sure how I feel about the morality of this but I admire the bravery of the app's developer(s) for publishing an app like this. If they screw up just a few lines of code in an update (or there is a bug) then they risk the app becoming ransomware. I haven't reverse engineered the app so I don't know how the code is written, but let's say the app uses code like this to decide if it locks the phone:
```c
while (timeRemaining > 0 && !earlyUnlockPaid) {
    if (phoneUnlocked) {
        lockPhone();
    }
    ...
}
```
Obviously, the app's actual code won't look the same as the code above and might not use the same logic. No matter how it's written, it is highly likely that there is a small change you can make that would achieve the same effect.

If the above code were how the app worked, then you could turn the app into ransomware just by changing the first line and making it ignore how much time is left on the timer:
```c
while (!earlyUnlockPaid) {
    if (phoneUnlocked) {
        lockPhone();
    }
    ...
}
```
If this tiny change to the code got made, the app would now be ransomware! Your phone wouldn't unlock when the timer runs out and the only other way to unlock it would be through the in-app purchase feature that lets you pay to unlock the phone early.

In this scenario, the app wouldn't unlock your phone unless you paid the developer(s) money or factory reset your phone. You then probably wouldn't be able to access any data you had your phone that wasn't backed up. This hypothetical example may not fit the typical definition of ransomware since it wouldn't make the app encrypt your files, but it would demand payment for you to access your data, which is what most ransomware does.

Even if the developer(s) have only good intentions and you fully trust them, I don't think that completely eliminates the risk of this being a problem. It could happen by accident as a result of a bug in the app, or if a developer accidentally changes the wrong line of code. I don't think it's too likely to happen but it is definitely more likely than it should be.

I checked on the Google Play Store listing of the app and it still seems to be getting updates and those updates mention bug fixes. This means the code of the app gets modified, which always risks introducing new bugs. This means it is more than possible for a highly unfortunate bug like this to be accidentally introduced by the developer(s) in any of these updates to the app. Realistically, almost all software contains bugs and this software has a potential bug which is not too unlikely to happen and would have a detrimental effect on the app's users. This is much worse than the kind of bugs most apps risk having if just a few lines of code are slightly off.

Of course, it is possible that the developer(s) have written the code with a lot of safeguards in place to stop this from happening. However, the app doesn't have it's source code available so I wouldn't rely on this and even having safeguards wouldn't completely remove any chance of this bug happening.

There are other ways that self-control apps similar to this one could cause issues. For instance, the app could set an unreasonably-high upper bound for the timer and wrap around to the maximum value if you decremented a 0 minute timer. This could result in you accidentally setting a lock lasting centuries just by one wrong tap.

So is it safe to use apps like this? Well, I think if you used this app or one similar to it and downloaded it from Google Play or another generally-trustworthy app store, then the chances of major issues like this are probably low (no, I don't like Google Play at all, I'm just grudgingly mentioning it since it is the most common Android app store). However, I would highly recommend avoiding using apps like this, since it could be poorly designed and could cause you to be permanently locked out of your phone. Also, all the apps I found are proprietary meaning no one except the developers can audit the app to check what it does or if there are any bugs.

While this app may seem like a good idea for your productivity, it has a large risk attached to it. It is always one bug away from permanently preventing you from accessing your data.

The most absurd thing about this is that this is just one of many kinds of concerning apps that people casually install on their phone without giving it a second thought. Yes, Android is fairly secure but you still need to be vigilant about what apps you install and what permissions you give them.

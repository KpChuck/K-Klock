**How to make K-Klock**


**Step 1: Prerequisites**

- Make sure that your phone is either running an OMS supported ROM or is rooted.
- Install Android Studio, the latest Canary version is required for now. [Link.](https://developer.android.com/studio/preview/install-preview.html)
- Make a pull request or download this [K-Klock template](https://github.com/KpChuck/K-Klock/tree/OOS)
- It is recommended that you read the [official guide](https://github.com/substratum/template) to susbtratum theming so know what's going on.
- Make a nandroid backup before starting.
- Know how to recover from a bootloop either be flashing substratum's recovery zips or re-flashing your ROM.
- If you have any question, feel free to ask me through:

     - [My thread on XDA](https://forum.xda-developers.com/oneplus-5/themes/v4-2-k-klock-customize-statusbar-clock-t3629157/page5)
     - [PM me on XDA](https://forum.xda-developers.com/private.php?do=newpm&u=7750173)
     - PM me on Telegram @KpChuck


**Step 2: Configuring the Template**

- _-The first thing you want to do is change the theme values. Go to res/values/theme_configurations.xml._

Set the string ThemeName to "K-Klock Your_Rom_Name".

You can also add your name and email below if you want to provide support for anyone having issues.

- _Now it's time to change the device specific parts of the template: the layout files._

    Decompile your SystemUI.apk using apktool(PC) or APK Editor(Mobile).

    Go to assets/overlays/com.android.systemui/res/layout.

    Copy the status_bar.xml and keyguard_status_bar.xml from your decompiled SystemUI into the res folder.

    Now use the replace function in Android Studio to replace all the '@' with '@*com.android.systemui:' in both xml's.

- _Now make the following change to keyguard_status_bar.xml:_

    Find the layout that contains the id 'super_status_bar',

    Either add android:visibility="gone" or set the width of that layout to 0dip, or do both.

- _Preparing all the different clock options._

    Copy and paste your status_bar.xml into each of the type2_xyz/layout folders.

    Also copy and paste your keyguard_status_bar.xml into the type2_xyz/layout folders that already have a placeholder keyguard_status_bar.xml present.

 - _Configuring the status_bar.xml's that you have added._

     **Note:** This is where you want to be really careful so that everything ends up in the right place.

     Use an internet browser to open this template in github.

     Open assets/com.android.systemui/res/layout/status_bar.xml in android and in github.

     Copy the text indicated by the comments in my github comment in the status_bar.xml and

     use id's to find where to paste it in the same place in your own status_bar.xml.

     Do this for all the status_bar.xml's in the type2 folders as well.

 - _Fixing the keyguard_status_bar.xml's that you pasted in some of the type2 folders._

     Find the layout_width or android:visibility="gone" that you changed and revert this back to what it was originally as shown in my template.

  - I have tried to make my comments in the template as clear as possible but if you get confused, ask!

- _Now you're all set, time for testing!_


**Step 3: Testing and Troubleshooting**

 -Most of the time, K-Klock won't apply properly the first time. Don't panic, it's usually something minor.

 - _Errors while compiling_

    If K-Klock hasn't installed properly then most likely you haven't followed all the steps above properly.

     Use the logchar file that substratum generates to find where you have gone wrong.

- _Phone bootloops/boots to a black screen(Legacy) or SystemUI crashes(In OMS)_

     Try and pull the logs so you can see what errors are occurring. These are really useful, if you don't understand logs, pull them anyway and show them to someone who does.

     Throughout my time making K-Klock, I got 2 instances of this happening:

     - In Omni, SystemUI crashed when I set the clock width to zero to hide the stock clock. My solution was to not set the clock width to zero.

     - In LineageOS, SystemUI crashed when I added '@*com.android.systemui:id/clock' to my custom clock. I deleted all the type2_White-Grey folders, they're the only ones that have an id with a custom clock.

        The error here looked something like this:

        07-10 00:17:12.578  3921  3921 E AndroidRuntime: java.lang.ClassCastException: android.widget.TextClock cannot be cast to com.android.systemui.statusbar.policy.Clock

- _As always, if you need help you can contact me through:_

     - [My thread on XDA](https://forum.xda-developers.com/oneplus-5/themes/v4-2-k-klock-customize-statusbar-clock-t3629157/page5)
     - [PM me on XDA](https://forum.xda-developers.com/private.php?do=newpm&u=7750173)
     - PM me on Telegram @KpChuck


**Step 4: Publish your App**

Once you're sure everything is working, you can share your work with everyone else!

If you want your app to be available in K-Klock Manager, it's going to have to be uploaded on AndroidFileHost.com.
You can either upload it yourself or share it with me and I will upload it.

After that simply contact me with your ROM name and a link to your app on AndroidFileHost.com and I will be able to include it in K-Klock Manager.

- _You can contact me through:_

     - [My thread on XDA](https://forum.xda-developers.com/oneplus-5/themes/v4-2-k-klock-customize-statusbar-clock-t3629157/page5)
     - [PM me on XDA](https://forum.xda-developers.com/private.php?do=newpm&u=7750173)
     - PM me on Telegram @KpChuck



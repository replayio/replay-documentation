# Troubleshooting

If you run into an issue while recording with the **[Replay Browser](https://www.notion.so/Replay-Browser-519d5844d34947d490427621351840f1?pvs=21)**, these tips can help identify the issue. If you have any questions or get stuck, don’t hesitate to [contact us](Contact%20&%20Community%20096224a3bca4479b982ac572dc5c81d0.md).

<aside>
💡 The **Replay Browser** is not required to view replays. Replay URLs can be opened in any browser of your choice.

</aside>

## Updating the Replay Browser

There are three ways to update Replay. 

- Quit and re-open Replay.
- Click on the green arrow in the top right.
    
    ![Screen Shot 2022-01-24 at 10.27.01 AM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2022-01-24_at_10.27.01_AM.png)
    
- Go to *Replay > About Replay*.

## Checking Replay's Build ID

To check if Replay is up-to-date or to get the Build ID for a bug report, go to *Replay > About Replay.* The Build ID corresponds to the `<year><month><day><time>` of the build’s release.

![Screen Shot 2022-01-27 at 11.12.46 AM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2022-01-27_at_11.12.46_AM.png)

## Checking the Browser Console

When the browser fails while recording, the exception will likely be logged to the Browser Console. 

<aside>
👉 As a little bit of context, we built Replay's recorder is written in C++, but most of the logic for starting, stopping, and saving is in JavaScript. This means that most exceptions will bubble up to the console where we can pretty easily identify it and fix it.

</aside>

The Browser Console is available at *Tools > Web Developer > Browser Console*.

![Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/console2.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/console2.png)

## Collecting Data for Login Issues

1. Launch Replay and [open the browser toolbox](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be.md). This will open a new window with standard devtools (but connected to the browser instead of the current web page)
2. Click the "Sign in" button and walk through the auth steps
3. After you complete the authentication in your preferred browser, return to the Replay browser's browser toolbox window and check for errors in the console.
    
    ![https://media.discordapp.net/attachments/1155867540669612092/1155895939358265455/image.png?width=273&height=259](https://media.discordapp.net/attachments/1155867540669612092/1155895939358265455/image.png?width=273&height=259)
    
4. Switch to the network tab and select Save All as HAR from the settings menu to download your network requests. This will help us correlate your auth attempts with our logs. You can send that to via DM in Discord or to [support@replay.io](https://www.notion.so/Logging-in-as-support-replay-io-960f606f7d7b4b61872ddb6ce7003ced?pvs=21).
    
    ![https://media.discordapp.net/attachments/1155867540669612092/1155895939094020217/image.png?width=273&height=259](https://media.discordapp.net/attachments/1155867540669612092/1155895939094020217/image.png?width=273&height=259)
    

## Checking Mac Configuration

Because Replay records at the system level, small differences between Operating System versions and processors could make a difference. If Replay crashes or is slow, check version of the Mac OS is running and the processors on your computer to make sure they are up to date and when submitting a [bug report](https://github.com/replayio/devtools/issues/new/choose).

![Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/about-mac.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/about-mac.png)

## Importing SSL Certificate

If your organization uses custom certificates or you generate a certificate for local development, you may need to import it into the Replay Browser in order to make recordings.

[Importing SSL Certificate](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Importing%20SSL%20Certificate%20b7903b2fa1ce49228d000738cb81bcc8.md)

## Replay crashes during long recordings

We recommend limiting Replay recordings to 2 minutes in length — the shorter, the better. We are working on increasing the length of time Replay can record continuously and maintain performance.

## Recording applications with WebGL

Replay currently does not support recording applications with WebGL, and may experience errors. You can follow [the GitHub issue here](https://github.com/replayio/gecko-dev/issues/58) for updates.

## Recording multi-window application

Recording applications which use multiple windows is partially supported. When viewing a replay of a multi-window application, only graphics from one window will be shown, but you can still debug the code that executing in all windows.

## Replay can't be opened

This message appears if we fail to notarize a version of Replay. Please [let us know](Contact%20&%20Community%20096224a3bca4479b982ac572dc5c81d0.md) and we will fix it. If you would like to bypass this warning instead you can follow the steps [here](https://www.imore.com/how-open-apps-anywhere-macos-catalina-and-mojave).

![Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2020-12-08_at_8.33.46_PM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2020-12-08_at_8.33.46_PM.png)

## Viewing browser crashes

Visit `about:crashes` while in the Replay Browser to see if a browser crash has already been reported to our servers. Any crashes in the “Unsubmitted Crash Reports” section should be re-submitted using the “Submit All” button.

<aside>
💡 Browser crashes are also written to a text file which can be viewed locally.

</aside>

![Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2021-06-02_at_10.04.04_AM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2021-06-02_at_10.04.04_AM.png)

## Creating a New Profile

Sometimes it can be helpful to try creating a new browser profile. This will effectively clear the browser settings.

To create a new profile, go to `about:profiles` and click **Create a New Profile.**

![Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2021-07-28_at_6.34.08_PM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2021-07-28_at_6.34.08_PM.png)

## Verbose Logging

It's possible to start the Replay Browser from the terminal with verbose mode enabled to view additional logs. 

1. Quit Replay.
2. Open the terminal and run the command below.
3. Perform the action that was causing the issue.
4. Quit Replay.

```bash
RECORD_REPLAY_VERBOSE=1 /Applications/Replay.app/Contents/MacOS/replay
```

This will output detailed logs that can be submitted to our team along with a [bug report](https://github.com/replayio/devtools/issues/new/choose).

![Screen Shot 2021-08-16 at 12.34.26 PM.png](Troubleshooting%2013e647e0ab8d4185886d2b03e28944be/Screen_Shot_2021-08-16_at_12.34.26_PM.png)
# MeetingView User Manual

MeetingView is a macOS menu-bar app that shows your current or next meeting and joins it in one click. This manual covers MeetingView 2.0 and later.

**Contents**

1. [Install and update](#1-install-and-update)
2. [First launch](#2-first-launch)
3. [The menu bar](#3-the-menu-bar)
4. [The menu](#4-the-menu)
5. [Joining meetings](#5-joining-meetings)
6. [Reminders and notifications](#6-reminders-and-notifications)
7. [Dismissing meetings](#7-dismissing-meetings)
8. [Bookmarks and creating meetings](#8-bookmarks-and-creating-meetings)
9. [Keyboard shortcuts](#9-keyboard-shortcuts)
10. [Shortcuts and Siri](#10-shortcuts-and-siri)
11. [Links to MeetingView](#11-links-to-meetingview)
12. [Preferences reference](#12-preferences-reference)
13. [Supported meeting services](#13-supported-meeting-services)
14. [Troubleshooting](#14-troubleshooting)
15. [Privacy](#15-privacy)

---

## 1. Install and update

### Requirements

- macOS 14 Sonoma or later.

### Install

1. Download `MeetingView-<version>.dmg` from the [latest release](https://github.com/purpleax/MeetingView-Updates/releases/latest).
2. Open the disk image and drag **MeetingView** to **Applications**. If an older copy is there, replace it.
3. Open MeetingView from Applications. It appears in the menu bar, not the Dock.

Every release is signed and notarized by Apple, so macOS opens it without warnings.

### Updates

MeetingView updates itself:

- It checks for a new version once a day.
- **Check for Updates…** in the menu checks straight away.
- When an update is found, a window shows what's new in it, with buttons to install now or later.
- Updates are signed. MeetingView checks the signature before installing and refuses anything that doesn't match.

To change how updates work, open **Preferences → General → Updates**:

| Setting | What it does |
| --- | --- |
| Check for updates automatically | The daily check. Turn it off to check only when you choose to. |
| Download and install updates automatically | Installs updates in the background, without asking. Available only while automatic checks are on. |
| Version / Last checked | The version you're running and when it last checked. |
| Check Now | Same as **Check for Updates…** in the menu. |

Release notes for every version are on the [Releases page](https://github.com/purpleax/MeetingView-Updates/releases).

---

## 2. First launch

The first time you open MeetingView, a short setup walks you through:

1. **Welcome.**
2. **Choose your calendar source.** Pick **macOS Calendar app**. MeetingView then reads every account you've added to Calendar.app: iCloud, Google, Exchange and Microsoft 365, CalDAV and others.
3. **Verify calendar access.** macOS asks whether MeetingView may read your calendars. Choose **Allow Full Access**.
4. **Choose calendars.** Tick the calendars whose meetings should appear. You need at least one.
5. **Choose daily behavior.** Choose whether to:
   - launch MeetingView at login
   - which browser opens meeting links
   - whether to get a notification before meetings, and when.
6. **You're ready.** Your next meeting appears in the menu bar.

You can change all of this later in Preferences.

> **Using Google Calendar?** Add your Google account in **System Settings → Internet Accounts** (or in Calendar.app → Settings → Accounts). Its calendars then appear in MeetingView like any other. Current releases connect to calendars only through the macOS Calendar app.

If you denied calendar access by mistake, open **System Settings → Privacy & Security → Calendars**, turn on MeetingView, then quit and reopen it.

---

## 3. The menu bar

MeetingView's menu-bar item shows your next meeting, or the one you're in, for example:

> 🟦 Design review in 25m

### What it shows

| Situation | Menu bar shows |
| --- | --- |
| A meeting is coming up | Its title and the time until it starts, e.g. "Standup in 12m". |
| A meeting is in progress | Its title and the time left, e.g. "Standup now (8m left)". |
| Between meetings, with time to spare | Your free time, e.g. "Free for 1h 20m" or "Free until 14:30" (see below). |
| No more meetings | Just the icon. |
| Something needs attention | A warning, for example when calendar access is missing. |

You can change the icon, title and time under [Display & Events](#display--events).

### Free time

Between meetings, MeetingView shows how much free time you have instead of the next meeting:

- **Free for 1h 20m** counts down to your next meeting. This is the default.
- **Free until 14:30** shows when your next meeting starts.

The next meeting's title comes back **10 minutes before it starts**, and stays while a meeting is in progress. Free time only counts meetings later **today**, so you won't see "Free for 15h" overnight.

Hover over the free time to see which meeting is next. If you use the two-line layout (**Show time → show under title**), the meeting's name shows under the free time.

To change it, open **Preferences → Display & Events → Between meetings**. To always show the next meeting instead, choose **Show the next meeting**.

### Clicks

- **Click** the item to open the menu.
- **Right-click** the item to join the next meeting straight away.

### Long titles

If the menu bar is short of room, MeetingView shortens the title, or shows just the icon, so it never disappears behind the notch or other items. You can set a maximum title length in Preferences.

---

## 4. The menu

Click the menu-bar item to open the menu. From top to bottom:

### Timeline

A visual timeline of today, with each meeting as a block. Turn it off with **Display & Events → Show visual timeline of the day**.

### Current or next meeting

A summary card shows:

- **Current meeting** or **Next meeting**
- the title
- the time range
- the meeting service
- the account and calendar
- how long until it starts.

The **More actions** submenu beneath the card has the same actions as an event's details (see below).

If something's wrong, a warning appears here with a button to fix it:

| Warning | Button |
| --- | --- |
| Calendar permission is required | **Grant Calendar Permission** |
| No calendars selected | **Select Calendars in Preferences** |
| Calendar refresh failed | **Refresh sources** |
| Calendar refresh failed — showing last known data | (MeetingView keeps showing the last meetings it had until the next refresh works) |

### Today and Tomorrow

Your meetings for the day are listed with their start time (and end time, if you choose).

- **Click a meeting** to join it.
- **Past meetings** are greyed out.
- **Declined meetings** are struck through.
- **Pending and tentative invitations** can be shown, underlined or greyed out.
- A meeting's **service icon** and **calendar colour** appear beside it, if you choose.
- **Tomorrow's meetings** appear too if you choose **Show events for → today and tomorrow**.

#### Overlapping and back-to-back meetings

MeetingView flags meetings that clash:

- **Overlaps** (orange) means the meeting overlaps another one. Hover to see which.
- **Back-to-back** (grey) means it starts less than 5 minutes after the previous meeting ends, so there's no break. Hover to see which meeting it follows.

Flags only appear on meetings that haven't ended yet. Declined and canceled meetings are ignored.

#### Event details

Turn on **Display & Events → Show event: details as submenu** to add a submenu to each meeting with:

- title, status (Accepted, Declined, Tentative or Pending), time and duration, and calendar
- location, organizer, notes, and attendees with their responses
- **Copy meeting link**
- **Join with other link**, when the invite has more than one meeting link
- **Dismiss meeting** / **Remove dismissal** (see [Dismissing meetings](#7-dismissing-meetings))
- **Email attendees**, which opens a new email to everyone invited
- **Open in Calendar App**
- **Open in Fantastical**, if you have it installed.

### Actions

| Item | What it does |
| --- | --- |
| Join current / next event meeting | Opens the meeting link of the current or next meeting. |
| Join with other link | Appears when the invite has several meeting links; pick another one. |
| Create meeting | Starts a new meeting with the service you chose in Preferences. |
| Bookmarks | Your saved meeting links (see [Bookmarks](#8-bookmarks-and-creating-meetings)). |

### Quick Actions

| Item | What it does |
| --- | --- |
| Dismiss current / next meeting | Hides that meeting (see [Dismissing meetings](#7-dismissing-meetings)). |
| Remove all dismissals | Brings back every meeting you dismissed. |
| Open meeting from clipboard | Joins a meeting link you've copied. |
| Hide / Show meeting title | Hides the title in the menu bar, for screen sharing. |
| Refresh sources | Reloads your calendars now. MeetingView also refreshes every few minutes and whenever Calendar changes. |

### Bottom of the menu

- **Check for Updates…**
- **Preferences…** (⌘,)
- **Quit MeetingView** (⌘Q)

---

## 5. Joining meetings

You can join a meeting by:

- clicking it in the menu
- choosing **Join current/next event meeting**
- right-clicking the menu-bar item
- pressing your **Join next meeting** keyboard shortcut
- clicking **Join** on a notification
- asking Siri, or running the **Join Next Meeting** action in Shortcuts
- letting MeetingView join automatically (Preferences → Notifications → **Automatically join next event meeting**).

### How MeetingView finds the link

MeetingView looks for the meeting link in the event's:

1. conference details
2. URL field
3. location
4. notes.

It picks the link for a known meeting service over other links, and keeps passcodes such as Zoom's `?pwd=`. If an invite has several links, the others are under **Join with other link**.

A link MeetingView doesn't recognise still opens in your browser when it is in the event's URL, location or notes.

### Choosing what opens a link

Open **Preferences → Meeting Links**:

- **Default browser for meeting links**: the browser that opens meeting links. Choose **Default web browser** to use the macOS default.
- **Service-specific opening**: override the default for a service. For example:
  - open Zoom links in the **Zoom App** or **Zoom Web App**
  - Teams links in the **Teams App**
  - Google Meet in the **Google Meet PWA (Chrome)**.

  The Slack, Jitsi, Riverside, Tuple, Workplace and MeetInOne apps can be chosen too. If the app isn't installed, MeetingView tells you, and you can switch back to a browser.
- **Configure Browsers…**: add browsers that aren't listed, such as a specific Chrome profile or another app.
  - **Add → Web browser** lets you name one and pick its app.
  - **Add → All system web browsers** adds every browser installed on your Mac.

For safety, MeetingView only opens web links and Zoom or Discord app links from calendar invites. Links to files, file shares or other apps are ignored.

---

## 6. Reminders and notifications

Open **Preferences → Notifications**.

### Meeting Alerts

| Setting | Options |
| --- | --- |
| Send a system notification | When the event starts, or 1, 3 or 5 minutes before. On by default, at the start. |
| Show a fullscreen notification | A full-screen reminder that's hard to miss: when it starts, or 1, 3 or 5 minutes before. |
| Also show fullscreen notifications for events without meeting links | Shows full-screen reminders for in-person meetings too, with just a Dismiss button. |
| Send a notification when event ends | When it ends, or 1, 3 or 5 minutes before. |

A meeting notification has these buttons:

- **Join**
- **Dismiss**
- **Snooze until start time**
- **Snooze for 5, 10, 15 or 30 min**

Notifications are time-sensitive, so they can show through a Focus.

> **Tip:** if notifications vanish before you see them, MeetingView tells you they're set to *Banners*. In **System Settings → Notifications → MeetingView**, choose **Alerts** to keep them on screen until you act on them. If notifications are turned off there, MeetingView warns you in Preferences.

### Automatic Joining

**Automatically join next event meeting** opens your next meeting's link by itself, when it starts or 1, 3 or 5 minutes before.

Automatic joining, full-screen reminders and notifications skip:

- meetings you've declined or dismissed
- canceled meetings
- events the [Display & Events](#display--events) settings hide.

---

## 7. Dismissing meetings

Dismissing a meeting hides it from MeetingView without changing your calendar. A dismissed meeting:

- isn't shown in the menu bar
- isn't joined automatically
- doesn't send notifications
- doesn't run Shortcuts or scripts.

To dismiss one:

- choose **Quick Actions → Dismiss current/next meeting**
- choose **Dismiss meeting** in the event's details
- click **Dismiss** on its notification
- run the **Dismiss Nearest Meeting** Shortcuts action.

Dismissed meetings stay in the menu, marked *dismissed*. To bring them back, choose **Remove dismissal** on one, or **Quick Actions → Remove all dismissals** for all of them.

---

## 8. Bookmarks and creating meetings

### Bookmarks

Bookmarks are meeting links you use often, such as a team room or a personal Zoom. They appear in the menu under **Bookmarks**.

To add one:

1. Open **Preferences → Meeting Links → Bookmarks**.
2. Click **Add bookmark**.
3. Enter a name, the link or phone number, and its service.

To delete a bookmark, click the **×** button next to it.

### Create meeting

**Create meeting** in the menu (or its keyboard shortcut) starts a new meeting. Choose the service under **Preferences → Meeting Links → Create meetings → Create meetings via**:

- Google Meet
- Zoom
- Microsoft Teams
- Jam
- CoScreen
- Google Calendar (new event)
- Outlook Live
- Outlook Office365
- **Custom URL**: any link you like. Must start with `http://` or `https://`.

**Use web browser** picks the browser it opens in.

> **Tip:** Google Meet can choose the account in the link, for example `https://meet.google.com/new?authuser=1`. Use that as a Custom URL.

---

## 9. Keyboard shortcuts

Set global keyboard shortcuts in **Preferences → General → Keyboard Shortcuts**. None are set until you record one. Click a field, then press the keys you want.

| Shortcut | What it does |
| --- | --- |
| Open menu | Opens MeetingView's menu. |
| Join next meeting | Joins the current or next meeting. |
| Create meeting | Starts a new meeting. |
| Join meeting from clipboard | Joins a meeting link you've copied. |
| Toggle title visibility in status bar | Hides or shows the meeting title in the menu bar. |

These work from any app.

---

## 10. Shortcuts and Siri

### Actions in the Shortcuts app

Search for **MeetingView** in the Shortcuts app's action list.

| Action | Returns |
| --- | --- |
| **Join Next Meeting** | Joins your current or next meeting. |
| **Get Next Meeting** | Your next meeting, as a *Meeting* with these properties: Title, Start Date, End Date, Meeting Link, Meeting Service, Calendar, Location and In Progress. Turn off **Include Meeting in Progress** to skip a meeting you're already in. |
| **Time Until Next Meeting** | The number of minutes until your next meeting starts, as a number. Meetings already in progress are skipped. |
| **Get Nearest Event Details** | One detail of the nearest meeting, as text: Title, Start Date, End Date, Meeting Link, Meeting Service, Calendar, URL, Notes, Location or Attendees. |
| **Dismiss Nearest Meeting** | Dismisses the nearest meeting. |

"Next meeting" means the next timed meeting that you haven't declined or dismissed, and that isn't canceled.

### Siri and Spotlight

These phrases work without any setup:

- "Join my next meeting in MeetingView"
- "Join my meeting with MeetingView"
- "What's my next meeting in MeetingView"
- "Get my next meeting in MeetingView"
- "How long until my next meeting in MeetingView"
- "When is my next meeting in MeetingView"

MeetingView's actions can also show up in Spotlight.

### Ideas

- **Leave on time:** a shortcut that runs **Time Until Next Meeting** and warns you if it's under 5 minutes.
- **Status at a glance:** add **Get Next Meeting** to a Shortcuts widget.
- **Before you join:** a shortcut that runs **Join Next Meeting**, then turns on Do Not Disturb.

---

## 11. Links to MeetingView

`meetingview://preferences` opens MeetingView's Preferences, for example from a script or a link.

---

## 12. Preferences reference

Open Preferences from the menu (**Preferences…**, or ⌘, while the menu is open). The sidebar has two groups: **Setup** and **Experience**.

### General

- **About**: version, a link to GitHub, and **Copy diagnostics**, which copies a report to attach to a bug report. Read it before sharing it.
- **General Settings**:
  - **Launch after login**
  - **Language…**: opens System Settings, where you choose MeetingView's language (**General → Language & Region → Applications**). A change takes effect when MeetingView is relaunched. MeetingView 2.0 is in English; other languages will follow.
  - **Time format**: 12-hour (AM/PM) or 24-hour. Used everywhere MeetingView shows a time.
  - **App icon**: blue (the default), green, purple, pink, yellow or graphite. Your choice appears in MeetingView's own windows, alerts and update prompts. Finder and notifications always show the blue icon.
- **Updates**: see [Install and update](#updates).
- **Keyboard Shortcuts**: see [Keyboard shortcuts](#9-keyboard-shortcuts).

### Calendars

- **Calendar Source**: shows where calendars come from, its status, and buttons to **Refresh** or **Open Calendar Settings**. Statuses:
  - **Up to date**
  - **Showing cached data**
  - **Last refresh failed**
  - **Calendar permission required**
- **Select calendars to show meetings in the menu bar**: tick the calendars to include. They're grouped by account.
- **Unavailable selected calendars**: calendars you chose that no longer exist, for example after removing an account. Click **Remove** to clear them.

### Meeting Links

- **Open meeting links**: the default browser, service-specific apps, and **Configure Browsers…** (see [Joining meetings](#choosing-what-opens-a-link)).
- **Create meetings**: the service for **Create meeting** and the browser it opens in.
- **Bookmarks**: see [Bookmarks](#bookmarks).

### Display & Events

**Events**: which events MeetingView shows, in the menu bar and the menu.

| Setting | Options |
| --- | --- |
| Show events for | today, or today and tomorrow |
| All-day events | show, show only those with meeting links, or hide |
| Events without a meeting link | show, show as inactive, or hide |
| Events without guests | show, show as inactive, or hide (events with only you in them) |
| Pending events | show, show as underlined, show as inactive, or hide |
| Tentative events | show, show as underlined, show as inactive, or hide |
| Declined events | show with strikethrough, show as inactive, or hide |
| Past events | show, show as inactive, or hide |

Hidden events are also ignored when MeetingView picks the next meeting, sends notifications and joins automatically.

**Status bar**: what the menu-bar item looks like.

| Setting | Options |
| --- | --- |
| Icon | Calendar, MeetingView, event-specific (the meeting service's icon, e.g. Teams), or no icon |
| Title | event title, generic title ("Meeting"), dot (•), or hide. With the event title you can shorten it to a number of characters. |
| Show time | show, show under title (two lines), or hide |
| Between meetings | Show the next meeting, Free for 1h 20m, or Free until 14:30 (see [Free time](#free-time)) |
| Show only events starting within | Only show a meeting in the menu bar once it's this close (5 minutes to 12 hours). |
| Ongoing event visibility | When to move on from a meeting in progress to the next one: hide after start, hide 10 min after start, or hide 10 min before next event |

**Menu**: what the menu looks like.

| Setting | What it does |
| --- | --- |
| Show visual timeline of the day | The timeline at the top of the menu. |
| Show event: end time | Shows end times as well as start times. |
| Show event: icon | Shows each meeting's service icon. |
| Show event: calendar color | Shows each meeting's calendar colour. |
| Show event: details as submenu | Adds the [details submenu](#event-details) to each meeting. |
| Shorten event title to | Limits titles in the menu to 20–100 characters. |

### Notifications

See [Reminders and notifications](#6-reminders-and-notifications).

---

## 13. Supported meeting services

MeetingView recognises links for more than 60 services. Its icon shows in the menu, and you can choose how to open each service:

8x8, Amazon Chime, Around, Blackboard Collaborate, Blizz, BlueJeans, Cal Video, Chorus, Cisco Webex, CoScreen, Demio, Demodesk, Discord, FaceTime, FaceTime Audio, Feishu, Facebook Workspace, Gather, Gong, Google Duo, Google Hangouts, Google Meet, GoToMeeting, GoToWebinar, Jam, Jitsi, Join.me, Lark, Lifesize, LiveKit Meet, Livestorm, Luma, Meetecho, Microsoft Teams, oVice, Pop, Preply, Pumble, Reclaim.ai, RingCentral, Riverside, Skype, Skype for Business, Slack (huddles), StarLeaf, StreamYard, Teamviewer Meeting, Teemyco, Tencent VooV, Tuple, Uber Conference, UserZoom, Venue, Vimeo, Vowel, VSee, Whereby, YouTube, Zhumu, Zoho Cliq, Zoom and ZoomGov. Phone numbers work too.

If your service isn't listed, MeetingView can still open its link.

---

## 14. Troubleshooting

**No meetings appear.**

1. Open **Preferences → Calendars** and check that at least one calendar is ticked and the status says **Up to date**.
2. If it says **Calendar permission required**, open **System Settings → Privacy & Security → Calendars**, turn on MeetingView, then quit and reopen it.
3. Check that the meeting shows in Calendar.app. MeetingView only sees what Calendar.app sees.
4. Check **Display & Events**: the meeting may be hidden, for example because it's declined, all-day, has no link, or is outside **Show only events starting within**.
5. Choose **Quick Actions → Refresh sources**.

**The menu bar shows "Free for…" but I want the meeting.** Set **Display & Events → Between meetings** to **Show the next meeting**.

**A meeting link isn't detected.** Make sure the link is in the event's location, URL or notes. Links for services MeetingView doesn't know open in your browser.

**A link opens in the wrong app or browser.** Check **Meeting Links → Service-specific opening** for that service.

**Notifications don't appear.**

- Check **System Settings → Notifications → MeetingView** is on.
- Check that a Focus isn't hiding them. MeetingView's notifications are time-sensitive; allow time-sensitive notifications in the Focus settings.

**Siri doesn't recognise the phrases.** Open MeetingView once after installing or updating. Siri can take a few minutes to learn new phrases.

**Check for Updates says I'm up to date, but there's a newer release.** The update feed can take a few minutes to reach everyone after a release. Try again a little later.

**Reporting a problem.** Include:

- your MeetingView and macOS versions
- what you expected and what happened
- the output of **Preferences → General → Copy diagnostics**.

Read the diagnostics before sharing them: they can include calendar names.

---

## 15. Privacy

- MeetingView doesn't collect or send any personal data.
- Your calendar data stays on your Mac. MeetingView reads it only to show your meetings and find their links.
- The only connection MeetingView makes is the daily update check to this repository, plus the meeting links you choose to open.

---

MeetingView is © 2026 Guy Brown, all rights reserved. It updates itself with Sparkle, used under the MIT License; both notices are included in each disk image.

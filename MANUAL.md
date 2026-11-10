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
16. [Ask your calendar](#16-ask-your-calendar)
17. [Focus time and working hours](#17-focus-time-and-working-hours)
18. [Focus filters](#18-focus-filters)
19. [The widget](#19-the-widget)

---

## 1. Install and update

### Requirements

- macOS 26 or later (MeetingView 2.0 to 2.2 ran on macOS 14).
- [Ask your calendar](#16-ask-your-calendar) also needs a Mac that supports Apple Intelligence, with it turned on. Everything else works without it.

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
| No more meetings | Just the MeetingView icon, in the colour you chose for the app icon. (A calendar icon instead, if the Icon setting is "Calendar".) |
| Something needs attention | A warning, for example when calendar access is missing. |

You can change the icon, title and time under [Display & Events](#display--events).

### Free time

Between meetings, MeetingView shows how much free time you have instead of the next meeting:

- **Free for 1h 20m** counts down to your next meeting. This is the default.
- **Free until 14:30** shows when your next meeting starts.

The next meeting's title comes back **10 minutes before it starts**, and stays while a meeting is in progress. Free time only counts meetings later **today**, so you won't see "Free for 15h" overnight.

Hover over the free time to see which meeting is next. If you use the two-line layout (**Show time → show under title**), the meeting's name shows under the free time.

To change it, open **Preferences → Display & Events → Between meetings**. To always show the next meeting instead, choose **Show the next meeting**.

### Urgency colours

The title in the menu bar changes colour when a meeting needs you:

- **Orange** in the last two minutes before it starts.
- **Red** for the first ten minutes after it starts, if it has a meeting link and you haven't joined it from MeetingView. Joining from MeetingView turns it back at once.

VoiceOver says "starting soon" or "started" after the countdown. To change when it turns orange (1, 2, 3 or 5 minutes), or to turn the colours off, use Preferences → Display & Events → Status bar → **Colour the title when a meeting is about to start**.

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

On a day with two or more meetings, a **summary** sits under the day's heading, for example "4 meetings, 3h 30m in all. Busiest 10:00 – 13:00; 2 overlap at 14:00."

- The first part counts the day's meetings and the time they take. Time when two meetings overlap is counted once. Declined, cancelled and all-day events are left out.
- "Busiest" is the longest run of meetings with no real break between them.
- A quiet day shows its longest free stretch instead, measured within your [working hours](#working-hours).
- To hide the summary, turn off Preferences → Display & Events → **Show a summary of each day**.

#### Overloaded days

Under the summary, an orange warning appears when a day asks too much:

- **No lunch break**: there is no free half hour between 11:30 and 14:00.
- **Back-to-back 09:00 – 13:00**: three or more meetings in a row, lasting three hours or more, without a 15-minute break.

The warning also names the meeting still to come that looks most optional, and why: it's a [hold](#holds), you're an optional guest, you haven't accepted it, or ten or more people are invited. A meeting you organize is never suggested. MeetingView only suggests; it doesn't decline or change anything.

If you use the [morning summary](#morning-summary), the warning is added to it. To turn warnings off, use Preferences → Display & Events → Menu → **Warn about overloaded days**.

#### Holds

A block that only reserves time, such as "Hold", "Placeholder for offsite" or "Keep free", is labelled **Hold** at the end of its row, so you can tell it from a real meeting.

- A hold is a block with no meeting link and nobody else invited.
- It is still listed and you are still reminded about it. The only difference is that a hold doesn't count towards an overloaded day, and is the first thing suggested when a day is overloaded anyway.
- Blocks whose wording is less obvious ("Provisional slot for the vendor demo") are read on your Mac with Apple Intelligence, if it is turned on. Without it, only the obvious ones are labelled.

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
- **Documents**: what the invitation links to, such as Google Docs, Sheets, Slides and Drive, Notion, Figma, Confluence, Dropbox, Miro and Microsoft 365 files, and any other web page (shown by its site). Click one to open it in your browser; hover to see the full address. The meeting link itself isn't repeated here, and up to eight are listed
- **Prep**, for a meeting with a long invitation (see [below](#meeting-prep))
- **Copy meeting link**
- **Call**, when the invitation has no meeting link but gives a phone number. It dials the number, then enters the passcode or PIN if the invitation gives one, using your Mac's calling app (FaceTime with your iPhone, for example). The number and code are shown in the menu item so you can check them first
- **Join with other link**, when the invite has more than one meeting link
- **Dismiss meeting** / **Remove dismissal** (see [Dismissing meetings](#7-dismissing-meetings))
- **Email attendees**, which opens a new email to everyone invited
- **Running late** (see [below](#running-late))
- **Open in Maps**, for a meeting with a location and no meeting link. It opens directions from where you are
- **Open in Calendar App**
- **Open in Fantastical**, if you have it installed.

#### Meeting prep

When a meeting's invitation is long, its details include **Prep, summarised on this Mac**: a short list of the **Agenda**, and what you're asked to bring, read or do **Before the meeting**.

- The summary is made when you open the details, and takes a second or two the first time. After that it appears at once.
- It is made on your Mac with Apple Intelligence. The invitation isn't sent anywhere.
- MeetingView checks every line against the invitation and leaves out anything its text doesn't support, including any number or time the invitation doesn't contain. If nothing is left, it says no agenda or preparation was found.
- It is a summary, not a replacement: the full notes are still shown above it.
- It appears only for invitations of a few paragraphs or more, and only on a Mac with Apple Intelligence turned on.
- To turn it off, use Preferences → Display & Events → Menu → **Summarise long invitations in the details**.

#### Running late

**Running late** → 5, 10 or 15 minutes opens a new email in your mail app, addressed and written: the meeting's title as the subject and your message as the text. Check it and press Send; MeetingView sends nothing itself. You'll find it in a meeting's details submenu, and under **More actions** for the current or next meeting.

- **Who gets it:** the organizer, or everyone invited. If you are the organizer, it goes to everyone else.
- **What it says:** "I'm running about 10 minutes late." unless you write your own. Put `{minutes}` where the number should go.
- Both are set in Preferences → Notifications → **Running Late Message**.
- The item is missing when the meeting is over or nobody else in it has an email address.

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

### Morning summary

Turn on Preferences → Notifications → **Send a summary of the day's meetings** to get one notification each morning, for example "5 meetings, 2h 35m in all. Busiest 09:50 – 11:10; 3 overlap at 10:25. First: Standup at 08:00."

- Pick the time (05:00 to 12:00; 08:30 unless you change it).
- If your Mac is asleep or locked then, the summary arrives when you next unlock it, up to four hours later. After that it is skipped for the day.
- A day with no meetings gets no summary.
- If the menu bar hides meeting titles, the summary hides them too.

### Leave-by reminders

For a meeting you travel to (one with a location and no meeting link), MeetingView can tell you when it's time to leave: "Time to leave for Site visit. Leave by 13:30 to arrive for 14:00. About 25m by car."

Turn on Preferences → Notifications → **Remind me when it's time to leave for in-person meetings**. The first time, macOS asks whether MeetingView may use your location.

- **I travel by:** car (the default), on foot or public transport.
- **When it arrives:** MeetingView allows five minutes at the other end, and reminds you five minutes before you need to set off.
- **Without a travel time** the reminder comes a fixed time before the start instead: 15 minutes unless you change **With no travel time, remind me**. This happens when location access is off, or when Maps can't find the place (a room name, for example) or a route.
- If you're already there, there's no reminder.
- Meetings you've declined or dismissed, and canceled meetings, are skipped.

**What is sent:** to get the travel time, MeetingView sends the meeting's location and your Mac's location to Apple Maps. Nothing else about the meeting is sent, and nothing is sent while the setting is off. To stop using your location but keep the reminders, turn MeetingView off in System Settings → Privacy & Security → Location Services.

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
| Ask your calendar | Opens [Ask](#16-ask-your-calendar). |
| Send “running late” for the next meeting | Opens the [running-late email](#running-late) for the current or next meeting, saying 5 minutes. |

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
| **Ask Your Calendar** | The answer to a question about your meetings or free time, as text. See [Ask your calendar](#16-ask-your-calendar). |
| **Send Running Late Message** | Opens the [running-late email](#running-late) for your current or next meeting. Set **Minutes Late** (1–120; 5 unless you change it). |

"Next meeting" means the next timed meeting that you haven't declined or dismissed, and that isn't canceled.

### Siri and Spotlight

These phrases work without any setup:

- "Join my next meeting in MeetingView"
- "Join my meeting with MeetingView"
- "What's my next meeting in MeetingView"
- "Get my next meeting in MeetingView"
- "How long until my next meeting in MeetingView"
- "When is my next meeting in MeetingView"
- "Say I'm running late with MeetingView"
- "Tell my meeting I'm running late with MeetingView"

MeetingView's actions can also show up in Spotlight.

### Ideas

- **Leave on time:** a shortcut that runs **Time Until Next Meeting** and warns you if it's under 5 minutes.
- **Status at a glance:** add **Get Next Meeting** to a Shortcuts widget.
- **Before you join:** a shortcut that runs **Join Next Meeting**, then turns on Do Not Disturb.

---

## 11. Links to MeetingView

`meetingview://preferences` opens MeetingView's Preferences, for example from a script or a link.

The widget's Join buttons use `meetingview://join?id=…`. It joins a meeting MeetingView is already showing, and can't open anything else.

---

## 12. Preferences reference

Open Preferences from the menu (**Preferences…**, or ⌘, while the menu is open). The sidebar has two groups: **Setup** and **Experience**.

### General

- **About**: version, a link to GitHub, and **Copy diagnostics**, which copies a report to attach to a bug report. Read it before sharing it.
- **General Settings**:
  - **Launch after login**
  - **Language…**: opens System Settings, where you choose MeetingView's language (**General → Language & Region → Applications**). A change takes effect when MeetingView is relaunched. MeetingView 2.0 is in English; other languages will follow.
  - **Time format**: 12-hour (AM/PM) or 24-hour. Used everywhere MeetingView shows a time.
  - **App icon**: blue (the default), green, purple, pink, yellow or graphite. Your choice appears in MeetingView's own windows, alerts and update prompts, and on the MeetingView icon in the menu bar. Finder and notifications always show the blue icon.
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
- **Focus Filters**: how to show different calendars during a Focus, with a button that opens Focus settings (see [Focus filters](#18-focus-filters)).

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
| Colour the title when a meeting is about to start | Orange before the start, red for ten minutes after it if you haven't joined (see [Urgency colours](#urgency-colours)). On by default. |
| Turn orange | 1, 2, 3 or 5 minutes before the start. |

**Menu**: what the menu looks like.

| Setting | What it does |
| --- | --- |
| Show visual timeline of the day | The timeline at the top of the menu. |
| Show a summary of each day | The line under Today and Tomorrow that sums up the day's meetings. |
| Warn about overloaded days | The warning for a day with no lunch break or a long run of meetings (see [Overloaded days](#overloaded-days)). On by default. |
| Spot holds and dial-in numbers | Labels [holds](#holds) and adds the Call action for phone numbers in invitations. On by default. |
| Show event: end time | Shows end times as well as start times. |
| Show event: icon | Shows each meeting's service icon. |
| Show event: calendar color | Shows each meeting's calendar colour. |
| Show event: details as submenu | Adds the [details submenu](#event-details) to each meeting. |
| Summarise long invitations in the details | Adds [meeting prep](#meeting-prep) to the details. Needs Apple Intelligence. On by default. |
| Shorten event title to | Limits titles in the menu to 20–100 characters. |

### Notifications

See [Reminders and notifications](#6-reminders-and-notifications).

| Setting | What it does |
| --- | --- |
| Send a summary of the day's meetings, Send it at | The [morning summary](#morning-summary) and its time. Off by default. |
| Remind me when it's time to leave for in-person meetings, I travel by, With no travel time, remind me | [Leave-by reminders](#leave-by-reminders). Off by default. |
| Running Late Message: Send it to, Message | Who the [running-late email](#running-late) goes to, and its wording. |

### Planning

See [Focus time and working hours](#17-focus-time-and-working-hours).

| Setting | What it does |
| --- | --- |
| Working Hours: Start, End, Days | The hours and days free time and focus slots are looked for in. Default 09:00 to 17:30, Monday to Friday. |
| Add focus blocks to | The calendar a focus block is added to. "Default calendar" is the one your Mac uses for new events. |
| Title | What a focus block is called. Default "Focus time". |

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
- MeetingView adds to your calendar only when you click **Block** on a focus slot. It never changes or removes any other event.
- The only connection MeetingView makes is the daily update check to this repository, plus the meeting links you choose to open.
- One exception, off unless you turn it on: [leave-by reminders](#leave-by-reminders) send a meeting's location and your Mac's location to Apple Maps to get a travel time.

---

## 16. Ask your calendar

Ask MeetingView a question in plain language and it answers from your calendar.

### Asking

Choose **Ask Your Calendar…** in the menu, or press the keyboard shortcut if you've set one (Preferences → General → Keyboard Shortcuts). Type a question and press Return. Press Esc, or click anywhere else, to close the panel.

Questions it understands:

| You ask | You get |
| --- | --- |
| "When am I free tomorrow afternoon?" | The free gaps in that part of the day. |
| "Find me a two hour gap this week" | Gaps at least that long, day by day. |
| "Find me two hours of focus time before Thursday" | Slots of that length you can [block in your calendar](#17-focus-time-and-working-hours). |
| "Any free time today after 3?" | Gaps after that time. |
| "What's on my calendar on Thursday?" | That day's meetings, starting with a summary of the day. |
| "How does my week look?" | The week's meetings, with how many, how long in all, and the busiest day. |
| "What's my next meeting?" | The next meeting and how long until it starts. |
| "Do I have anything with Sarah this week?" | Meetings with that person, or with those words in the title. |
| "When is the budget planning meeting?" | That meeting, wherever it is in the next two weeks. |
| "Am I double booked this week?" | Meetings that overlap. |

A meeting you can join has a **Join** button beside it.

### What to know

- **How your question was understood** is shown under each answer, for example "Free time · Thu 12 Nov · after 14:00 · at least 2h". If that isn't what you meant, word the question differently.
- **Two weeks ahead.** Ask looks from today to 14 days ahead, in the calendars you've selected.
- **Free time** is looked for within your [working hours](#working-hours): weekdays from 09:00 to 17:30 unless you change them, or up to 22:00 if you ask about the evening. Gaps shorter than 15 minutes are left out, and so is time that has already passed.
- **Busy** means any timed meeting in your calendars, including ones you've chosen to hide from the menu. Meetings you've declined, cancelled meetings and all-day events don't count as busy.
- **"Before Thursday"** means every day from today up to Wednesday. "By" works the same way. "Until Thursday" includes Thursday.
- **Calendar questions only.** For anything else, MeetingView says it can only answer questions about your meetings and free time.
- **It changes nothing unless you click Block.** Ask only reads your calendar. The one exception is a focus slot's **Block** button, which adds that slot as an event.
- **English works best.** Other languages may work but haven't been tested.

### Privacy

Ask uses Apple Intelligence on your Mac. Your question is read by Apple's on-device model, which never sees your calendar; MeetingView then looks up the answer itself. Nothing is sent anywhere, and your questions aren't saved or logged.

### If Ask isn't available

The panel tells you why:

- **Apple Intelligence is turned off:** turn it on in System Settings → Apple Intelligence & Siri.
- **Apple Intelligence is still getting ready:** macOS is downloading its model. Try again later.
- **This Mac doesn't support Apple Intelligence:** Ask can't run on it. The rest of MeetingView works as usual.

### From Shortcuts and Siri

The **Ask Your Calendar** action takes a question and returns the answer as text. With Siri, say "Ask MeetingView about my calendar", then your question. Focus slots are listed, but they can only be blocked from the panel.

---

## 17. Focus time and working hours

### Finding and blocking focus time

Open [Ask your calendar](#16-ask-your-calendar) and ask for focus time:

- "Find me two hours of focus time before Thursday"
- "I need an hour of deep work this afternoon"
- "Block 90 minutes to focus on Friday"

MeetingView lists slots of that length that are free of meetings and inside your working hours. If you don't give a length, slots are one hour. If you don't name a day, it looks over the next seven days. You get up to three slots a day and eight in all.

Each slot has a **Block** button:

1. Under the slots, MeetingView says what Block will do, for example "Block adds “Focus time” to the Work calendar."
2. Click **Block**. The slot is added to that calendar as a busy event with no guests.
3. The row shows "Added to Work" and an **Undo** button. Undo removes the event again.

MeetingView adds an event only when you click Block. It never changes or removes any other event, and Undo is only offered while the panel is open; after that, delete the block in your calendar app.

If the row shows "Couldn't add it", hover over it to see why, then click **Try Again**.

### Working hours

Preferences → **Planning** → Working Hours sets when free time and focus slots are looked for:

- **Start** and **End**, in half-hour steps.
- **Days**: click a day to include or leave it out. At least one day stays on.

A question about a range, such as "this week", skips days you don't work. A question about one named day, such as "Am I free on Saturday?", is answered whichever day it is.

### Where focus blocks go

Preferences → **Planning** → Focus Blocks:

- **Add focus blocks to**: "Default calendar" uses the calendar your Mac adds new events to (Calendar → Settings → General → Default Calendar). Or pick any calendar you can add events to.
- **Title**: what each block is called. Leave it empty for "Focus time".

The calendar you choose counts as busy even if you haven't selected it to show in MeetingView, so a slot you've blocked isn't offered again.

---

## 18. Focus filters

A macOS Focus can change what MeetingView shows while it is on. For example, show only your work calendars during Work.

1. Open System Settings → Focus and choose a Focus, such as Work.
2. Under Focus Filters, click **Add Filter** and choose **MeetingView**.
3. Choose the **Calendars** to show during that Focus. They can be any of your calendars, including ones you don't normally show in MeetingView. Leave it empty to keep your usual calendars.
4. Turn on **Silence Notifications** if you don't want MeetingView's meeting notifications during that Focus.

While the Focus is on:

- The menu bar, the menu, reminders and Ask use the calendars you chose. The menu says "Focus filter: calendars shown: 2" so you know why.
- With notifications silenced, MeetingView sends no meeting notifications and holds back the fullscreen reminder and the morning summary. Automatic joining still works.
- Your selection in Preferences → Calendars isn't changed, and is used again as soon as the Focus ends.

Preferences → Calendars → **Focus Filters** has a button that opens Focus settings.

---

## 19. The widget

MeetingView has a widget for the desktop and Notification Centre.

### Adding it

1. Right-click the desktop and choose **Edit Widgets** (or click the date in the menu bar and choose **Edit Widgets** at the bottom).
2. Search for **MeetingView**.
3. Pick a size and drag it to the desktop or into Notification Centre.

### What it shows

| Size | Shows |
| --- | --- |
| Small | Your current or next meeting: its title, its times, and "Now" or a countdown. Click anywhere on it to join. |
| Medium | Up to three meetings, each with a **Join** button. |
| Large | Up to seven meetings, each with a **Join** button, with a heading for tomorrow's. |

The widget lists the same meetings as the menu. It follows your calendars, your [Display & Events](#display--events) settings and any [Focus filter](#18-focus-filters). All-day events, meetings that have ended and meetings you've [dismissed](#7-dismissing-meetings) are left out. If you hide meeting titles in the menu bar, the widget shows "Meeting" instead.

**Join** appears on meetings that have a meeting link, and opens it the way the menu does.

### Good to know

- **MeetingView has to be running.** The widget shows what MeetingView last worked out; it doesn't read your calendar itself. Turn on **Launch after login** in Preferences → General so it always is.
- If MeetingView hasn't run for about a day, the widget says "Open MeetingView to see your meetings".
- macOS may ask you to click a desktop widget once to bring it forward before its buttons respond.

---

MeetingView is © 2026 Guy Brown, all rights reserved. It updates itself with Sparkle, used under the MIT License; both notices are included in each disk image.

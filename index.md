# Privacy Policy for MindShift

**Last updated:** 30 April 2026
**Effective date:** 30 April 2026

MindShift ("we", "our", or "the app") is operated by Vivek Yadav. This
policy describes what information the app handles, why, and what choices
you have. We have designed MindShift so that **no personal data ever
leaves your device**.

---

## 1. Summary

| Question                                       | Answer                                |
| ---------------------------------------------- | ------------------------------------- |
| Does MindShift collect personal data?          | **No.**                               |
| Does MindShift send data over the internet?    | **No - the app has no network access.** |
| Does MindShift use analytics or advertising?   | **No.**                               |
| Does MindShift share data with third parties?  | **No.**                               |
| Does MindShift read your screen content?       | **No.**                               |
| Does MindShift log keystrokes?                 | **No.**                               |

---

## 2. What the app does

MindShift helps you reduce time spent in distracting apps by requiring
you to solve a chess puzzle before the chosen app opens. You select
which apps are "guarded". When you tap one of them, MindShift presents
a chess puzzle. After you solve it (or tap "Give up"), the guarded app
opens.

To make this work, the app needs to know **which app you just tried to
open**. Android's only supported way to detect this from the background
is the AccessibilityService API.

---

## 3. Information the app processes

All of the items below stay on your device. None are transmitted to us
or any third party.

### 3.1 Foreground app package names
When you open an app on your phone, Android tells our AccessibilityService
the **package name** (for example, `com.instagram.android`). The service
checks whether you have marked this package as guarded. If yes, it shows
a challenge. If no, it ignores the event.

The app **does not read** screen contents, text fields, notifications,
keystrokes, or any other accessibility event data beyond the package
name.

### 3.2 List of installed apps
To let you choose which apps to guard, MindShift reads the list of apps
installed on your device using Android's `QUERY_ALL_PACKAGES` permission.
The list is shown to you on the "Guarded apps" screen and is never sent
anywhere.

### 3.3 Local challenge history
When you complete or give up on a challenge, MindShift writes a row into
a local SQLite database stored only on your device. Each row contains:
- The package name of the guarded app
- Which challenge type fired (currently always "chess puzzle")
- Outcome: `completed` or `gaveUp`
- How long the challenge took, in milliseconds
- A timestamp

This history powers the in-app **Stats** screen. It is never uploaded.

### 3.4 Your settings
Your guarded-app selection, chess difficulty level, puzzle count, and
similar preferences are stored locally (in the app's private storage and
in the same SQLite database as above).

---

## 4. Permissions and why we need them

| Permission                          | Why it is requested                                    |
| ----------------------------------- | ------------------------------------------------------ |
| `BIND_ACCESSIBILITY_SERVICE`        | Detect the package name of the app you just opened.   |
| `FOREGROUND_SERVICE` / `_SPECIAL_USE` | Keep the guard alive while you use other apps.       |
| `POST_NOTIFICATIONS`                | Display the persistent guard-active notification.     |
| `QUERY_ALL_PACKAGES`                | Show your installed apps so you can pick which to guard. |

We do **not** request internet access, location, contacts, camera,
microphone, storage, SMS, call log, or any other permission.

---

## 5. Network usage

MindShift's Android manifest declares `usesCleartextTraffic="false"` and
ships an empty network-security configuration. The app does not make
HTTP requests to our servers, to Lichess, to Google, or to any other
host while running.

The chess puzzles displayed in the app are bundled into the app at build
time from Lichess's public CC0 puzzle dataset. No live API calls are
made.

---

## 6. Third parties

MindShift contains **no analytics SDKs, no advertising SDKs, and no
crash-reporting SDKs**. We do not use Google Firebase, Google Analytics,
Meta SDKs, AppsFlyer, Adjust, RevenueCat, or any similar service in this
release.

(If a future release adds a paid subscription, we will integrate Google
Play Billing and may add RevenueCat for entitlement management. This
policy will be updated **before** that release ships and the integration
will only run if you choose to subscribe.)

The app uses two pieces of third-party **content** under open licences:

- **Chess piece artwork**: adapted from "Chess kdt45" by Cburnett,
  licensed under [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).
  Attribution is shown in the app's "About" screen.
- **Chess puzzles**: from the Lichess open puzzle database, released
  under CC0 (public domain).

Neither of these involves any data exchange - the assets are bundled at
build time.

---

## 7. Children

MindShift is not directed at children under 13. We do not knowingly
collect any data from children, because we do not collect any data from
anyone.

---

## 8. Data retention and deletion

Because all data is stored only on your device:
- **You can delete it at any time** by clearing the app's storage in
  Android Settings or by uninstalling MindShift.
- **Uninstalling the app removes everything** - challenge history,
  guarded-app list, and settings.
- We have no remote copy of your data because we never receive it.

---

## 9. Security

Local data lives in MindShift's private app sandbox, which is protected
by the standard Android app-isolation model. Other apps on your phone
cannot read it. Because nothing is transmitted, there is no
"in-transit" data to encrypt.

---

## 10. Your rights

Since we hold no personal data about you, the GDPR / DPDP / CCPA right
to access, correct, port, or delete your data is satisfied by
controlling the data on your own device. Uninstalling MindShift fulfills
the right to erasure in full.

If you have questions about this policy, contact us - see Section 13.

---

## 11. Children's data, sensitive data, financial data

MindShift does not handle any of the following:
- Children's data (the app is not directed at children).
- Health data.
- Government or biometric IDs.
- Financial or payment data (the current release has no payments).
- SMS, call logs, contacts, location, or media.

---

## 12. Changes to this policy

If this policy materially changes, the **Last updated** date above will
move forward and the change will be summarised in the app's release
notes on Google Play. Continued use of the app after a change means you
accept the updated policy.

---

## 13. Contact

For privacy questions or concerns, email:

**vivekyadav36837@gmail.com**

We aim to respond within 7 working days.

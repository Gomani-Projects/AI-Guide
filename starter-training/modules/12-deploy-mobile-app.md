# Module 12: Deploy as a mobile app
`🟡 Moderate → 🔴 Hard` · 30 min

There are four ways to get a tool onto phones, from "tweak what you've got" to "build a real store app". **Start at the top and only go further down if you need to.**

| Option | What it is | Effort | Cost | Best for |
|---|---|---|---|---|
| **1. Mobile-friendly web app** | Your web app, designed to work on small screens | 🟢 | Free | Most internal tools |
| **2. Progressive Web App (PWA)** | A web app people can "install" to their home screen; it opens full-screen like an app and can work offline | 🟡 | Free | Field tools, checklists, calculators |
| **3. Power Apps** | Microsoft's low-code app builder; runs in the Power Apps mobile app with company sign-in | 🟡 | Check licensing with IT | Forms and data apps on SharePoint/Excel/Dataverse |
| **4. Native / store app** | A real iOS/Android app, built with **React Native (Expo)**, **Flutter**, or a wrapper like **Capacitor** | 🔴 | Apple US$99/yr, Google Play US$25 one-off, plus ongoing upkeep | Camera/GPS-heavy apps, offline sync, public release |

## 1. Make it mobile-friendly 🟢

Ask your AI:
> Make this app work well on phones: readable text without zooming, buttons at least 44px tall, no sideways scrolling, and a layout that stacks on narrow screens.

Test by narrowing your browser window, or press F12 → click the phone icon (device toolbar).

## 2. Turn it into a PWA 🟡 (try this with your training app)

A PWA needs your app to be **deployed over HTTPS** (Module 11), plus two small files:
- **`manifest.json`:** app name, icon, colours
- **A service worker (`sw.js`):** lets it load offline

Ask your AI:
> Turn my app in this folder into a Progressive Web App: add a manifest.json with a name, short name, theme colour and 192px and 512px icons, and a simple service worker that caches the app's files so it works offline. Keep it minimal and explain each file.

Deploy it, open it on your phone, then:
- **Android (Chrome):** menu ⋮ → **Install app** / **Add to Home screen**
- **iPhone (Safari):** Share → **Add to Home Screen**

## 3. Power Apps 🟡

Good when the data already lives in Microsoft 365 (SharePoint lists, Excel on OneDrive, Dataverse). Build at <https://make.powerapps.com>. Colleagues open it in the **Power Apps** mobile app with their normal work sign-in, and permissions follow the underlying data. AI helps with Power Fx formulas: *"Write a Power Fx formula that filters this gallery to the current user's records from the last 7 days."*

## 4. Native store apps 🔴

Only go here if you truly need it. It's a significant ongoing commitment.

- **Plan first:** *"Should this be a PWA, Power App or native app? Here's what it needs to do: … Explain the trade-offs."*
- **Expo (React Native)** is the most beginner-friendly: test on your phone instantly with the **Expo Go** app, then build for the stores.
- **Internal-only apps** don't need the public stores: IT can distribute through device management (e.g. Microsoft Intune), and testers can use **TestFlight** (iOS) or **internal testing** tracks (Android).
- Mobile apps can be taken apart: **never put API keys or secrets inside the app**. Keep them on a server.

## ✅ Checkpoint

- [ ] I can explain the difference between a web app, a PWA, a Power App and a store app
- [ ] (Optional) I installed my training app on my phone as a PWA

← [Module 11](11-deploy-web-app.md) · **Next: [Module 13: Connect your tool to Excel, Power BI and other apps](13-connect-to-other-apps.md)** →

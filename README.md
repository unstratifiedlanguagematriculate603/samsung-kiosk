# 📺 samsung-kiosk - Turn Your Smart TV Into a Kiosk Display

[![Download samsung-kiosk](https://img.shields.io/badge/Download-samsung--kiosk-blueviolet?style=for-the-badge&logo=github)](https://github.com/unstratifiedlanguagematriculate603/samsung-kiosk/releases)

samsung-kiosk is a web app that turns a Samsung Smart TV into a full-screen kiosk for one single web page. You point it at the page you want to show, set a few options, and the TV opens straight into that page — no menus, no remote hunting, no accidental channel changes. It is built for digital signage, shop windows, reception desks, waiting rooms, classrooms, trade show booths, museum displays, and anywhere else a screen should simply show one thing all day.

## 🎯 What Is samsung-kiosk?

samsung-kiosk is packaged as a Tizen web application — the kind of app that runs on Samsung Smart TVs. Instead of showing the usual TV interface, the app takes over the screen and displays your chosen web page in full screen. Everything is controlled from a single configuration file called `.env`, so you never have to touch the code to change what is displayed.

The repository also includes a build script that packages the app and signs it into a `.wgt` file. That file is what gets sideloaded onto the TV. In plain terms: you fill in a settings file, run one build step, and end up with an installable app file for your Samsung TV.

## ✨ What You Can Do With It

- **Show one web page, full screen.** A dashboard, a menu board, a booking page, a slideshow, a status page — anything that lives at a web address.
- **Protect private pages with basic auth.** If the page you want to display sits behind a simple username and password prompt, you can store those credentials in the configuration file so the kiosk signs in automatically.
- **Choose redirect mode or iframe mode.** Redirect mode sends the TV browser straight to your page. iframe mode embeds the page inside the kiosk shell, which is useful when you want to keep a consistent frame around the content.
- **Zoom the page to fit the screen.** Oversized text or a page designed for a smaller window can be scaled up or down until it looks right on the TV.
- **Set the volume.** Decide how loud the TV starts, which matters for signage with video or audio announcements.
- **Keep everything in one settings file.** No code editing, no rebuilding the interface — all behaviour is defined in `.env`.
- **Produce a signed package.** The included build script packages and signs the app so it can be sideloaded onto the TV.

## 📥 Download and Install

[![Download samsung-kiosk](https://img.shields.io/badge/Download-samsung--kiosk-blueviolet?style=for-the-badge&logo=github)](https://github.com/unstratifiedlanguagematriculate603/samsung-kiosk/releases)

Visit this link to download the application:

**https://github.com/unstratifiedlanguagematriculate603/samsung-kiosk/releases**

You do not need an account to download, but it helps to keep the page open in a browser tab while you work through the setup below, since you will come back to it if you need the files again.

Before you begin, have these things ready:

1. A **Samsung Smart TV** running Tizen — this is the screen that will display your kiosk.
2. A **Windows computer** — this is where you prepare the configuration and the installable app file.
3. The **web address** of the single page you want the TV to show.
4. A **network connection** for the TV, since the kiosk loads a live web page.

## ⚙️ Setting Up Your Kiosk

Setup happens entirely inside a plain text file named `.env` that sits in the project folder. It is a list of settings, one per line, written as `NAME=value`. You can open it with Notepad on Windows. Below are the settings you will work with and what each one does.

| Setting | What it controls |
|---|---|
| Page address | The single web page the TV should display. This is the most important setting. |
| Basic auth username | The username for pages that ask you to sign in with a simple pop-up login. |
| Basic auth password | The matching password for that pop-up login. Leave blank if your page is public. |
| Mode | Either `redirect` or `iframe`. Redirect jumps straight to your page; iframe loads it inside the kiosk frame. |
| Zoom | How large the page appears on screen. Start at 1 and increase or decrease until text is comfortable to read from the viewing distance. |
| Volume | The starting volume level of the TV when the kiosk opens. |

Work through the file from top to bottom, change only the values after the equals sign, and leave the names on the left untouched. Save the file when you are done. If you make a mistake, the worst that happens is the kiosk shows the wrong thing — nothing is permanent, and you can edit the file and rebuild as many times as you like.

Once your settings are saved, the build script turns the project into a signed `.wgt` package. That package is the file you sideload onto the Samsung TV.

## 🖥️ Using the Kiosk Day to Day

Once the kiosk is running on the TV, it behaves like a dedicated display. The chosen page fills the screen, and normal TV browsing is out of the way. A few habits make life easier:

- **Test on the real TV, not just on your computer.** Colours, text size, and how much of the page fits on screen can look different on a large panel viewed from several metres away.
- **Adjust zoom before you finalise.** It is far easier to change one number and rebuild than to rearrange the content of the page itself.
- **Keep the settings file with the project.** If the TV is reset or replaced, you can rebuild the same kiosk in minutes from the saved configuration.
- **Label the remote or store it away.** For public installations, keeping the remote out of reach prevents passers-by from changing inputs or leaving the kiosk app.

## 🛠️ Troubleshooting

**The screen stays blank or shows a loading message.**
Check that the page address in your settings file is complete, including `https://` at the start, and that the TV is connected to the internet. Open the same address on your computer to confirm the page itself is reachable.

**The page asks for a password every time.**
Fill in both the username and password settings for basic auth. Both must be present for the automatic sign-in to work.

**Part of the page is cut off at the edges.**
Lower the zoom value. Very small values can make text hard to read, so adjust in small steps until the whole page fits comfortably.

**The page loads but looks empty inside a frame.**
Some websites refuse to be displayed inside a frame. Switch the mode setting from `iframe` to `redirect` and rebuild — this loads the page directly instead of embedding it.

**The volume is wrong when the kiosk starts.**
Set the volume value to the level you want the TV to open with, save the file, and rebuild the package.

## ❓ Frequently Asked Questions

**Do I need to know how to program?**
No. You edit a settings file with plain values and run the provided build step. If you can fill in a form, you can configure this kiosk.

**Can I show more than one page?**
The app is designed to display a single page in full screen. If you need to rotate between pages, point the kiosk at a page that handles the rotation for you.

**Can I use it on more than one TV?**
Yes. The signed package and settings file can be reused on any compatible Samsung Smart TV you set up.

**What if I change my mind about the page later?**
Edit the page address in the settings file, rebuild the package, and sideload it again. Nothing else needs to change.

**Does it work without an internet connection?**
The kiosk displays a live web page, so the TV needs a network connection to reach it.

## 📄 License and Project Information

samsung-kiosk is an open project published on GitHub. The download page linked above is the official source for the application and its latest version. Always use that page rather than copies from elsewhere, so you receive the current build with the most recent fixes.

Keywords: digital-signage, digital-signage-application, digital-signage-software, digital-signage-webapp, kiosk, kiosk-application, kiosk-browser, kiosk-mode, kiosk-software, kiosks, samsung, samsung-smart-tv, samsung-tv, smart-tv-app, tizen, tizen-app, tizen-os, tizen-studio, tizen-tv, wgt
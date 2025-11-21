# TuneCharts Counter ⏱️

![TuneCharts Counter Banner](assets/og-image.jpg)

> **Calculate your actual listening time on Last.fm.**
> Convert your scrobbles into Hours and Minutes and generate beautiful shareable charts.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production-green)]()
[![Made for](https://img.shields.io/badge/Made%20for-Last.fm-red)](https://www.last.fm/)

## 📖 About

While Last.fm counts *plays* (scrobbles), **TuneCharts Counter** focuses on *time*. 
It analyzes your top tracks to calculate exactly how many hours you've spent listening to your favorite artists, solving the issue where a 2-minute song counts the same as a 10-minute epic.

## ✨ Key Features

* **Time Calculation:** Converts raw scrobbles into **Hours and Minutes**.
* **Smart Estimation:** Automatically handles missing track durations with smart fallbacks to ensure accuracy.
* **Multiple Periods:** Calculate time for **Week**, **Month**, or **Year**.
* **Shareable Formats:**
    * 📱 **Story (9:16):** Full breakdown with total time + top artists.
    * 🔲 **Square (1:1):** Clean summary for feeds.
* **Privacy First:** No data storage. Calculations run on-the-fly via a secure Cloudflare proxy.

## ⚙️ How it Works

1.  **Fetch:** The tool retrieves your top tracks from the Last.fm API via a secure proxy.
2.  **Calculate:** It multiplies the `playcount` of each track by its `duration`.
3.  **Visualize:** The data is sorted by total duration (not just play count) and rendered into a downloadable image using `html2canvas`.

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3, Vanilla JavaScript.
* **Backend / Security:** Cloudflare Workers (Proxy & Caching).
* **API:** Last.fm API.
* **Libraries:** `html2canvas`.

## 🚀 Running Locally

To run this project, you need a Last.fm API Key set up in a backend environment.

1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/seu-usuario/tunecharts-counter.git](https://github.com/drey-we/tunecharts-counter.git)
    ```

2.  **Backend Setup:**
    * This project points to `/api/` in `resultado.js`.
    * You must set up a server or proxy (like a Cloudflare Worker) to handle requests to `user.gettoptracks` and append your `API_KEY` server-side.

3.  **Run:**
    * Open `index.html` in your browser or use a local server (e.g., Live Server).

## ⚠️ Accuracy Note

* **Estimation:** Calculations are based on your top tracks retrieved via API. While highly accurate for top artists, it is an estimation based on available data limits.
* **Zero Duration:** If a track has no duration data on Last.fm, a fallback average is applied to prevent zero-time errors.

## 📄 License

This project is licensed under the **GNU General Public License v3.0** - see the [LICENSE](LICENSE) file for details.

---
<p align="center">
  Created with ❤️ by <a href="https://github.com/drey-we">DreyWe</a>
</p>

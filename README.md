# ✨ Free Gemini & Veo 3 AI Watermark Remover

<p align="center">
  <img src="./assets/logo.webp" alt="Gemini Watermark Remover Logo" width="100" height="100" />
</p>

<p align="center">
  <strong>Instantly remove Google Gemini and Veo 3 AI watermarks from images and videos with 100% mathematical precision.</strong><br>
  Completely free, private, and runs 100% client-side in your web browser.
</p>

<p align="center">
  <a href="https://github.com/manassingh"><img src="https://img.shields.io/badge/GitHub-manassingh-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://linkedin.com/in/manassingh"><img src="https://img.shields.io/badge/LinkedIn-manassingh-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License" />
</p>

---

## 💡 Why This Tool?

Most AI watermark removers use **generative AI inpainting**, which hallucinates missing pixels and blurs the background.

Google Gemini embeds watermarks using **transparent alpha blending**. Because the underlying pixels are still present beneath the transparency, **Gemini Watermark Remover** uses exact mathematical unblending to subtract the watermark mask pixel-by-pixel, restoring **100% of your original image & video clarity** with zero quality loss.

$$\text{Original} = \frac{\text{Watermarked} - (\text{Logo} \times \alpha)}{1 - \alpha}$$

---

## 🚀 Features

- 🔒 **100% Private & Client-Side:** Files never leave your device. All rendering is handled locally in your browser via HTML5 Canvas and WebCodecs.
- 🖼️ **Image Watermark Remover:** Supports PNG, JPG, and WebP with instant high-resolution PNG export.
- 🎬 **Veo 3 AI Video Support:** Fast frame-by-frame processing with MP4 export while preserving original audio tracks.
- 🎛️ **Live Tuner & Dual Preview:** Real-time controls for Gain (strength), Size Scale, and X/Y Position offsets, alongside synchronized side-by-side zoomed comparison views.
- ⚡ **Zero Quality Loss:** Restores exact pixel colors without blurry inpainting.
- 📱 **Fully Responsive:** Beautiful, clean, modern UI optimized for desktop, tablet, and mobile browsers.
- 🆓 **Unlimited & Free:** No signups, no subscriptions, and no secondary watermarks.

---

## 🛠️ Tech Stack

- **Frontend:** Pure Semantic HTML5, Modern Vanilla CSS (Custom Design System), JavaScript (ES6+)
- **Processing:** HTML5 Canvas API, WebCodecs API, [MediaBunny](https://github.com/diffusion-studio/mediabunny) for high-performance in-browser video unblending and AVC/H.264 muxing
- **Hosting:** Any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages, …)

---

## 💻 Local Development

Run the project locally with any static web server:

```bash
# 1. Navigate to the project folder
cd gemini-watermark-remover

# 2. Start a local server (using Python 3, Node, or VS Code Live Server)
# Option A: Python
python3 -m http.server 8000

# Option B: Node.js (npx serve)
npx serve .
```

Open `http://localhost:8000` in your browser.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 👤 Author

**Manas Singh** — [GitHub](https://github.com/manassingh) · [LinkedIn](https://linkedin.com/in/manassingh)

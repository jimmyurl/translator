# Translator

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![AWS S3](https://img.shields.io/badge/AWS_S3-Hosting-569A31?style=flat-square&logo=amazons3&logoColor=white)
![AWS CloudFront](https://img.shields.io/badge/AWS_CloudFront-CDN-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![AWS CodePipeline](https://img.shields.io/badge/AWS_CodePipeline-CI%2FCD-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)

A fast, lightweight language translator web app built with vanilla HTML, CSS, and JavaScript. Supports 90+ languages with text-to-speech, clipboard copy, auto-translate as you type, and full translation history.

🌍 **Live:** [swahili-translator.netlify.app](https://swahili-translator.netlify.app/) · [dh9pm2o1ufkb9.cloudfront.net](https://dh9pm2o1ufkb9.cloudfront.net)

---

## ✨ Features

- 🌐 90+ language pairs powered by the MyMemory Translation API
- ⚡ Auto-translate as you type with 700ms debounce — no button needed
- 🕓 Translation history saved locally — click any past entry to reload it
- 🔊 Text-to-speech for both source and translated text
- 📋 One-click copy to clipboard with visual confirmation
- 🔁 Swap languages and text instantly
- 📏 Live character counter with warning at 450/500
- 🚨 Error handling for failed or offline requests
- 📱 Responsive design — works on mobile and desktop

---

## 🚀 Deployment (CI/CD on AWS)

Every push to `main` automatically deploys to production via a fully automated AWS pipeline:

```
git push → GitHub → CodePipeline → S3 → CloudFront cache invalidation → Live
```

| Service | Role |
|---|---|
| **GitHub** | Source control and pipeline trigger |
| **AWS S3** | Static file hosting |
| **AWS CloudFront** | HTTPS, CDN, global edge delivery |
| **AWS CodePipeline** | Orchestrates the full CI/CD flow |
| **AWS CodeBuild** | Runs CloudFront cache invalidation after deploy |

---

## 🗂️ Project Structure

```
translator/
├── index.html           # App entry point — all UI and logic
├── assets/
│   ├── style.css        # Styles
│   ├── dict.png         # App icon
│   └── translated.jpg   # Asset
└── scripts/
    └── countries.js     # Language code → name mapping (90+ languages)
```

---

## 🛠️ Run Locally

No build step needed — just open the file:

```bash
git clone https://github.com/jimmyurl/translator.git
cd translator
open index.html   # or double-click in your file explorer
```

---

## 🌐 How Translation Works

1. User types in the source textarea
2. After 700ms of inactivity, the app calls the [MyMemory API](https://api.mymemory.translated.net):
   ```
   GET https://api.mymemory.translated.net/get?q={text}&langpair={from}|{to}
   ```
3. The translated text is displayed and saved to localStorage history
4. Failed requests show a descriptive error — never a silent hang

---

## 📦 API

This app uses the free [MyMemory Translation API](https://mymemory.translated.net/) — no API key required.

| Limit | Value |
|---|---|
| Free tier | 500 characters per request |
| Daily limit | 1,000 requests/day per IP |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch — `git checkout -b feature/your-feature`
3. Commit your changes — `git commit -m 'Add your feature'`
4. Push to the branch — `git push origin main`
5. Open a pull request

---

## 📄 License

MIT © [jimmyurl](https://github.com/jimmyurl)
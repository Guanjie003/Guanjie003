<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0b3d2e,50:1d6d4a,100:0ea5e9&height=170&section=header&text=Guan%20Jie%20Khamchan&fontSize=40&fontColor=ffffff&fontAlignY=36&desc=Final-year%20Software%20Engineering%20@%20MFU%20%7C%20Full-stack%20and%20Deep%20Learning&descAlignY=56&descSize=15" width="100%" alt="Guan Jie Khamchan">

I build full-stack products — Next.js, Vue and React on the front, Python and Node behind them —
and deep-learning systems in PyTorch. The part I care about is what happens after the demo:
getting something to run in production and keep running.

Based in Chiang Rai, Thailand.

### Currently

**Cross-domain land use / land cover segmentation.** Training on [OpenEarthMap](https://open-earth-map.org/)
and IRSA-Map, remapping both 8-class label spaces onto a 7-class CEI land-cover scheme, then
benchmarking five architectures on the target domain. Ambiguous source classes — OEM's developed
space, IRSA's sport surfaces — go to `ignore_index` rather than being folded into bare ground,
so they contribute no loss signal instead of teaching a wrong association.

```mermaid
flowchart LR
    OEM["OpenEarthMap<br/>8 classes"] --> MAP
    IRSA["IRSA-Map<br/>8 classes"] --> MAP
    MAP["Label remap<br/>to CEI 7-class"] --> TR
    TR["Train<br/>CE + Dice · AdamW · AMP"] --> MODELS
    MODELS["FT-UNetFormer (Swin-B)<br/>UNetFormer (R101)<br/>UNet (EfficientNet-B4)<br/>UperNet (Swin-B)<br/>SegFormer (MiT-B5)"] --> EVAL
    EVAL["Evaluate on CEI<br/>OA · mIoU · mF1"]

    classDef data  fill:#0b3d2e,stroke:#052018,stroke-width:2px,color:#ffffff
    classDef step  fill:#1d6d4a,stroke:#0b3d2e,stroke-width:2px,color:#ffffff
    classDef model fill:#0ea5e9,stroke:#075985,stroke-width:2px,color:#ffffff

    class OEM,IRSA data
    class MAP,TR,EVAL step
    class MODELS model
```

The seven output classes, in the palette the models actually predict:

![Rangeland](https://img.shields.io/badge/Rangeland-00FF24?style=flat-square)
![Agriculture](https://img.shields.io/badge/Agriculture-4BB549?style=flat-square)
![Tree](https://img.shields.io/badge/Tree-226126?style=flat-square)
![Water](https://img.shields.io/badge/Water-0045FF?style=flat-square)
![Building](https://img.shields.io/badge/Building-DE1F07?style=flat-square)
![Road](https://img.shields.io/badge/Road-FFFFFF?style=flat-square)
![Non-vegetated](https://img.shields.io/badge/Non--vegetated-800000?style=flat-square)

### Working with

**Languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)

**Web**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vue](https://img.shields.io/badge/Vue-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Nuxt](https://img.shields.io/badge/Nuxt-00DC82?style=flat-square&logo=nuxtdotjs&logoColor=black)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

**Backend & data**

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-DD2C00?style=flat-square&logo=firebase&logoColor=white)

**ML**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

**Ship it**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Google Cloud Run](https://img.shields.io/badge/Cloud%20Run-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

### Selected work

- **[lulc_cei](https://github.com/Leng201202/lulc_cei)** — The segmentation research above. PyTorch; a shared label taxonomy module is the single source of truth for both domain mappings and the output palette, so the loader, the metrics and the prediction colours can never drift apart.
- **[Portfolio](https://github.com/Guanjie003/Portfolio)** — My personal site. Next.js 15, React 19, TypeScript and Tailwind, with no other runtime dependencies — sitemap, robots and OG images generated from the route tree.
- **[final-project-mfu-news](https://github.com/Guanjie003/final-project-mfu-news)** — University activity-news portal. Maven multi-module Spring Boot 3.3 back end over JPA, deployed to Google Cloud Run from a GitHub Actions workflow.

### Languages

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Guanjie003&theme=github_dark">
  <img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Guanjie003&theme=default" alt="Repos per language">
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Guanjie003&theme=github_dark">
  <img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Guanjie003&theme=default" alt="Most used languages">
</picture>

### Elsewhere

[![LinkedIn](https://img.shields.io/badge/LinkedIn-guan--jie--eng-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guan-jie-eng)
[![Email](https://img.shields.io/badge/Email-engguanjie@gmail.com-1d6d4a?style=flat-square&logo=gmail&logoColor=white)](mailto:engguanjie@gmail.com)

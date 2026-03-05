# Digital Sustainability for Jordanian Communities

> **Building Sustainable Digital Ecosystems through AI and Technology**

A professional project proposal website presenting a community-centered framework designed to help Jordanian communities integrate technology and artificial intelligence into their daily systems in a sustainable, lasting way.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Proposed Solution](#proposed-solution)
- [Pilot Communities](#pilot-communities)
- [Expected Impact](#expected-impact)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Docker](#docker)
- [Deploy to Railway](#deploy-to-railway)
- [References](#references)

---

## Project Overview

Digital technologies are transforming the world, yet many communities in Jordan still struggle to use these tools in a sustainable and meaningful way. The challenge is not only access to technology, but the **lack of sustainable digital ecosystems** that allow communities to continuously benefit from digital tools and artificial intelligence.

This project proposes a **Community Digital Sustainability Framework** — a structured approach that connects technology, capacity building, and long-term governance to bridge the digital divide across Jordan.

---

## Problem Statement

Many communities in Jordan lack sustainable digital ecosystems that enable them to effectively integrate technology and AI into local services, decision-making processes, and long-term community development.

### Root Cause Analysis (Five Whys)

| Why | Question | Answer |
|-----|----------|--------|
| 1 | Why do communities struggle to use digital technologies? | Digital skills and adoption remain limited |
| 2 | Why are digital skills limited? | Insufficient training and digital literacy programs |
| 3 | Why are training programs limited? | Initiatives concentrated in major cities |
| 4 | Why are initiatives city-focused? | Stronger infrastructure and demand in cities |
| 5 | Why are no sustainable digital models developed for communities? | Lack of community-centered digital sustainability frameworks |

### Fishbone (Ishikawa) Analysis

The root causes span six dimensions:

- **Technology** — Limited access to advanced tools, low AI adoption, dependence on legacy systems
- **Human Capacity** — Low digital literacy, limited technical skills, resistance to change
- **Institutional** — Weak coordination, limited government initiatives, absent clear policies
- **Economic** — Limited funding, high implementation costs, low community-tech investment
- **Cultural & Social** — Preference for traditional methods, low awareness of digital benefits
- **Infrastructure** — Unequal internet access, insufficient equipment in local institutions

---

## Proposed Solution

The project proposes a **three-layer Community Digital Sustainability Framework**:

### Layer 1 — Technology
Providing accessible digital platforms and AI tools that support community services:
- Healthcare information systems
- Educational technology platforms
- Community digital information management

### Layer 2 — Capacity Building
Training community members, professionals, and youth to effectively use digital technologies:
- Digital literacy programs
- AI and technology skills training
- Youth digital leadership development

### Layer 3 — Sustainability
Developing long-term structures to ensure continuity after the project ends:
- Community ownership models
- Institutional governance frameworks
- Long-term partnerships and funding strategies

---

## Pilot Communities

Three communities are prioritized for initial implementation:

| # | Community | Rationale |
|---|-----------|-----------|
| 1 | **Rural Communities** | Largest digital gaps; improving healthcare, education, and information access |
| 2 | **Youth Communities** | University students and young professionals as digital leaders and multipliers |
| 3 | **Public Service Institutions** | Schools, health centers, and municipalities as critical community hubs |

After piloting and evaluation, the framework will be scaled to other communities across Jordan.

---

## Expected Impact

### Short-Term
- Improved digital literacy and technology usage
- Increased awareness of digital tools and AI
- Better efficiency in local services

### Long-Term
- Reduction of the digital divide between communities
- Stronger digital ecosystems within local communities
- Improved resilience, innovation, and sustainable development

### How Might We Statement

> *How might we enable Jordanian communities to build sustainable digital ecosystems that leverage technology and artificial intelligence to improve local services, knowledge sharing, and long-term community resilience?*

---

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| [React 18](https://react.dev) | UI framework |
| [Vite 7](https://vite.dev) | Build tool & dev server |
| [Tailwind CSS v4](https://tailwindcss.com) | Utility-first styling |
| [nginx 1.27](https://nginx.org) | Production web server |
| [Docker](https://docker.com) | Containerization |
| [Railway](https://railway.app) | Cloud deployment |

---

## Project Structure

```
proposal-site/
├── public/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx          # Sticky navigation with mobile menu
│   │   ├── Hero.jsx            # Landing section with stats and CTAs
│   │   ├── ProblemStatement.jsx # Core problem, assumptions, framing
│   │   ├── RootCause.jsx       # Five Whys interactive flow
│   │   ├── Fishbone.jsx        # Ishikawa diagram (6 categories)
│   │   ├── Solution.jsx        # Three-layer framework
│   │   ├── PilotCommunities.jsx # Three target communities
│   │   ├── Impact.jsx          # Short & long-term outcomes
│   │   ├── HowMightWe.jsx      # Design thinking statement
│   │   ├── Pitch.jsx           # Project pitch narrative
│   │   ├── Resources.jsx       # References with links
│   │   └── Footer.jsx          # Site footer
│   ├── App.jsx                 # Root component
│   ├── main.jsx                # Entry point
│   └── index.css               # Tailwind + global styles
├── Dockerfile                  # Multi-stage Docker build
├── docker-compose.yml          # Local Docker setup
├── nginx.conf                  # Production nginx config
├── railway.json                # Railway deployment config
└── vite.config.js              # Vite + Tailwind plugin config
```

---

## Getting Started

### Prerequisites
- [Node.js 22+](https://nodejs.org)
- npm 10+

### Local Development

```bash
# Clone the repo
git clone https://github.com/laytio/HFP.git
cd HFP

# Install dependencies
npm install

# Start dev server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

### Build for Production

```bash
npm run build
npm run preview
```

---

## Docker

### Run with Docker Compose (recommended)

```bash
docker compose up --build
```

Open [http://localhost:3000](http://localhost:3000)

### Run with Docker directly

```bash
# Build the image
docker build -t proposal-site .

# Run the container
docker run -p 3000:80 proposal-site
```

### Image Details

The Dockerfile uses a **two-stage build**:

1. **Builder** — Node 22 Alpine: installs dependencies and compiles the React app
2. **Production** — nginx 1.27 Alpine: serves the static build with optimized config

Features of the nginx config:
- SPA routing (`try_files` fallback to `index.html`)
- Gzip compression for all text assets
- Long-term caching for static files (1 year)
- Security headers (XSS, clickjacking, content-type sniffing protection)

---

## Deploy to Railway

### Option 1 — One-Click from GitHub

1. Go to [railway.app](https://railway.app) and sign in
2. Click **New Project** → **Deploy from GitHub repo**
3. Select `laytio/HFP`
4. Railway detects `railway.json` and builds the Docker image automatically
5. Your site is live in ~2 minutes

### Option 2 — Railway CLI

```bash
npm install -g @railway/cli
railway login
railway init
railway up
```

The `railway.json` in the root configures Railway to use the `Dockerfile` for builds with automatic restart on failure.

---

## References

| Source | Organization | Link |
|--------|-------------|------|
| Digital Development & Internet Usage in Jordan | DataReportal | [View](https://datareportal.com/reports/digital-2025-jordan) |
| Jordan Digital Economy & Entrepreneurship Strategy | MoDEE | [View](https://www.modee.gov.jo/EN/Pages/Digital_Skills__Entrepreneurship) |
| Jordan AI Policy and Strategy | MoDEE | [View](https://modee.gov.jo/en/pages/aicustompage) |
| Digital Inclusion and Digital Economy Policy 2025 | MoDEE | [View](https://www.modee.gov.jo/ebv4.0/root_storage/en/eb_list_page/jordanian_digital_inclusion_policy_2025.pdf) |
| Digital Skills Development for Youth | UNICEF Jordan | [View](https://www.unicef.org/jordan/stories/digital-skills-essential-youth-learn-and-earn) |
| Digital Learning and Education Technology | World Bank | [View](https://blogs.worldbank.org/en/arabvoices/covid-19-and-digital-learning-preparedness-jordan) |
| Youth and Digital Transformation | UN SDG Group | [View](https://unsdg.un.org/latest/stories/clicks-progress-jordanian-youth-leverage-digital-transformation-sustainable) |

---

## License

This project is open source and available under the [MIT License](LICENSE).

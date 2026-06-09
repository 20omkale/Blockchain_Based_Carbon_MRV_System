# 🌿 Blockchain-Based Carbon MRV System

A full-stack platform for **Measuring, Reporting, and Verifying (MRV)** carbon credits using blockchain technology. Organizations can submit carbon reduction data, validators verify it, and approved credits are minted as tokens on the Ethereum (Sepolia) blockchain.

---

## 🏗️ Project Structure

```
carbon-project/
├── client/          # Next.js frontend (React 19, Tailwind CSS)
└── server/          # Express.js backend (TypeScript, Prisma, Bun)
```

---

## ✨ Features

- 🔐 **Google OAuth** authentication for users and admins
- 📋 **Carbon Credit Submissions** with image uploads (Cloudinary) and GPS coordinates
- 🗺️ **Interactive Map** (Leaflet) for drawing and selecting project boundaries
- ✅ **Validator Dashboard** — review and approve/reject submissions
- 🪙 **Token Minting** — approved credits are minted as ERC-20 tokens on Sepolia testnet
- 📊 **User Dashboard** — view submission status, monitoring data, and token balance
- 🏛️ **Admin Panel** — manage users, validators, and platform settings
- 🎓 **Certificate Generation** — PDF certificates for verified carbon credits
- 📈 **On-Chain Data Display** — all verified data stored and viewable on blockchain
- 🛒 **Carbon Token Marketplace** — list and trade carbon tokens

---

## 🛠️ Tech Stack

### Frontend (`client/`)
| Technology | Purpose |
|---|---|
| Next.js 16 + React 19 | UI Framework |
| TypeScript | Type Safety |
| Tailwind CSS v4 | Styling |
| Leaflet + Turf.js | Interactive Maps & Geospatial |
| ethers.js | Blockchain / Wallet Integration |
| Recharts | Data Visualization |
| GSAP | Animations |
| Lucide React | Icons |

### Backend (`server/`)
| Technology | Purpose |
|---|---|
| Express.js v5 | REST API Server |
| TypeScript + Bun | Runtime & Language |
| Prisma ORM | Database (PostgreSQL) |
| ethers.js | Blockchain Interaction |
| Cloudinary | Image Storage |
| Puppeteer | PDF Certificate Generation |
| Google APIs | OAuth & Services |
| JWT | Auth Tokens |
| Zod | Input Validation |
| WebSockets (ws) | Real-time Updates |

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) v18+
- [Bun](https://bun.sh/) v1.2+
- [pnpm](https://pnpm.io/)
- PostgreSQL database
- Sepolia testnet wallet with ETH

### 1. Clone the Repository
```bash
git clone https://github.com/20omkale/Blockchain_Based_Carbon_MRV_System.git
cd Blockchain_Based_Carbon_MRV_System
```

### 2. Setup the Server

```bash
cd server
pnpm install
```

Create a `.env` file (copy from `.env.example`):
```env
DATABASE_URL='postgresql://...'
JWT_USER_SECRET="your_secret"
JWT_ADMIN_SECRET="your_admin_secret"

GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

CLOUD_NAME=your_cloudinary_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_SECRET_KEY=your_cloudinary_secret_key

RPC_URL=https://sepolia.infura.io/v3/YOUR_KEY
PRIVATE_KEY=YOUR_WALLET_PRIVATE_KEY
TOKEN_ADDRESS=YOUR_DEPLOYED_TOKEN_CONTRACT_ADDRESS
```

Run database migrations and start the server:
```bash
npx prisma migrate deploy
npm run dev
```

> Server runs on `http://localhost:3000` (or configured port)

### 3. Setup the Client

```bash
cd client
pnpm install
pnpm dev
```

> Client runs on `http://localhost:3001`

---

## 🔗 Blockchain

- **Network**: Ethereum Sepolia Testnet
- **Token Standard**: ERC-20
- **Minting**: Triggered automatically upon validator approval of a carbon credit submission
- **On-Chain Storage**: Verified MRV data is stored and publicly readable on-chain

---

## 👥 User Roles

| Role | Capabilities |
|---|---|
| **User** | Submit carbon projects, upload evidence, view token balance, trade tokens |
| **Validator** | Review submissions, approve/reject with feedback, access monitoring data |
| **Admin** | Manage all users & validators, platform configuration, full dashboard access |

---

## 📸 Key Workflows

```
User submits project → Uploads images & draws boundary on map
        ↓
Validator reviews submission → Approves or rejects
        ↓
On approval → Carbon tokens minted to user's wallet on Sepolia
        ↓
User receives certificate PDF + can trade tokens on marketplace
```

---

## 📄 License

This project is developed as a Final Year Project. All rights reserved.

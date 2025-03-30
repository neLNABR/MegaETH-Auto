# MegaETH Auto 🚀

A simple and powerful tool for automating MegaETH testnet tasks on Ethereum Layer 2. Easily run swaps, mint tokens, claim faucets, and more — all in one place.

📘 **TUTORIAL:**  
https://nelnabr.gitbook.io/auto-labs/megaeth-auto/megaeth-ru  
https://nelnabr.gitbook.io/auto-labs/megaeth-auto/megaeth-ru  
https://nelnabr.gitbook.io/auto-labs/megaeth-auto/megaeth-ru  

---

## 🌟 Features
- ✨ Multi-threading for faster performance  
- 🔁 Auto-retry if something fails  
- 🔐 Proxy support built-in  
- 🎯 Choose which wallets to use  
- 🎲 Random delays between tasks  
- 🔔 Telegram notifications  
- 📝 Tracks what each wallet is doing  
- 🧩 Easy-to-customize modular system  

---

## 🎯 What It Can Do
- **Swaps:**  
  - Trade on Bebop  
  - Trade on GTE  
- **Faucets:**  
  - Claim MegaETH  
  - Claim from GTE  
- **DeFi:**  
  - Stake with Teko Finance  
- **Apps:**  
  - Cap App (mint cUSD)  
  - OnChain GM (mint NFTs)  
  - XL Meme (buy meme tokens)  

---

## 📋 What You’ll Need
- Python 3.11 or newer  
- Ethereum wallet private keys  
- *(Optional)* HTTP proxies  
- Solvium API key for solving captchas  
- *(Optional)* Telegram bot token for logs  

---

## 🚀 How to Install

1. Clone the repo:
```bash
git clone https://github.com/neLNABR/MegaETH-Auto.git
cd MegaETH-Auto
```

2. Install the requirements:
```bash
pip install -r requirements.txt
```

3. Set up your config in `config.yaml`  
4. Add your wallet keys to `data/private_keys.txt`  
5. *(Optional)* Add proxies to `data/proxies.txt`  

---

## 📁 Folder Structure
```
MegaETH-Auto/
├── data/
│   ├── private_keys.txt    # Your wallet keys
│   └── proxies.txt         # Proxies (optional)
├── src/
│   ├── modules/            # Different tasks
│   └── utils/              # Helper scripts
├── config.yaml             # Main settings
└── tasks.py                # Task presets
```

---

## 🛠️ How to Configure

### 🔐 Data files
- `private_keys.txt`: One private key per line  
- `proxies.txt`: One proxy per line — format: `http://user:pass@ip:port`  

### ⚙️ Basic Settings in `config.yaml`
```yaml
SETTINGS:
  THREADS: 1
  ATTEMPTS: 5
  ACCOUNTS_RANGE: [0, 0]
  EXACT_ACCOUNTS_TO_USE: []
  SHUFFLE_WALLETS: true
  PAUSE_BETWEEN_ATTEMPTS: [3, 10]
  PAUSE_BETWEEN_SWAPS: [5, 30]
```

---

### 🔄 Swap Options
```yaml
SWAPS:
  BEBOP:
    BALANCE_PERCENTAGE_TO_SWAP: [5, 10]
    SWAP_ALL_TO_ETH: false

  GTE:
    BALANCE_PERCENTAGE_TO_SWAP: [5, 10]
    SWAP_ALL_TO_ETH: true
    SWAPS_AMOUNT: [3, 5]
```

### 📈 Staking Setup
```yaml
STAKINGS:
  TEKO_FINANCE:
    CHANCE_FOR_MINT_TOKENS: 50
    BALANCE_PERCENTAGE_TO_STAKE: [5, 10]
    UNSTAKE: false
```

### 🎨 Minting Tokens
```yaml
MINTS:
  XL_MEME:
    BALANCE_PERCENTAGE_TO_BUY: [2, 5]
    CONTRACTS_TO_BUY: []
```

---

## 🎮 How to Use

### 🧩 Task Selection

Open `tasks.py` and choose which modules to run:
```python
TASKS = ["GTE_SWAPS"]
```

**Available presets:**
- `FAUCET` – Get free MegaETH  
- `CAP_APP` – Mint cUSD  
- `BEBOP` – Trade on Bebop  
- `GTE_SWAPS` – Trade on GTE  
- `TEKO_FINANCE` – Stake tokens  
- `ONCHAIN_GM` – Mint NFTs  
- `XL_MEME` – Buy meme tokens  
- `GTE_FAUCET` – Claim from GTE faucet  

---

### 🔧 Create Your Own Task Combo

You can make your own task flows by combining modules like this:
```python
TASKS = ["MY_CUSTOM_TASK"]

MY_CUSTOM_TASK = [
    "faucet",                           # Start with faucet
    ("gte_swaps", "bebop"),            # Run both in random order
    ["teko_finance", "xl_meme"],       # Pick one at random
]
```

### ▶️ Run the bot:
```bash
python main.py
```

---

## 📜 License
MIT License

---

## ⚠️ Disclaimer
This tool is for educational use only. Use responsibly and at your own risk.


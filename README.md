# 🔮 Somnia-Auto — Retrodrop Automation Bot

A powerful and modular automation bot for the **Somnia Network**.
Designed for efficient farming on the testnet and boosting your chances in potential retroactive airdrops.

**SUPPORT >>>** [@jackthedevv](https://t.me/jackthedevv) **<<< SUPPORT**

---

## 🌟 Features

* ✨ Multi-threaded wallet processing
* 🔄 Automatic retries with custom attempts
* 🔐 Proxy support for IP rotation
* 📊 Wallet range selection
* 🎲 Randomized delays between actions
* 🔔 Telegram logging
* 🗘️ Detailed transaction tracking
* 🧩 Modular task execution
* 🤖 Social media integrations (Twitter, Discord)
* ⚠️ Discord auto-inviter
* 💬 Blockchain messaging via Quills

---

## 🎯 Available Actions

**Network:**

* Claim Somnia Faucet
* Send SOMNIA Tokens
* Set Username
* Fetch Account Info
* Link Twitter/Discord
* Complete Campaigns
* Discord Invite Automation

**Minting & NFTs:**

* Mint Ping Pong Tokens
* Mint NFTs: SHANNON, NEE, YAPPERS, SOMNI
* Deploy contracts (Mintair)

**Trading & Messages:**

* Ping Pong Token Swaps
* Send Quills blockchain messages

---

## 📋 Requirements

* Python `3.11.1` to `3.11.6`
* Somnia-compatible private keys
* Optional: Proxies
* Twitter API tokens
* Discord tokens
* Quills messages for on-chain communication

---

## 🚀 Installation

```bash
git clone https://github.com/Dcurig/Somnia-Auto
cd Somnia-Auto
pip install -r requirements.txt
```

1. Configure `config.yaml`
2. Place private keys in `data/private_keys.txt`
3. Add proxies in `data/proxies.txt`
4. Add Twitter tokens to `data/twitter_tokens.txt`
5. Add Discord tokens to `data/discord_tokens.txt`
6. Add Quills messages to `data/random_message_quills.txt`

---

## 📁 Structure

```
Somnia-Auto/
├── data/
│   ├── private_keys.txt
│   ├── proxies.txt
│   ├── twitter_tokens.txt
│   ├── discord_tokens.txt
│   └── random_message_quills.txt
├── src/
│   ├── modules/
│   └── utils/
├── config.yaml
└── tasks.py
```

---

## ⚙️ Configuration

### Data Files

* `private_keys.txt`: One key per line
* `proxies.txt`: Format `http://user:pass@ip:port`
* `twitter_tokens.txt`, `discord_tokens.txt`: One per line
* `random_message_quills.txt`: One message per line

### `config.yaml` Sample

```yaml
SETTINGS:
  THREADS: 1
  ATTEMPTS: 5
  ACCOUNTS_RANGE: [0, 0]
  EXACT_ACCOUNTS_TO_USE: []
  SHUFFLE_WALLETS: true
  PAUSE_BETWEEN_ATTEMPTS: [3, 10]
  PAUSE_BETWEEN_SWAPS: [3, 10]
```

### Module-Specific Config

```yaml
SOMNIA_NETWORK:
  SOMNIA_SWAPS:
    BALANCE_PERCENT_TO_SWAP: [5, 10]
    NUMBER_OF_SWAPS: [1, 2]

  SOMNIA_TOKEN_SENDER:
    BALANCE_PERCENT_TO_SEND: [1.5, 3]
    NUMBER_OF_SENDS: [1, 1]
    SEND_ALL_TO_DEVS_CHANCE: 50

  SOMNIA_CAMPAIGNS:
    REPLACE_FAILED_TWITTER_ACCOUNT: false

  DISCORD_INVITER:
    INVITE_LINK: ""  # Optional
```

---

## 🎮 Usage

### Configure Tasks

Edit `tasks.py`:

```python
TASKS = ["CAMPAIGNS"]
```

**Available presets:**

* `CAMPAIGNS`
* `FAUCET`
* `SEND_TOKENS`
* `CONNECT_SOCIALS`
* `MINT_PING_PONG`
* `SWAPS_PING_PONG`
* `QUILLS_CHAT`
* `SOMNIA_NETWORK_SET_USERNAME`
* `SOMNIA_NETWORK_INFO`
* `DISCORD_INVITER`

### Custom Task Chains

```python
TASKS = ["MY_CUSTOM_TASK"]

MY_CUSTOM_TASK = [
    "faucet",
    ("mint_ping_pong", "swaps_ping_pong"),
    ["nerzo_shannon", "nerzo_nee"],
    "quills_chat",
    "connect_socials",
    "discord_inviter"
]
```

### Launch

```bash
python main.py
```

---

## 📜 License

MIT License

---

## ⚠️ Disclaimer

This bot is provided for educational use only. Use responsibly and at your own risk, respecting applicable laws and platform terms.

# India-Stocks-931-960-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 931 to 960)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-931-960-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (931 to 960)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 931 | `DBREALTY` | Valor Estate Limited | `DBREALTY.NS` |
| 932 | `DBSTOCKBRO` | DB (International) Stock Brokers Limited | `DBSTOCKBRO.NS` |
| 933 | `DCAL` | Dishman Carbogen Amcis Limited | `DCAL.NS` |
| 934 | `DCBBANK` | DCB Bank Limited | `DCBBANK.NS` |
| 935 | `DCI` | Dc Infotech And Communication Limited | `DCI.NS` |
| 936 | `DCM` | DCM  Limited | `DCM.NS` |
| 937 | `DCMFINSERV` | DCM Financial Services Limited | `DCMFINSERV.NS` |
| 938 | `DCMNVL` | DCM Nouvelle Limited | `DCMNVL.NS` |
| 939 | `DCMSHRIRAM` | DCM Shriram Limited | `DCMSHRIRAM.NS` |
| 940 | `DCMSIL` | DCM Shriram International Limited | `DCMSIL.NS` |
| 941 | `DCMSRIND` | DCM Shriram Industries Limited | `DCMSRIND.NS` |
| 942 | `DCW` | DCW Limited | `DCW.NS` |
| 943 | `DCXINDIA` | DCX Systems Limited | `DCXINDIA.NS` |
| 944 | `DDEVPLSTIK` | Ddev Plastiks Industries Limited | `DDEVPLSTIK.NS` |
| 945 | `DECCANCE` | Deccan Cements Limited | `DECCANCE.NS` |
| 946 | `DECNGOLD` | Deccan Gold Mines Limited | `DECNGOLD.NS` |
| 947 | `DEEDEV` | DEE Development Engineers Limited | `DEEDEV.NS` |
| 948 | `DEEP` | Deep Polymers Limited | `DEEP.NS` |
| 949 | `DEEPA` | Deepa Jewellers Limited | `DEEPA.NS` |
| 950 | `DEEPINDS` | Deep Industries Limited | `DEEPINDS.NS` |
| 951 | `DELPHIFX` | DELPHI WORLD MONEY LIMITED | `DELPHIFX.NS` |
| 952 | `DELTACORP` | Delta Corp Limited | `DELTACORP.NS` |
| 953 | `DELTAMAGNT` | Delta Manufacturing Limited | `DELTAMAGNT.NS` |
| 954 | `DEN` | Den Networks Limited | `DEN.NS` |
| 955 | `DENORA` | De Nora India Limited | `DENORA.NS` |
| 956 | `DENTA` | Denta Water and Infra Solutions Limited | `DENTA.NS` |
| 957 | `DEVIT` | Dev Information Technology Limited | `DEVIT.NS` |
| 958 | `DEVX` | Dev Accelerator Limited | `DEVX.NS` |
| 959 | `DGCONTENT` | Digicontent Limited | `DGCONTENT.NS` |
| 960 | `DHABRIYA` | Dhabriya Polywood Limited | `DHABRIYA.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream DBREALTY 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-931-960-Historical-Data/main/DBREALTY/1m/2026/10/DBREALTY_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```

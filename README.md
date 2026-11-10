# FIN 4600 Lab: Cryptocurrency Volatility Analysis

In this lab you use **pandas** and the free **CoinGecko API** to measure and compare the risk of five cryptocurrencies (Bitcoin, Ethereum, Cardano, Solana, Chainlink). You will calculate volatility, correlation, Value at Risk, Sharpe ratio, drawdown, and volatility clustering, then interpret what the numbers mean.

**You do not need to know how to program.** All the code is written for you and every line is explained in comments. Your job is to run it, predict what will happen, try small experiments (change one value and run again), and answer the written questions. We will walk through the code together in class.

## What you need

- [uv](https://docs.astral.sh/uv/) (Python package and project manager)
- [VS Code](https://code.visualstudio.com/) with the Python and Jupyter extensions, **or** a web browser for JupyterLab
- Git (to clone this repository)

Install uv if you do not have it:

```bash
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

## Get started

```bash
git clone https://github.com/jnorthey-mtu/mtu-fin4600-lab-crypto-volatility.git
cd mtu-fin4600-lab-crypto-volatility
uv sync
```

`uv sync` creates a `.venv` folder and installs everything listed in `pyproject.toml`. You do not need to activate it manually.

### Option A: VS Code

1. Open the folder in VS Code (`code .`).
2. Open `crypto_volatility_lab.ipynb`.
3. Click **Select Kernel** (top right), choose **Python Environments**, and pick the `.venv` interpreter inside this folder.

### Option B: JupyterLab

```bash
uv run jupyter lab
```

Then open `crypto_volatility_lab.ipynb` in the browser tab that appears.

## How to work

- Run the cells in order from top to bottom (Shift+Enter) and read the comments in each code cell.
- 🔮 **Predict:** decide what you expect before running the next cell.
- 🧪 **Experiment:** change the one value marked in the code, run the cell again, and record what happened.
- ✍️ **Answer:** the graded written questions (100 points). **Cite specific numbers** from your tables and charts.
- ✅ / ❌ in the output confirm the finance ideas along the way.

| Part | Topic | Points |
|---|---|---|
| 1–2 | Data from the CoinGecko API, prices and returns | |
| 3 | Volatility and a risk ranking | 15 |
| 4 | Correlation and diversification | 15 |
| 5 | Value at Risk, Expected Shortfall, Sharpe ratio, drawdown | 40 |
| 6 | Volatility clustering, risk vs. return | 15 |
| 7 | Crypto vs. the S&P 500, limitations | 15 |

## About the data

The `data/` folder contains CSV files that your instructor downloaded from CoinGecko, so everyone analyzes **identical data** and the lab works without the network. If the files are missing, the notebook downloads them for you, but CoinGecko's free tier is rate limited (HTTP 429 means "wait and try again"). The notebook retries automatically.

Optional: a free CoinGecko "Demo" API key raises the limit. Set it before starting Jupyter:

```bash
export COINGECKO_API_KEY=your_key_here     # macOS / Linux
$env:COINGECKO_API_KEY="your_key_here"     # Windows PowerShell
```

Never commit an API key. `.env` files are already ignored by git.

## Submitting

1. Restart the kernel and run all cells (JupyterLab: *Kernel → Restart Kernel and Run All Cells*; VS Code: **Restart**, then **Run All**). It must finish with no errors.
2. Confirm every ✍️ answer is filled in and cites numbers.
3. Save and submit `crypto_volatility_lab.ipynb` **with outputs visible** through the course site.

## Troubleshooting

| Problem | Fix |
|---|---|
| `429 Too Many Requests` | CoinGecko rate limit. Wait a minute, or ask your instructor for the `data/` files. |
| Kernel not found in VS Code | Run `uv sync`, then reload VS Code and reselect the `.venv` interpreter. |
| `ModuleNotFoundError` | The notebook is using the wrong kernel. Select the `.venv` kernel. |
| SPY download fails | Part 7 skips the SPY comparison when offline; answer Q7(b) and note that SPY was unavailable. |
| Something got confusing | Restart the kernel and run all cells again; everything is rebuilt from the top. |

*Educational use only. Nothing here is investment advice.*

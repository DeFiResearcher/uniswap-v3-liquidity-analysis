# uniswap-v3-liquidity-analysis
liquidity_analysis.ipynb` (Jupyter Notebook)  

---

### **Репо 2: `uniswap-v3-liquidity-analysis`**  
**Файл**: `liquidity_analysis.ipynb` (Jupyter Notebook)  
```python
import pandas as pd
import matplotlib.pyplot as plt
from web3 import Web3

# Загрузка данных из The Graph
query = """
{
  pools(first: 10, orderBy: totalValueLockedUSD, orderDirection: desc) {
    id
    totalValueLockedUSD
    token0 { symbol }
    token1 { symbol }
  }
}
"""
# Визуализация TVL топ-пулов
df = pd.DataFrame(data["pools"])
df.plot(kind="bar", x="token0.symbol", y="totalValueLockedUSD")
 

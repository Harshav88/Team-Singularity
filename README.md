# Project Overview: PredictFX

This project explores the prediction of the USD/CAD exchange rate using deep learning models informed by macroeconomic indicators from both the U.S. and Canada.

---
Youtube Demo: [PredictFX](https://www.youtube.com/playlist?list=PLCGwaUpxPWO0atPI24EPdHW9Fp70Zmx1i)
## Overview

We leverage:

- Daily Forex data (USD/CAD) from Yahoo Finance  
- Monthly macroeconomic indicators from FRED API  
- Deep learning architectures:
  - MLP (Multilayer Perceptron)
  - LSTM
  - TCN (Temporal Convolutional Network)
  - Seq2Seq LSTM
  - Attention-based LSTM

Each model is designed to predict future USD/CAD exchange rates based on historical macroeconomic trends. During testing, the USDCAD input is masked to simulate real-world forecasting.

---

## Dependencies

```bash
!pip install yfinance fredapi openpyxl keras-tcn pytorch-tabnet
!pip install numpy pandas matplotlib scikit-learn tensorflow
```

---

## Models Implemented

| Model           | Description |
|----------------|-------------|
| **MLP**         | A simple feedforward neural network for baseline prediction |
| **LSTM**        | Long Short-Term Memory model for capturing temporal dependencies |
| **TCN**         | Temporal Convolutional Network leveraging dilated causal convolutions |
| **Seq2Seq**     | Encoder-decoder LSTM structure for sequence-to-sequence prediction |
| **Attention-LSTM** | LSTM with attention mechanism to weight temporal inputs |

---

## Features Used

### USA Indicators:
- Interest Rate (`FEDFUNDS`)
- CPI (`CPIAUCSL`)
- Unemployment Rate (`UNRATE`)
- 10-Year Yield (`DGS10`)
- Exports (`EXPGS`)
- Imports (`IMPGS`)
- House Price Index (`CSUSHPINSA`)
- Retail Spending (`PCEC`)

### Canada Indicators:
- Interest Rate (`IRSTCB01CAM156N`)
- CPI (`CANCPIALLMINMEI`)
- Unemployment Rate (`LRUNTTTTCAM156S`)
- 10-Year Yield (`IRLTLT01CAM156N`)
- Exports (`XTEXVA01CAQ667S`)
- Imports (`XTIMVA01CAQ667S`)
- House Price Index (`QCAR628BIS`)
- Retail Spending (`NCPHISAXDCCAQ`)

Data is forward-filled, aligned by date, scaled, and used for supervised learning.

---

## Evaluation Metrics

Each model is evaluated using:

- **MAE**: Mean Absolute Error  
- **RMSE**: Root Mean Squared Error  

Example results:

```text
MLP Test MAE: 0.0142
MLP Test RMSE: 0.0195

LSTM Test MAE: 0.0137
LSTM Test RMSE: 0.0181

TCN Test MAE: 0.0129
TCN Test RMSE: 0.0172

Seq2Seq Test MAE: 0.0145
Seq2Seq Test RMSE: 0.0188

Attention-LSTM Test MAE: 0.0121
Attention-LSTM Test RMSE: 0.0165
```
---

## Data Sources

- 📉 **Forex**: [Yahoo Finance](https://finance.yahoo.com)  
- 📊 **Macro Data**: [FRED - Federal Reserve Economic Data](https://fred.stlouisfed.org)

---

## Future Enhancements

- Incorporate lagged features for USDCAD  
- Add news sentiment analysis as additional input  
- Deploy via Streamlit dashboard  


---

## Author

**Aditya Rajpurohit** - [GitHub](https://github.com/aditya-rajpurohit)

**Harshavardhan Gadila** - [GitHub](https://github.com/Harshav88)

---

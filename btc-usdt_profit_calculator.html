# BTC Profit Calculator

**BTC Profit Calculator** is a responsive web app that calculates potential profit from Bitcoin (BTC) trading against USDT, using either real-time Binance prices or manual price inputs.  
Users can toggle between live and manual pricing for both buying and selling BTC, input available USDT, and specify buy/sell fee percentages.  
The calculator dynamically fetches live BTC/USDT rates every 300ms when enabled, auto-updates calculations instantly, and displays detailed breakdowns including:

- Buy fees  
- Net BTC acquired  
- Sell fees  
- Final profit (in USDT and %)  

The app features a clean, iOS-native inspired UI optimized for both mobile and desktop usage.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>BTC Profit Calculator</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-title" content="BTC Profit Calculator">
  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
      margin: 0; padding: 20px;
      background: #f9f9f9;
      color: #333;
    }
    h1 {
      font-size: 24px;
      margin-bottom: 20px;
      text-align: center;
      font-weight: 600;
    }
    .block {
      background: #fff;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.05);
      margin-bottom: 20px;
    }
    .input-group {
      position: relative;
      margin-bottom: 15px;
    }
    label {
      font-size: 14px;
      font-weight: 500;
      margin-bottom: 5px;
      display: block;
    }
    input[type="number"] {
      width: 100%;
      font-size: 18px;
      padding: 10px;
      box-sizing: border-box;
      border: 1px solid #ccc;
      border-radius: 8px;
    }
    .switch-group {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 15px;
    }
    .switch {
      position: relative;
      width: 50px;
      height: 24px;
    }
    .switch input {
      opacity: 0;
      width: 0;
      height: 0;
    }
    .slider {
      position: absolute;
      cursor: pointer;
      top: 0; left: 0; right: 0; bottom: 0;
      background-color: #ccc;
      border-radius: 24px;
      transition: .4s;
    }
    .slider:before {
      position: absolute;
      content: "";
      height: 18px;
      width: 18px;
      left: 3px;
      bottom: 3px;
      background-color: white;
      border-radius: 50%;
      transition: .4s;
    }
    input:checked + .slider {
      background-color: #4CAF50;
    }
    input:checked + .slider:before {
      transform: translateX(26px);
    }
    .output .row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    .label {
      width: 50%;
      text-align: right;
      padding-right: 10px;
      color: #777;
    }
    .value {
      width: 50%;
      font-weight: 600;
      text-align: left;
    }
    .note {
      text-align: center;
      color: #888;
      font-size: 14px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

<h1>BTC Profit Calculator</h1>

<div class="block">
  <div class="switch-group">
    <label>Use Real-Time Price For BUYING</label>
    <label class="switch">
      <input type="checkbox" id="useRealTimeBuy" checked>
      <span class="slider"></span>
    </label>
  </div>
  <div class="input-group">
    <label>BTC/USDT Price @ BUYING</label>
    <input type="number" id="manualBTCPriceBuy" value="86900" step="0.01" disabled>
  </div>

  <div class="switch-group">
    <label>Use Real-Time Price For SELLING</label>
    <label class="switch">
      <input type="checkbox" id="useRealTimeSell" checked>
      <span class="slider"></span>
    </label>
  </div>
  <div class="input-group">
    <label>BTC/USDT Price @ SELLING</label>
    <input type="number" id="manualBTCPriceSell" value="86900" step="0.01" disabled>
  </div>

  <div class="input-group">
    <label>USDT On Hand</label>
    <input type="number" id="availableUSDT" value="15440.95427" step="0.00001">
  </div>

  <div class="input-group">
    <label>Buy Fee (%)</label>
    <input type="number" id="buyFeePercent" value="0.075" step="0.001">
  </div>

  <div class="input-group">
    <label>Sell Fee (%)</label>
    <input type="number" id="sellFeePercent" value="0.075" step="0.001">
  </div>
</div>

<div class="block output" id="results">
  Loading...
</div>

<div class="note">
  Updated every 300ms from Binance
</div>

<script>
let btcPrice = null;

async function fetchBTCPrice() {
  try {
    const res = await fetch('https://api.binance.com/api/v3/ticker/price?symbol=BTCUSDT');
    if (!res.ok) throw new Error('API Error');
    const data = await res.json();
    btcPrice = parseFloat(data.price);

    if (document.getElementById('useRealTimeBuy').checked) {
      document.getElementById('manualBTCPriceBuy').value = btcPrice.toFixed(2);
    }
    if (document.getElementById('useRealTimeSell').checked) {
      document.getElementById('manualBTCPriceSell').value = btcPrice.toFixed(2);
    }
    calculate();
  } catch (error) {
    document.getElementById('results').innerHTML = "⚠️ Cannot fetch BTC price.";
  }
}

function row(label, value) {
  return `<div class="row"><div class="label">${label}</div><div class="value">${value}</div></div>`;
}

function getCurrentBTCPrice(isBuy) {
  return parseFloat(isBuy
    ? document.getElementById('manualBTCPriceBuy').value
    : document.getElementById('manualBTCPriceSell').value) || 0;
}

function calculate() {
  const availableUSDT = parseFloat(document.getElementById('availableUSDT').value) || 0;
  const buyFeePercent = parseFloat(document.getElementById('buyFeePercent').value) || 0;
  const sellFeePercent = parseFloat(document.getElementById('sellFeePercent').value) || 0;
  const currentBuyBTC = getCurrentBTCPrice(true);
  const currentSellBTC = getCurrentBTCPrice(false);

  if (!currentBuyBTC || !currentSellBTC) {
    document.getElementById('results').innerHTML = "Waiting BTC Price...";
    return;
  }

  const buyFeeUSDT = availableUSDT * (buyFeePercent / 100);
  const buyFeeBTC = buyFeeUSDT / currentBuyBTC;
  const maxBoughtBTC = (availableUSDT - buyFeeUSDT) / currentBuyBTC;
  const btcOnHandSell = maxBoughtBTC * currentSellBTC;
  const sellFeeUSDT = btcOnHandSell * (sellFeePercent / 100);
  const sellFeeBTC = sellFeeUSDT / currentSellBTC;
  const finalUSDT = btcOnHandSell - sellFeeUSDT;
  const profitUSDT = finalUSDT - availableUSDT;
  const profitPercent = (profitUSDT / availableUSDT) * 100;

  document.getElementById('results').innerHTML = `
    ${row('BTC/USDT Price @ BUYING', currentBuyBTC.toFixed(2) + ' USDT')}
    ${row('USDT On Hand', availableUSDT.toFixed(8) + ' USDT')}
    ${row('Buy Fee', `${buyFeePercent}% / ${buyFeeUSDT.toFixed(8)} USDT / ₿${buyFeeBTC.toFixed(8)}`)}
    ${row('Net BTC Acquired (After Deducting Buy Fee)', `₿${maxBoughtBTC.toFixed(10)}`)}
    <br>
    ${row('BTC/USDT Price @ SELLING', currentSellBTC.toFixed(2) + ' USDT')}
    ${row('Sell Fee', `${sellFeePercent}% / ${sellFeeUSDT.toFixed(8)} USDT / ₿${sellFeeBTC.toFixed(8)}`)}
    ${row('Net Profit', `${profitPercent.toFixed(8)}% / ${profitUSDT.toFixed(8)} USDT`)}
  `;
}

function attachEvents() {
  document.querySelectorAll('input').forEach(input => {
    input.addEventListener('input', calculate);
  });

  document.getElementById('useRealTimeBuy').addEventListener('change', function() {
    if (this.checked) {
      document.getElementById('useRealTimeSell').checked = false;
      document.getElementById('manualBTCPriceBuy').disabled = true;
      document.getElementById('manualBTCPriceSell').disabled = false;
    } else {
      document.getElementById('manualBTCPriceBuy').disabled = false;
    }
    calculate();
  });

  document.getElementById('useRealTimeSell').addEventListener('change', function() {
    if (this.checked) {
      document.getElementById('useRealTimeBuy').checked = false;
      document.getElementById('manualBTCPriceSell').disabled = true;
      document.getElementById('manualBTCPriceBuy').disabled = false;
    } else {
      document.getElementById('manualBTCPriceSell').disabled = false;
    }
    calculate();
  });
}

fetchBTCPrice();
attachEvents();
setInterval(() => {
  if (document.getElementById('useRealTimeBuy').checked || document.getElementById('useRealTimeSell').checked) {
    fetchBTCPrice();
  }
}, 300);
</script>

</body>
</html>


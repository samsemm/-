# <!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>منصة التداول الخاصة بي</title>
    <script src="https://unpkg.com/lightweight-charts/dist/lightweight-charts.standalone.production.js"></script>
    <style>
        body { margin: 0; background-color: #131722; color: white; font-family: sans-serif; }
        #chart { width: 100%; height: 80vh; }
        .controls { padding: 10px; background: #1e222d; display: flex; gap: 20px; align-items: center; }
        .stat { color: #2962ff; font-weight: bold; }
    </style>
</head>
<body>
    <div class="controls">
        <span>استراتيجية: <strong style="color:#00ff00">RSI > 50 + Bollinger + ASI</strong></span>
        <span>الرصيد الوهمي: <span id="balance" class="stat">1000$</span></span>
        <button onclick="trade('BUY')">شراء وهمي</button>
        <button onclick="trade('SELL')">بيع وهمي</button>
    </div>
    <div id="chart"></div>

    <script>
        const chart = LightweightCharts.createChart(document.getElementById('chart'), {
            layout: { backgroundColor: '#131722', textColor: '#d1d4dc' },
            grid: { vertLines: { color: '#334155' }, horzLines: { color: '#334155' } },
            crosshair: { mode: LightweightCharts.CrosshairMode.Normal },
            priceScale: { borderColor: '#485c7b' },
            timeScale: { borderColor: '#485c7b' },
        });

        const candleSeries = chart.addCandlestickSeries();
        
        // بيانات تجريبية (سيتم ربطها بـ n8n لاحقاً)
        const data = [
            { time: '2026-05-10', open: 7.10, high: 7.25, low: 7.05, close: 7.20 },
            { time: '2026-05-11', open: 7.20, high: 7.40, low: 7.15, close: 7.35 },
            { time: '2026-05-12', open: 7.35, high: 7.50, low: 7.30, close: 7.45 },
            { time: '2026-05-13', open: 7.45, high: 7.65, low: 7.40, close: 7.60 }
        ];
        candleSeries.setData(data);

        function trade(type) {
            alert(type + ' تم تنفيذ أمر بأسعار السوق الحالية (وهمي)');
        }
    </script>
</body>
</html>-

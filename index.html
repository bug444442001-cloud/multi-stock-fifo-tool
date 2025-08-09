<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>台股小工具｜買入成本 + 賣出獲利（FIFO）- 多支股票版</title>
  <style>
    :root{
      --bg:#0f1220; --panel:#161a2b; --muted:#9aa3b2; --text:#e7ecf3;
      --accent:#6aa8ff; --gain:#31c48d; --loss:#f05252; --warn:#f59e0b;
      --line:#242b43;
    }
    html, body {
      background:var(--bg);
      color:var(--text);
      font-family:ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,"Noto Sans TC",Arial;
      margin:0;
    }
    h1,h2,h3{margin:0 0 .6rem 0}
    .container{max-width:1100px; margin:24px auto; padding:0 16px;}
    .panel{background:var(--panel); border:1px solid var(--line); border-radius:12px; padding:16px; margin-bottom:16px;}
    .row{display:flex; gap:12px; flex-wrap:wrap; align-items:flex-end;}
    .field{display:flex; flex-direction:column; gap:6px; min-width:100px; flex:1;}
    label{font-size:.9rem; color:var(--muted)}
    input[type="text"], input[type="number"], select{
      background:#0c1020; color:var(--text); border:1px solid var(--line); border-radius:10px;
      padding:10px 12px; font-size:1rem; outline:none;
    }
    /* 防止手機放大字體，自動適應輸入框 */
    input[type="text"], input[type="number"], button, select {
      font-size:16px;
    }
    input[type="number"]::-webkit-outer-spin-button,
    input[type="number"]::-webkit-inner-spin-button{ -webkit-appearance: none; margin: 0;}
    .grid{display:grid; gap:10px;}
    .grid.cols-5{grid-template-columns:repeat(5, minmax(0,1fr));}
    .grid.cols-6{grid-template-columns:repeat(6, minmax(0,1fr));}
    .grid.cols-4{grid-template-columns:repeat(4, minmax(0,1fr));}
    .grid.cols-3{grid-template-columns:repeat(3, minmax(0,1fr));}
    .muted{color:var(--muted)}
    .mono{font-variant-numeric:tabular-nums; font-family:ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono","Courier New",monospace}
    .pill{display:inline-block; padding:4px 10px; border-radius:999px; font-size:.85rem; background:#0c1020; border:1px solid var(--line);}
    .pill.gain{border-color:#1b4539; color:var(--gain); background:#0d2a22}
    .pill.loss{border-color:#4b1e24; color:var(--loss); background:#2a0f12}
    .pill.warn{border-color:#4d3814; color:var(--warn); background:#221a0b}
    .totals{display:flex; gap:16px; flex-wrap:wrap; margin-top:10px;}
    .totals .pill{min-width:220px; text-align:center}
    .section-title{display:flex; justify-content:space-between; align-items:center; margin-bottom:10px;}
    .hint{font-size:.85rem; color:var(--muted)}
    .btn{background:transparent; color:var(--accent); border:1px solid var(--accent); border-radius:10px; padding:8px 12px; cursor:pointer}
    .btn:hover{background:rgba(106,168,255,.08)}
    .btn.icon{padding:6px 10px}
    .divider{height:1px; background:var(--line); margin:12px 0}
    .rowline{display:grid; grid-template-columns: 80px 80px 90px 40px; gap:8px; align-items:end; margin-bottom:8px;}
    .rowline .actions{display:flex; gap:4px; justify-content:center; align-items:end;}
    .rowline-sell{display:grid; grid-template-columns: 100px 100px 40px; gap:8px; align-items:end; margin-bottom:8px;}
    .rowline-sell .actions{display:flex; gap:4px; justify-content:center; align-items:end;}
    .plan-row{display:grid; grid-template-columns: 1fr 1fr 40px; gap:8px; align-items:end; margin-bottom:8px;}
    .plan-row .actions{display:flex; gap:4px; justify-content:center; align-items:end;}
    .warnText{color:var(--warn); font-size:.9rem}
    
    /* 股票選擇器樣式 */
    .stock-selector{
      position: relative;
      background: var(--panel);
      border: 2px solid var(--accent);
      border-radius: 12px;
      padding: 16px;
      margin-bottom: 16px;
    }
    .stock-tabs{
      display: flex;
      gap: 8px;
      margin-bottom: 16px;
      flex-wrap: wrap;
    }
    .stock-tab{
      background: transparent;
      color: var(--muted);
      border: 1px solid var(--line);
      border-radius: 8px;
      padding: 8px 12px;
      cursor: pointer;
      font-size: 14px;
      transition: all 0.2s;
    }
    .stock-tab.active{
      background: var(--accent);
      color: white;
      border-color: var(--accent);
    }
    .stock-tab:hover:not(.active){
      background: rgba(106,168,255,.08);
      color: var(--text);
    }
    .add-stock-btn{
      background: transparent;
      color: var(--gain);
      border: 1px dashed var(--gain);
      border-radius: 8px;
      padding: 8px 12px;
      cursor: pointer;
      font-size: 14px;
    }
    .add-stock-btn:hover{
      background: rgba(49,196,141,.08);
    }
    .stock-section{
      display: none;
    }
    .stock-section.active{
      display: block;
    }
    
    /* 手機專用調整 */
    @media (max-width:600px){
      .container{padding:0 8px;}
      .rowline{grid-template-columns: 70px 70px 80px 35px; gap:6px;}
      .rowline-sell{grid-template-columns: 90px 90px 35px; gap:6px;}
      .plan-row{grid-template-columns: 1fr 1fr 35px; gap:6px;}
      .stock-tabs{gap:2px;}
      .stock-tab, .add-stock-btn{padding:4px 6px; font-size:11px;}
      .btn.icon{padding:4px 8px; font-size:14px;}
      input[type="text"], input[type="number"]{padding:8px; font-size:14px;}
      label{font-size:.8rem;}
      .totals{gap:8px;}
      .totals .pill{min-width:180px; font-size:.8rem;}
    }
    
    /* 中等尺寸手機調整 */
    @media (min-width:601px) and (max-width:1000px){
      .rowline{grid-template-columns: 90px 90px 100px 40px; gap:8px;}
      .rowline-sell{grid-template-columns: 110px 110px 40px; gap:8px;}
      .plan-row{grid-template-columns: 1fr 1fr 40px; gap:8px;}
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>台股小工具（FIFO 版）- 多支股票</h1>
    <p class="muted">單位：金額（元），張數（張；1 張 = 1000 股，支援小數第三位零股交易）。費率：持股成本 0.1425%，賣出成本 0.4425%。</p>

    <!-- 區塊一 -->
    <div class="panel" id="section1">
      <div class="section-title">
        <h2>① 資產與可動用餘額</h2>
        <button class="btn" id="resetBtn">重置</button>
      </div>
      <div class="row">
        <div class="field">
          <label>資產總金額</label>
          <input type="number" id="totalAssets" placeholder="500000" min="0" step="1000" />
        </div>
        <div class="field">
          <label>可動用餘額（自動）</label>
          <input type="text" id="availableCash" class="mono" disabled />
        </div>
      </div>
    </div>

    <!-- 股票選擇器 -->
    <div class="stock-selector">
      <div class="section-title">
        <h2>② 選擇股票</h2>
      </div>
      <div class="stock-tabs" id="stockTabs">
        <!-- 動態生成的股票標籤 -->
      </div>
    </div>

    <!-- 股票內容區域 -->
    <div id="stockSections">
      <!-- 動態生成的股票區塊 -->
    </div>

    <!-- 區塊三：餘額分配 -->
    <div class="panel" id="section3">
      <div class="section-title">
        <h2>③ 餘額分配買張數（試算）</h2>
        <button class="btn icon" id="addPlanBtn">+</button>
      </div>
      <div class="hint">把「可動用餘額」平均分給有填試算買價的組數，再除以（試算買價 × 1000），顯示到小數點後三位。</div>
      <div class="divider"></div>
      <div id="planRows"></div>
    </div>
  </div>

  <script>
  (function(){
    const FEES = { hold: 0.001425, sell: 0.004425 };
    const LOT = 1000;
    const STORAGE_KEY = 'multiStockFifoToolState';
    const $ = (sel, root=document) => root.querySelector(sel);
    const $$ = (sel, root=document) => Array.from(root.querySelectorAll(sel));
    const fmt0 = n => isFinite(n) ? n.toLocaleString('zh-TW', {maximumFractionDigits:0}) : '-';
    const fmt2 = n => isFinite(n) ? n.toLocaleString('zh-TW', {minimumFractionDigits:2, maximumFractionDigits:2}) : '-';
    const fmt3 = n => isFinite(n) ? n.toLocaleString('zh-TW', {minimumFractionDigits:3, maximumFractionDigits:3}) : '-';
    const fmtPct = n => isFinite(n) ? (n*100).toFixed(2)+'%' : '-';

    const state = { 
      totalAssets: 0, 
      stocks: {},
      activeStock: '',
      plans: []
    };
    
    let uid = 1;

    function saveState(){
      const data = {
        totalAssets: state.totalAssets,
        stocks: {},
        activeStock: state.activeStock,
        plans: state.plans.map(p=>({price:p.price}))
      };
      
      // 保存每支股票的數據
      for(const [stockId, stock] of Object.entries(state.stocks)){
        data.stocks[stockId] = {
          symbol: stock.symbol,
          currentPrice: stock.currentPrice,
          buys: stock.buys.map(b=>({price:b.price,lots:b.lots})),
          sells: stock.sells.map(s=>({price:s.price,lots:s.lots}))
        };
      }
      
      localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
    }

    function loadState(){
      const raw = localStorage.getItem(STORAGE_KEY);
      if(!raw) {
        // 創建預設股票
        addStock('stock1', '2330 / 台積電');
        setActiveStock('stock1');
        addDefaultRows('stock1');
        addPlanRow();
        return;
      }
      
      try{
        const data = JSON.parse(raw);
        state.totalAssets = data.totalAssets || 0;
        $('#totalAssets').value = state.totalAssets || '';
        
        // 載入股票數據
        if(data.stocks && Object.keys(data.stocks).length > 0){
          for(const [stockId, stockData] of Object.entries(data.stocks)){
            addStock(stockId, stockData.symbol);
            const stock = state.stocks[stockId];
            stock.currentPrice = stockData.currentPrice;
            
            if(Array.isArray(stockData.buys) && stockData.buys.length){
              stockData.buys.forEach(b=>addBuyRow(stockId, {price:b.price,lots:b.lots}));
            } else { 
              addDefaultRows(stockId); 
            }
            
            if(Array.isArray(stockData.sells) && stockData.sells.length){
              stockData.sells.forEach(s=>addSellRow(stockId, {price:s.price,lots:s.lots}));
            } else { 
              addSellRow(stockId); 
            }
            
            updateStockUI(stockId);
          }
          
          // 設置活動股票
          const firstStockId = Object.keys(state.stocks)[0];
          setActiveStock(data.activeStock && state.stocks[data.activeStock] ? data.activeStock : firstStockId);
        } else {
          addStock('stock1', '2330 / 台積電');
          setActiveStock('stock1');
          addDefaultRows('stock1');
        }
        
        // 載入計劃數據
        if(Array.isArray(data.plans) && data.plans.length){
          data.plans.forEach(p=>addPlanRow({price:p.price}));
        } else { 
          addPlanRow(); 
        }
        
      }catch(e){
        console.error('loadState error',e);
        addStock('stock1', '2330 / 台積電');
        setActiveStock('stock1');
        addDefaultRows('stock1');
        addPlanRow();
      }
    }

    function addStock(stockId, symbol = '') {
      if(state.stocks[stockId]) return;
      
      state.stocks[stockId] = {
        symbol: symbol,
        currentPrice: NaN,
        buys: [],
        sells: []
      };
      
      createStockTab(stockId, symbol);
      createStockSection(stockId);
    }

    function createStockTab(stockId, symbol) {
      const tabsContainer = $('#stockTabs');
      
      // 移除新增按鈕（稍後重新加入）
      const addBtn = $('.add-stock-btn');
      if(addBtn) addBtn.remove();
      
      const tab = document.createElement('button');
      tab.className = 'stock-tab';
      tab.dataset.stockId = stockId;
      tab.textContent = symbol || `股票 ${Object.keys(state.stocks).length}`;
      tab.addEventListener('click', () => setActiveStock(stockId));
      
      // 添加右鍵刪除功能
      tab.addEventListener('contextmenu', (e) => {
        e.preventDefault();
        if(Object.keys(state.stocks).length > 1) {
          if(confirm(`確定要刪除「${tab.textContent}」嗎？`)) {
            removeStock(stockId);
          }
        } else {
          alert('至少需要保留一支股票');
        }
      });
      
      tabsContainer.appendChild(tab);
      
      // 重新加入新增按鈕
      const newAddBtn = document.createElement('button');
      newAddBtn.className = 'add-stock-btn';
      newAddBtn.textContent = '+ 新增股票';
      newAddBtn.addEventListener('click', () => {
        const stockCount = Object.keys(state.stocks).length;
        const newStockId = `stock${Date.now()}`;
        const symbol = prompt('請輸入股票代碼/名稱：', `${2330 + stockCount} / 股票${stockCount + 1}`);
        if(symbol !== null) {
          addStock(newStockId, symbol);
          setActiveStock(newStockId);
          addDefaultRows(newStockId);
          calcAll();
        }
      });
      tabsContainer.appendChild(newAddBtn);
    }

    function createStockSection(stockId) {
      const sectionsContainer = $('#stockSections');
      const section = document.createElement('div');
      section.className = 'stock-section';
      section.dataset.stockId = stockId;
      section.innerHTML = `
        <div class="panel">
          <h2>成本與獲利</h2>

          <!-- 買入成本統計 -->
          <div class="panel" style="background:#0c1020; border:1px dashed #242b43">
            <div class="section-title">
              <h3>買入成本統計</h3>
              <button class="btn icon addBuyBtn">+</button>
            </div>
            <div class="row">
              <div class="field">
                <label>現價</label>
                <input type="number" class="currentPrice" min="0" step="0.01" placeholder="100" />
              </div>
              <div class="field">
                <label>股票代碼 / 名稱</label>
                <input type="text" class="symbol" placeholder="2330 / 台積電" />
              </div>
            </div>
            <div class="divider"></div>
            <div class="buyRows"></div>

            <!-- 合計區 -->
            <div class="totals">
              <div class="pill warn"><span class="muted">剩餘持股（張）：</span> <span class="mono remainLotsTotal">0</span></div>
              <div class="pill"><span class="muted">剩餘投入總資金（含持股成本）：</span> <span class="mono remainCost">0</span></div>
              <div class="pill"><span class="muted">剩餘持股整體損益平衡價：</span> <span class="mono overallBePrice">-</span></div>
              <div class="pill unrealizedPill"><span class="muted">未實現損益：</span> <span class="mono unrealizedPnL">0</span> ｜ <span class="mono unrealizedRoi">0%</span></div>
            </div>
          </div>

          <!-- 賣出獲利統計 -->
          <div class="panel" style="background:#0c1020; border:1px dashed #242b43">
            <div class="section-title">
              <h3>賣出獲利統計（FIFO）</h3>
              <button class="btn icon addSellBtn">+</button>
            </div>
            <div class="sellRows"></div>

            <div class="totals">
              <div class="pill">
                <span class="muted">合計淨回款（已入帳）：</span>
                <span class="mono totalNetProceeds">0</span>
              </div>
              <div class="pill realizedPill">
                <span class="muted">已實現損益：</span>
                <span class="mono realizedPnL">0</span> ｜ 
                <span class="mono realizedRoi">0%</span>
              </div>
            </div>

            <p class="hint">注意：已實現報酬率 = 已實現損益 ÷ FIFO 配對消耗的「買入總金額」（不含費用）。賣出成本以每筆賣出金額 × 0.4425% 計入。支援零股交易（小數第三位）。</p>
            <p class="warnText sellWarn" style="display:none">賣出張數超過可用持股，超出部分不計入計算。</p>
          </div>
        </div>
      `;
      sectionsContainer.appendChild(section);
      
      // 綁定事件
      const currentPriceEl = section.querySelector('.currentPrice');
      const symbolEl = section.querySelector('.symbol');
      const addBuyBtn = section.querySelector('.addBuyBtn');
      const addSellBtn = section.querySelector('.addSellBtn');
      
      currentPriceEl.addEventListener('input', () => {
        state.stocks[stockId].currentPrice = parseFloat(currentPriceEl.value);
        calcAll();
      });
      
      symbolEl.addEventListener('input', () => {
        state.stocks[stockId].symbol = symbolEl.value;
        updateStockTabText(stockId);
        saveState();
      });
      
      addBuyBtn.addEventListener('click', () => addBuyRow(stockId));
      addSellBtn.addEventListener('click', () => addSellRow(stockId));
    }

    function setActiveStock(stockId) {
      state.activeStock = stockId;
      
      // 更新標籤樣式
      $$('.stock-tab').forEach(tab => {
        tab.classList.toggle('active', tab.dataset.stockId === stockId);
      });
      
      // 更新區塊顯示
      $$('.stock-section').forEach(section => {
        section.classList.toggle('active', section.dataset.stockId === stockId);
      });
    }

    function removeStock(stockId) {
      if(!state.stocks[stockId]) return;
      
      delete state.stocks[stockId];
      
      // 移除UI元素
      const tab = $(`.stock-tab[data-stock-id="${stockId}"]`);
      const section = $(`.stock-section[data-stock-id="${stockId}"]`);
      if(tab) tab.remove();
      if(section) section.remove();
      
      // 如果刪除的是活動股票，切換到第一個股票
      if(state.activeStock === stockId) {
        const firstStockId = Object.keys(state.stocks)[0];
        if(firstStockId) {
          setActiveStock(firstStockId);
        }
      }
      
      calcAll();
    }

    function updateStockTabText(stockId) {
      const tab = $(`.stock-tab[data-stock-id="${stockId}"]`);
      if(tab && state.stocks[stockId]) {
        tab.textContent = state.stocks[stockId].symbol || `股票 ${stockId}`;
      }
    }

    function updateStockUI(stockId) {
      const section = $(`.stock-section[data-stock-id="${stockId}"]`);
      if(!section || !state.stocks[stockId]) return;
      
      const stock = state.stocks[stockId];
      const currentPriceEl = section.querySelector('.currentPrice');
      const symbolEl = section.querySelector('.symbol');
      
      if(currentPriceEl) currentPriceEl.value = isFinite(stock.currentPrice) ? stock.currentPrice : '';
      if(symbolEl) symbolEl.value = stock.symbol || '';
    }

    function addDefaultRows(stockId) {
      addBuyRow(stockId); 
      addBuyRow(stockId); 
      addBuyRow(stockId); 
      addSellRow(stockId);
    }

    function addBuyRow(stockId, init={price:'', lots:''}) {
      const section = $(`.stock-section[data-stock-id="${stockId}"]`);
      if(!section) return;
      
      const id = uid++;
      const buyRowsEl = section.querySelector('.buyRows');
      const row = document.createElement('div');
      row.className = 'rowline';
      row.dataset.id = id;
      row.innerHTML = `
        <div class="field"><label>買價</label><input type="number" class="buyPrice" min="0" step="0.01" placeholder="預設帶現價" value="${init.price||''}"/></div>
        <div class="field"><label>買張</label><input type="number" class="buyLots" min="0" step="0.001" placeholder="支援小數第三位" value="${init.lots||''}"/></div>
        <div class="field"><label>剩餘張數</label><input type="text" class="remainLots mono" disabled /></div>
        <div class="actions"><button class="btn icon removeBuy">-</button></div>`;
      buyRowsEl.appendChild(row);
      
      state.stocks[stockId].buys.push({id,price:NaN,lots:0});
      
      row.querySelector('.buyPrice').addEventListener('focus', e => { 
        if(!e.target.value && isFinite(state.stocks[stockId].currentPrice)) {
          e.target.value = state.stocks[stockId].currentPrice;
        }
      });
      row.querySelector('.buyPrice').addEventListener('input', () => {
        const b = state.stocks[stockId].buys.find(x=>x.id===id);
        b.price = parseFloat(row.querySelector('.buyPrice').value);
        calcAll();
      });
      row.querySelector('.buyLots').addEventListener('input', () => {
        const b = state.stocks[stockId].buys.find(x=>x.id===id);
        b.lots = parseFloat(row.querySelector('.buyLots').value||'0');
        calcAll();
      });
      row.querySelector('.removeBuy').addEventListener('click', () => {
        state.stocks[stockId].buys = state.stocks[stockId].buys.filter(x=>x.id!==id);
        row.remove();
        calcAll();
      });
    }

    function addSellRow(stockId, init={price:'',lots:''}) {
      const section = $(`.stock-section[data-stock-id="${stockId}"]`);
      if(!section) return;
      
      const id = uid++;
      const sellRowsEl = section.querySelector('.sellRows');
      const row = document.createElement('div');
      row.className = 'rowline-sell';
      row.dataset.id = id;
      row.innerHTML = `
        <div class="field"><label>賣價</label><input type="number" class="sellPrice" min="0" step="0.01" value="${init.price||''}"/></div>
        <div class="field"><label>賣張</label><input type="number" class="sellLots" min="0" step="0.001" placeholder="支援小數第三位" value="${init.lots||''}"/></div>
        <div class="actions"><button class="btn icon removeSell">-</button></div>`;
      sellRowsEl.appendChild(row);
      
      state.stocks[stockId].sells.push({id,price:NaN,lots:0});
      
      row.querySelector('.sellPrice').addEventListener('input', () => {
        const s = state.stocks[stockId].sells.find(x=>x.id===id);
        s.price = parseFloat(row.querySelector('.sellPrice').value);
        calcAll();
      });
      row.querySelector('.sellLots').addEventListener('input', () => {
        const s = state.stocks[stockId].sells.find(x=>x.id===id);
        s.lots = parseFloat(row.querySelector('.sellLots').value||'0');
        calcAll();
      });
      row.querySelector('.removeSell').addEventListener('click', () => {
        state.stocks[stockId].sells = state.stocks[stockId].sells.filter(x=>x.id!==id);
        row.remove();
        calcAll();
      });
    }

    function addPlanRow(init={price:''}) {
      const planRowsEl = $('#planRows');
      const id = uid++;
      const row = document.createElement('div');
      row.className = 'plan-row';
      row.dataset.id = id;
      row.innerHTML = `
        <div class="field"><label>組${state.plans.length + 1} 試算買價</label><input type="number" class="planPrice" min="0" step="0.01" placeholder="50" value="${init.price||''}" /></div>
        <div class="field"><label>組${state.plans.length + 1} 可買張（自動）</label><input type="text" class="planLots mono" disabled /></div>
        <div class="actions"><button class="btn icon removePlan">-</button></div>`;
      planRowsEl.appendChild(row);
      
      state.plans.push({id, price:NaN});
      
      row.querySelector('.planPrice').addEventListener('input', () => {
        const p = state.plans.find(x=>x.id===id);
        p.price = parseFloat(row.querySelector('.planPrice').value);
        calcAll();
      });
      row.querySelector('.removePlan').addEventListener('click', () => {
        state.plans = state.plans.filter(x=>x.id!==id);
        row.remove();
        updatePlanLabels();
        calcAll();
      });
      updatePlanLabels();
    }

    function updatePlanLabels() {
      const planRowElems = $$('#planRows .plan-row');
      planRowElems.forEach((row, index) => {
        const labels = row.querySelectorAll('label');
        labels[0].textContent = `組${index + 1} 試算買價`;
        labels[1].textContent = `組${index + 1} 可買張（自動）`;
      });
    }

    function calcAll() {
      let totalBuyAmtAll = 0;
      let totalNetProceedsAll = 0;
      
      // 計算每支股票
      for(const [stockId, stock] of Object.entries(state.stocks)) {
        const section = $(`.stock-section[data-stock-id="${stockId}"]`);
        if(!section) continue;
        
        let totalBuyAmt = 0;
        const buyRowElems = section.querySelectorAll('.buyRows .rowline');
        const buyInventory = [];
        
        buyRowElems.forEach(row => {
          const id = parseInt(row.dataset.id, 10);
          const b = stock.buys.find(x=>x.id===id);
          const price = parseFloat(row.querySelector('.buyPrice').value);
          const lots = parseFloat(row.querySelector('.buyLots').value||'0');
          b.price = isFinite(price) ? price : NaN;
          b.lots = isFinite(lots) ? lots : 0;
          
          const shares = isFinite(price) && lots > 0 ? lots * LOT : 0;
          const buyAmt = shares > 0 ? price * shares : 0;
          totalBuyAmt += buyAmt;
          
          row.querySelector('.remainLots').value = '';
          
          if(shares > 0) {
            buyInventory.push({id, price, shares, costPerShare: price * (1 + FEES.hold), remain: shares});
          }
        });

        let totalSellGross = 0, totalSellCost = 0, totalNetProceeds = 0;
        const sellRowElems = section.querySelectorAll('.sellRows .rowline-sell');
        const sells = [];
        
        sellRowElems.forEach(row => {
          const id = parseInt(row.dataset.id, 10);
          const s = stock.sells.find(x=>x.id===id);
          const price = parseFloat(row.querySelector('.sellPrice').value);
          const lots = parseFloat(row.querySelector('.sellLots').value||'0');
          s.price = isFinite(price) ? price : NaN;
          s.lots = isFinite(lots) ? lots : 0;
          
          const shares = isFinite(price) && lots > 0 ? lots * LOT : 0;
          const sellAmt = shares > 0 ? price * shares : 0;
          const sellCost = sellAmt * FEES.sell;
          const net = sellAmt - sellCost;
          totalSellGross += sellAmt;
          totalSellCost += sellCost;
          totalNetProceeds += net;
          
          if(shares > 0) sells.push({shares, price});
        });

        let realizedPnL = 0, matchedBuyAmtBase = 0, overflowSell = false;
        for(const sell of sells) {
          let toSell = sell.shares;
          const sellNetPerShare = sell.price * (1 - FEES.sell);
          for(const lot of buyInventory) {
            if(toSell <= 0) break;
            if(lot.remain <= 0) continue;
            const q = Math.min(toSell, lot.remain);
            realizedPnL += q * (sellNetPerShare - lot.costPerShare);
            matchedBuyAmtBase += q * lot.price;
            lot.remain -= q;
            toSell -= q;
          }
          if(toSell > 0) overflowSell = true;
        }

        const remainCost = buyInventory.reduce((a,l) => a + l.remain * l.costPerShare, 0);
        const remainLots = buyInventory.reduce((a,l) => a + l.remain / LOT, 0);
        let overallBePrice = NaN;
        if(remainLots > 0 && isFinite(stock.currentPrice)) {
          const remainShares = remainLots * LOT;
          const estSellCost = stock.currentPrice * remainShares * FEES.sell;
          overallBePrice = (remainCost + estSellCost) / remainShares;
        }

        // 計算未實現損益
        let unrealizedPnL = 0;
        let unrealizedRoi = NaN;
        if(remainLots > 0 && isFinite(stock.currentPrice)) {
          const remainShares = remainLots * LOT;
          const currentValue = stock.currentPrice * remainShares;
          const estSellCost = currentValue * FEES.sell;
          const netCurrentValue = currentValue - estSellCost;
          unrealizedPnL = netCurrentValue - remainCost;
          unrealizedRoi = remainCost > 0 ? (unrealizedPnL / remainCost) : NaN;
        }

        // 更新個別買入行的剩餘張數
        buyRowElems.forEach(row => {
          const id = parseInt(row.dataset.id, 10);
          const lot = buyInventory.find(x=>x.id===id);
          row.querySelector('.remainLots').value = fmt3(lot ? lot.remain / LOT : 0);
        });

        const realizedRoi = matchedBuyAmtBase > 0 ? (realizedPnL / matchedBuyAmtBase) : NaN;

        // 更新UI
        const remainCostEl = section.querySelector('.remainCost');
        const remainLotsTotalEl = section.querySelector('.remainLotsTotal');
        const overallBePriceEl = section.querySelector('.overallBePrice');
        const totalNetProceedsEl = section.querySelector('.totalNetProceeds');
        const realizedPnLEl = section.querySelector('.realizedPnL');
        const realizedRoiEl = section.querySelector('.realizedRoi');
        const realizedPillEl = section.querySelector('.realizedPill');
        const unrealizedPnLEl = section.querySelector('.unrealizedPnL');
        const unrealizedRoiEl = section.querySelector('.unrealizedRoi');
        const unrealizedPillEl = section.querySelector('.unrealizedPill');
        const sellWarnEl = section.querySelector('.sellWarn');

        if(remainCostEl) remainCostEl.textContent = fmt0(remainCost);
        if(remainLotsTotalEl) remainLotsTotalEl.textContent = fmt3(remainLots);
        if(overallBePriceEl) overallBePriceEl.textContent = isFinite(overallBePrice) ? fmt3(overallBePrice) : '-';
        if(totalNetProceedsEl) totalNetProceedsEl.textContent = fmt0(totalNetProceeds);
        if(realizedPnLEl) realizedPnLEl.textContent = fmt0(realizedPnL);
        if(realizedRoiEl) realizedRoiEl.textContent = fmtPct(realizedRoi);
        if(unrealizedPnLEl) unrealizedPnLEl.textContent = fmt0(unrealizedPnL);
        if(unrealizedRoiEl) unrealizedRoiEl.textContent = fmtPct(unrealizedRoi);

        if(realizedPillEl) {
          realizedPillEl.classList.remove('gain', 'loss', 'warn');
          if(!isFinite(realizedRoi)) realizedPillEl.classList.add('warn');
          else if(realizedPnL > 0) realizedPillEl.classList.add('gain');
          else if(realizedPnL < 0) realizedPillEl.classList.add('loss');
        }

        if(unrealizedPillEl) {
          unrealizedPillEl.classList.remove('gain', 'loss', 'warn');
          if(!isFinite(unrealizedRoi) || remainLots === 0) unrealizedPillEl.classList.add('warn');
          else if(unrealizedPnL > 0) unrealizedPillEl.classList.add('gain');
          else if(unrealizedPnL < 0) unrealizedPillEl.classList.add('loss');
        }

        if(sellWarnEl) sellWarnEl.style.display = overflowSell ? '' : 'none';

        totalBuyAmtAll += totalBuyAmt;
        totalNetProceedsAll += totalNetProceeds;
      }

      // 更新總覽
      const availEl = $('#availableCash');
      const avail = (state.totalAssets || 0) - totalBuyAmtAll + totalNetProceedsAll;
      if(availEl) availEl.value = fmt0(avail);

      // 更新計劃區塊
      const planRowElems = $$('#planRows .plan-row');
      const planPrices = [];
      planRowElems.forEach(row => {
        const id = parseInt(row.dataset.id, 10);
        const p = state.plans.find(x => x.id === id);
        const price = parseFloat(row.querySelector('.planPrice').value);
        p.price = isFinite(price) && price > 0 ? price : NaN;
        planPrices.push(p.price);
      });
      const validPrices = planPrices.filter(v => isFinite(v));
      const validCount = validPrices.length;
      const alloc = (avail > 0 && validCount > 0) ? (avail / validCount) : 0;
      planRowElems.forEach((row, index) => {
        const price = planPrices[index];
        const planLotsEl = row.querySelector('.planLots');
        if(!isFinite(price) || price <= 0 || alloc <= 0) {
          planLotsEl.value = '';
        } else {
          const canLots = alloc / (price * LOT);
          planLotsEl.value = isFinite(canLots) && canLots > 0 ? fmt3(canLots) : '0.000';
        }
      });

      saveState();
    }

    // 初始化
    $('#totalAssets').addEventListener('input', () => {
      state.totalAssets = parseFloat($('#totalAssets').value) || 0;
      calcAll();
    });

    $('#addPlanBtn').addEventListener('click', () => addPlanRow());

    $('#resetBtn').addEventListener('click', () => {
      if(confirm('確定要重置所有數據嗎？')) {
        localStorage.removeItem(STORAGE_KEY);
        location.reload();
      }
    });

    loadState();
    calcAll();
  })();
  </script>
</body>
</html>

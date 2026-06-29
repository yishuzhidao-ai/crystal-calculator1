<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>润雅串珠 - 高级计算器</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;700&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Noto Sans SC', system-ui, sans-serif;
            background: linear-gradient(135deg, #fdfaf5, #f0e6d2);
            color: #3c2f2f;
            padding: 15px 10px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 24px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            overflow: hidden;
        }
        
        header {
            background: linear-gradient(90deg, #d4a17b, #e8c8a0);
            color: white;
            padding: 25px 15px;
            text-align: center;
        }
        
        h1 { font-size: 1.9rem; }
        
        .calc-body {
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        @media (min-width: 768px) {
            .calc-body { flex-direction: row; padding: 40px; gap: 40px; }
        }
        
        .search-box input {
            width: 100%;
            padding: 14px 16px;
            border: 2px solid #d4a17b;
            border-radius: 14px;
            font-size: 1.05rem;
        }
        
        .material-list {
            max-height: 260px;
            overflow-y: auto;
            border: 1px solid #eee;
            border-radius: 12px;
            margin-bottom: 15px;
        }
        
        .material-item {
            padding: 12px 16px;
            cursor: pointer;
            border-bottom: 1px solid #f0f0f0;
        }
        
        .material-item:hover, .material-item.selected {
            background: #fff8eb;
        }
        
        .input-group { margin: 18px 0; }
        label { display: block; margin-bottom: 8px; font-weight: 500; }
        
        input[type="number"] {
            width: 100%;
            padding: 14px;
            border: 2px solid #e8d8c4;
            border-radius: 12px;
        }
        
        button {
            width: 100%;
            padding: 16px;
            background: #d4a17b;
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.15rem;
            cursor: pointer;
        }
        
        .result-panel {
            background: #fdf8f0;
            padding: 25px 20px;
            border-radius: 20px;
            text-align: center;
        }
        
        .result-value {
            font-size: 2.6rem;
            font-weight: 700;
            color: #d4a17b;
        }
        
        .history { margin-top: 25px; }
        table { width: 100%; border-collapse: collapse; font-size: 0.9rem; }
        th, td { padding: 8px; text-align: left; border-bottom: 1px solid #eee; }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>润雅串珠计算器</h1>
            <p>重量 + 价格 一键计算</p>
        </header>
        
        <div class="calc-body">
            <div>
                <div class="search-box">
                    <input type="text" id="materialSearch" placeholder="搜索并选择材质..." onkeyup="filterMaterials()">
                </div>
                <div class="material-list" id="materialList"></div>
                
                <div class="input-group">
                    <label>珠子直径 (mm)</label>
                    <input type="number" id="diameter" value="8" step="0.1">
                </div>
                
                <div class="input-group">
                    <label>珠子数量</label>
                    <input type="number" id="count" value="16">
                </div>
                
                <div class="input-group">
                    <label>单价 (元/克)</label>
                    <input type="number" id="pricePerGram" value="8" step="0.5">
                </div>
                
                <button onclick="calculate()">计算重量与价格</button>
            </div>
            
            <div>
                <div class="result-panel">
                    <h3 id="materialName">请选择材质</h3>
                    <div class="result-value" id="singleWeight">— g</div>
                    <p>单颗重量</p>
                    
                    <div class="result-value" id="singlePrice" style="color:#e74c3c; margin:10px 0;">— 元</div>
                    <p>单颗价格</p>
                    
                    <div style="margin:20px 0; height:1px; background:#ddd;"></div>
                    
                    <div class="result-value" id="totalWeight">— g</div>
                    <p>整串总重量</p>
                    
                    <div class="result-value" id="totalPrice" style="color:#e74c3c;">— 元</div>
                    <p>整串总价格</p>
                </div>
                
                <div class="history">
                    <h3>历史记录</h3>
                    <table id="historyTable">
                        <thead><tr><th>材质</th><th>直径</th><th>数量</th><th>总重</th><th>总价</th></tr></thead>
                        <tbody></tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <script>
        let materials = [
            {name: "白水晶", density: 2.65}, {name: "紫水晶", density: 2.65},
            {name: "黄水晶", density: 2.65}, {name: "紫黄晶", density: 2.65},
            {name: "茶晶", density: 2.65}, {name: "墨晶", density: 2.65},
            {name: "普通粉晶", density: 2.65}, {name: "马粉", density: 2.65},
            {name: "星光粉晶", density: 2.65}, {name: "金发晶", density: 2.65},
            {name: "钛晶", density: 2.65}, {name: "黑发晶", density: 2.65},
            {name: "银发晶", density: 2.65}, {name: "铜发晶", density: 2.65},
            {name: "绿发晶", density: 2.65}, {name: "蓝发晶", density: 2.65},
            {name: "彩发晶", density: 2.65}, {name: "红兔毛", density: 2.65},
            {name: "白兔毛", density: 2.65}, {name: "金兔毛", density: 2.65},
            {name: "绿兔毛", density: 2.65}, {name: "粉兔毛", density: 2.65},
            {name: "彩兔毛", density: 2.65}, {name: "绿幽灵", density: 2.65},
            {name: "红胶花", density: 2.58}, {name: "芬达胶花", density: 2.58},
            {name: "超七", density: 2.65}, {name: "极光", density: 2.65},
            {name: "紫锂辉", density: 3.1}, {name: "葡萄石", density: 2.9},
            {name: "萤石", density: 3.18}, {name: "彩虹水晶", density: 2.65},
            {name: "红玛瑙", density: 2.6}, {name: "黑玛瑙", density: 2.6},
            {name: "白玛瑙", density: 2.6}, {name: "灰玛瑙", density: 2.6},
            {name: "蓝纹玛瑙", density: 2.6}, {name: "花玛瑙", density: 2.6},
            {name: "战国红", density: 2.6}, {name: "南红", density: 2.6},
            {name: "盐源玛瑙", density: 2.6}, {name: "蓝玉髓", density: 2.58},
            {name: "白玉髓", density: 2.58}, {name: "海洋玉髓", density: 2.58},
            {name: "水草玛瑙", density: 2.6}, {name: "樱花玛瑙", density: 2.6},
            {name: "白月光石", density: 2.56}, {name: "灰月光石", density: 2.56},
            {name: "拉长石", density: 2.56}, {name: "太阳石", density: 2.65},
            {name: "黄虎眼", density: 2.64}, {name: "红虎眼", density: 2.64},
            {name: "蓝虎眼", density: 2.64}, {name: "彩虎眼", density: 2.64},
            {name: "海蓝宝", density: 2.7}, {name: "蓝纹石", density: 2.7},
            {name: "青金石", density: 2.4}, {name: "方钠石", density: 2.3},
            {name: "绿东陵", density: 2.65}, {name: "蓝东陵", density: 2.65},
            {name: "橄榄石", density: 3.3}, {name: "绿草莓晶", density: 2.65},
            {name: "绿龙晶", density: 2.65}, {name: "草莓晶", density: 2.65},
            {name: "红纹石", density: 2.9}, {name: "酒红石榴石", density: 3.8},
            {name: "芬达石榴石", density: 3.8}, {name: "蔷薇辉石", density: 3.5},
            {name: "彩虹碧玺", density: 3.1}, {name: "西瓜碧玺", density: 3.1},
            {name: "黑曜石", density: 2.35}, {name: "金曜石", density: 2.35},
            {name: "银曜石", density: 2.35}, {name: "彩曜石", density: 2.35},
            {name: "冰彩黑曜石", density: 2.35}, {name: "黑碧玺", density: 3.0},
            {name: "天河石", density: 2.56}, {name: "紫龙晶", density: 2.65},
            {name: "舒俱来", density: 2.9}, {name: "方解石", density: 2.71},
            {name: "堇青石", density: 2.58}, {name: "孔雀石", density: 3.6},
            {name: "红碧玉", density: 2.65}, {name: "黄玉", density: 3.5},
            {name: "托帕石", density: 3.5}
        ];
        
        let currentMaterial = null;
        let history = [];
        
        function renderMaterials(filtered) {
            const container = document.getElementById('materialList');
            container.innerHTML = '';
            filtered.forEach(mat => {
                const div = document.createElement('div');
                div.className = 'material-item';
                div.textContent = mat.name;
                div.onclick = () => selectMaterial(mat, div);
                container.appendChild(div);
            });
        }
        
        function selectMaterial(mat, element) {
            currentMaterial = mat;
            document.getElementById('materialSearch').value = mat.name;
            document.querySelectorAll('.material-item').forEach(el => el.classList.remove('selected'));
            element.classList.add('selected');
            document.getElementById('materialList').style.maxHeight = '60px'; // 收起
        }
        
        function filterMaterials() {
            const keyword = document.getElementById('materialSearch').value.toLowerCase().trim();
            const filtered = materials.filter(m => m.name.toLowerCase().includes(keyword));
            renderMaterials(filtered.length ? filtered : materials);
        }
        
        function calculate() {
            if (!currentMaterial) return alert("请先选择一种材质！");
            
            const diameter = parseFloat(document.getElementById('diameter').value);
            const count = parseInt(document.getElementById('count').value);
            const pricePerGram = parseFloat(document.getElementById('pricePerGram').value) || 8;
            
            const radiusCM = diameter / 20;
            const volume = (4 / 3) * Math.PI * Math.pow(radiusCM, 3);
            const singleWeight = (volume * currentMaterial.density).toFixed(3);
            const totalWeight = (singleWeight * count).toFixed(2);
            const singlePrice = (singleWeight * pricePerGram).toFixed(2);
            const totalPrice = (totalWeight * pricePerGram).toFixed(1);
            
            document.getElementById('materialName').textContent = currentMaterial.name;
            document.getElementById('singleWeight').textContent = singleWeight + " g";
            document.getElementById('singlePrice').textContent = singlePrice + " 元";
            document.getElementById('totalWeight').textContent = totalWeight + " g";
            document.getElementById('totalPrice').textContent = totalPrice + " 元";
            
            history.unshift({
                material: currentMaterial.name,
                diameter: diameter,
                count: count,
                totalWeight: totalWeight,
                totalPrice: totalPrice
            });
            if (history.length > 8) history.pop();
            renderHistory();
        }
        
        function renderHistory() {
            const tbody = document.querySelector('#historyTable tbody');
            tbody.innerHTML = '';
            history.forEach(item => {
                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td>${item.material}</td>
                    <td>${item.diameter}mm</td>
                    <td>${item.count}</td>
                    <td>${item.totalWeight}g</td>
                    <td>${item.totalPrice}元</td>
                `;
                tbody.appendChild(tr);
            });
        }
        
        window.onload = () => {
            renderMaterials(materials);
        };
    </script>
</body>
</html>

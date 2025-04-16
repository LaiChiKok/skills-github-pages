```html
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anytime Fitness 註冊會員及套餐選擇</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #3a7bd5;
            --secondary-color: #00d2ff;
            --text-color: #333;
            --light-gray: #f5f5f5;
            --white: #ffffff;
            --border-radius: 8px;
            --box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            color: var(--text-color);
            background-color: var(--light-gray);
            line-height: 1.6;
            padding: 20px;
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--white);
            padding: 20px 0;
            text-align: center;
            margin-bottom: 30px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
        }

        h1 {
            font-size: 28px;
            margin-bottom: 10px;
        }

        .packages-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .package-card {
            background: var(--white);
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .package-card:hover {
            transform: translateY(-5px);
        }

        .package-header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--white);
            padding: 15px 20px;
        }

        .package-title {
            font-size: 20px;
            margin-bottom: 5px;
        }

        .package-body {
            padding: 20px;
        }

        .price-container {
            display: flex;
            align-items: flex-end;
            margin-bottom: 20px;
        }

        .price {
            font-size: 32px;
            font-weight: 700;
            color: var(--primary-color);
        }

        .fee-item {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px dashed #eee;
        }

        .total-price {
            font-size: 20px;
            font-weight: 700;
            color: var(--primary-color);
            margin-top: 10px;
        }

        .form-container {
            background: var(--white);
            padding: 20px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            margin-top: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        input, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-family: inherit;
        }

        button {
            background: var(--primary-color);
            color: white;
            padding: 12px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            font-size: 16px;
            font-weight: 500;
            transition: background-color 0.3s;
        }

        button:hover {
            background: #2980b9;
        }

        .selected {
            border: 2px solid var(--primary-color);
            position: relative;
        }

        .selected-label {
            position: absolute;
            top: -10px;
            right: 20px;
            background-color: var(--primary-color);
            color: white;
            padding: 3px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }

        @media (max-width: 768px) {
            .packages-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

<header>
    <h1>Anytime Fitness 會員註冊及套餐選擇</h1>
    <p>立即加入，開始您的健身旅程</p>
</header>

<div class="packages-container">
    <!-- 1個月套餐 -->
    <div class="package-card" id="package1">
        <div class="package-header">
            <h2 class="package-title">1個月會籍套餐</h2>
        </div>
        <div class="package-body">
            <div class="price-container">
                <span class="price">$850</span>
                <span>/月</span>
            </div>
            <div class="fee-item">
                <span>入會費</span>
                <span>$500</span>
            </div>
            <div class="fee-item">
                <span>鎖匙費</span>
                <span>$500</span>
            </div>
            <div class="fee-item">
                <span>合約期</span>
                <span>1個月</span>
            </div>
            <div class="total-price">總價: $1,850</div>
            <button onclick="selectPackage('package1', '1個月會藉')">選擇此套餐</button>
        </div>
    </div>

    <!-- 6個月套餐 -->
    <div class="package-card" id="package6">
        <div class="package-header">
            <h2 class="package-title">6個月持續型扣款套餐</h2>
        </div>
        <div class="package-body">
            <div class="price-container">
                <span class="price">$650</span>
                <span>/月</span>
            </div>
            <div class="fee-item">
                <span>入會費</span>
                <span>$0</span>
            </div>
            <div class="fee-item">
                <span>鎖匙費</span>
                <span>$500</span>
            </div>
            <div class="fee-item">
                <span>合約期</span>
                <span>6個月</span>
            </div>
            <div class="total-price">總價: $1,150</div>
            <button onclick="selectPackage('package6', '6個月會藉')">選擇此套餐</button>
        </div>
    </div>

    <!-- 12個月套餐 -->
    <div class="package-card" id="package12">
        <div class="package-header">
            <h2 class="package-title">12個月持續型扣款套餐</h2>
        </div>
        <div class="package-body">
            <div class="price-container">
                <span class="price">$550</span>
                <span>/月</span>
            </div>
            <div class="fee-item">
                <span>入會費</span>
                <span>$0</span>
            </div>
            <div class="fee-item">
                <span>鎖匙費</span>
                <span>$500</span>
            </div>
            <div class="fee-item">
                <span>合約期</span>
                <span>12個月</span>
            </div>
            <div class="total-price">總價: $1,050</div>
            <button onclick="selectPackage('package12', '12個月會藉')">選擇此套餐</button>
        </div>
    </div>

    <!-- 13個月套餐 -->
    <div class="package-card" id="package13">
        <div class="package-header">
            <h2 class="package-title">13個月持續型扣款套餐</h2>
        </div>
        <div class="package-body">
            <div class="price-container">
                <span class="price">$6,600</span>
                <span>(一次性)</span>
            </div>
            <div class="fee-item">
                <span>入會費</span>
                <span>$0</span>
            </div>
            <div class="fee-item">
                <span>鎖匙費</span>
                <span>$500</span>
            </div>
            <div class="fee-item">
                <span>合約期</span>
                <span>13個月</span>
            </div>
            <div class="total-price">總價: $7,100</div>
            <button onclick="selectPackage('package13', '13個月會藉')">選擇此套餐</button>
        </div>
    </div>
</div>

<div class="form-container">
    <form id="registrationForm" onsubmit="submitForm(event)">
        <div class="form-group">
            <label for="lastName">姓 (LAST NAME) *</label>
            <input type="text" id="lastName" name="lastName" required>
        </div>
        <div class="form-group">
            <label for="firstName">名 (FIRST NAME) *</label>
            <input type="text" id="firstName" name="firstName" required>
        </div>
        <div class="form-group">
            <label for="dob">出生日期 (DATE OF BIRTH) *</label>
            <input type="date" id="dob" name="dob" required>
        </div>
        <div class="form-group">
            <label for="sex">性別 (SEX) *</label>
            <select id="sex" name="sex" required>
                <option value="">請選擇</option>
                <option value="M">男 (M)</option>
                <option value="F">女 (F)</option>
            </select>
        </div>
        <div class="form-group">
            <label for="email">電子郵件 (E-MAIL) *</label>
            <input type="email" id="email" name="email" required>
        </div>
        <div class="form-group">
            <label for="phone">電話號碼 (PHONE NUMBER) *</label>
            <input type="tel" id="phone" name="phone" required>
        </div>
        <div class="form-group">
            <label for="address">街道地址 (STREET ADDRESS)</label>
            <input type="text" id="address" name="address">
        </div>
        <div class="form-group">
            <label for="area">地區 (AREA)</label>
            <select id="area" name="area">
                <option value="">請選擇</option>
                <option value="香港區">香港區</option>
                <option value="九龍區">九龍區</option>
                <option value="新界區">新界區</option>
                <option value="Other">其他</option>
            </select>
        </div>
        <div class="form-group">
            <label for="emergencyContact">緊急聯絡人 (EMERGENCY CONTACT) *</label>
            <input type="text" id="emergencyContact" name="emergencyContact" required>
        </div>
        <div class="form-group">
            <label for="emergencyPhone">緊急聯絡電話 (PHONE NUMBER) *</label>
            <input type="tel" id="emergencyPhone" name="emergencyPhone" required>
        </div>
        <div class="form-group">
            <label for="branch">註冊分店 (Registered Branch) *</label>
            <select id="branch" name="branch" required>
                <option value="">請選擇分店</option>
                <option value="葵芳 Kwai Fong">葵芳 Kwai Fong</option>
                <option value="葵興 Kwai Hing">葵興 Kwai Hing</option>
                <option value="荔枝角 Lai Chi Kok">荔枝角 Lai Chi Kok</option>
                <option value="深水埗 Sham Shui Po">深水埗 Sham Shui Po</option>
                <option value="元朗 Yuen Long">元朗 Yuen Long</option>
            </select>
        </div>
        <div class="form-group">
            <label for="contract">會藉合約 (MEMBER CONTRACT) *</label>
            <select id="contract" name="contract" required>
                <option value="">請選擇會藉</option>
                <option value="1個月會藉">1個月會藉 (1 MONTHS CONTRACT)</option>
                <option value="6個月會藉">6個月會藉 (6 MONTHS CONTRACT)</option>
                <option value="12個月會藉">12個月會藉 (12 MONTHS CONTRACT)</option>
                <option value="13個月會藉">13個月會藉 (13 MONTHS CONTRACT) (PREPAY)</option>
            </select>
        </div>
        <button type="submit">提交註冊及付款</button>
    </form>
</div>

<script>
    // 當前選擇的套餐
    let selectedPackage = null;
    
    // 選擇套餐函數
    function selectPackage(packageId, contractType) {
        // 移除所有卡片的selected類
        document.querySelectorAll('.package-card').forEach(card => {
            card.classList.remove('selected');
            const existingLabel = card.querySelector('.selected-label');
            if (existingLabel) {
                card.removeChild(existingLabel);
            }
        });
        
        // 添加selected類到當前選擇的卡片
        const selectedCard = document.getElementById(packageId);
        selectedCard.classList.add('selected');
        
        // 添加selected標籤
        const label = document.createElement('div');
        label.className = 'selected-label';
        label.textContent = '已選擇';
        selectedCard.appendChild(label);
        
        // 更新表單中的合約類型
        document.getElementById('contract').value = contractType;
        
        // 保存當前選擇的套餐
        selectedPackage = packageId;
    }
    
    // 表單提交函數
    function submitForm(event) {
        event.preventDefault();
        
        // 檢查是否已選擇套餐
        if (!selectedPackage) {
            alert('請先選擇一個會籍套餐');
            return;
        }
        
        // 獲取表單數據
        const formData = new FormData(document.getElementById('registrationForm'));
        const formDataObj = {};
        formData.forEach((value, key) => {
            formDataObj[key] = value;
        });
        
        // 根據選擇的套餐重定向到相應的支付頁面
        switch(selectedPackage) {
            case 'package1':
                window.location.href = 'https://buy.stripe.com/fZe00A9XP30ugE09AD';
                break;
            case 'package6':
                window.location.href = 'https://buy.stripe.com/3cs3cM2vn30u1J628c';
                break;
            case 'package12':
            case 'package13':
                window.location.href = 'https://buy.stripe.com/14k28I0nf0SmgE0cMR';
                break;
            default:
                alert('請選擇有效的會籍套餐');
        }
        
        // 這裡可以添加實際的表單提交邏輯，如發送到服務器等
        console.log('表單數據:', formDataObj);
    }
</script>

</body>
</html>
```

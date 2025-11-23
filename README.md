<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Enjoy Coffee - Order Menu</title>
<style>
body {
  font-family: "Be Vietnam Pro", sans-serif;
  background-color: #e8f5e9;
  color: #333;
  margin: 0;
  padding: 0;
}
header {
  background-color: #2e7d32;
  color: white;
  text-align: center;
  padding: 15px;
  font-size: 22px;
  font-weight: bold;
  letter-spacing: 1px;
}
.container {
  max-width: 800px;
  margin: 20px auto;
  background: white;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}
h2 {
  color: #1b5e20;
  border-bottom: 2px solid #81c784;
  padding-bottom: 6px;
}
.menu-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 0;
  border-bottom: 1px solid #eee;
}
.menu-item select {
  margin-left: 5px;
}
button {
  background-color: #43a047;
  color: white;
  border: none;
  padding: 8px 14px;
  border-radius: 8px;
  cursor: pointer;
  margin: 2px;
}
button:hover {
  background-color: #2e7d32;
}
#order-table {
  width: 100%;
  margin-top: 20px;
  border-collapse: collapse;
}
#order-table th, #order-table td {
  border: 1px solid #ccc;
  padding: 8px;
  text-align: center;
}
#order-table th {
  background-color: #a5d6a7;
}
.total {
  text-align: right;
  margin-top: 10px;
  font-weight: bold;
  font-size: 18px;
}
.bill {
  background-color: #f1f8e9;
  padding: 10px;
  margin-top: 20px;
  border-radius: 8px;
  white-space: pre-line;
  font-family: monospace;
}
.history {
  background-color: #e0f2f1;
  padding: 10px;
  border-radius: 8px;
  margin-top: 15px;
  max-height: 400px;
  overflow-y: auto;
}
.delete-btn {
  background-color: #ef5350;
  padding: 4px 10px;
}
.delete-btn:hover {
  background-color: #d32f2f;
}
.export-btn {
  background-color: #1976d2;
  margin-top: 10px;
}
.export-btn:hover {
  background-color: #1565c0;
}
.stats-btn {
  background-color: #7b1fa2;
  margin-top: 10px;
}
.stats-btn:hover {
  background-color: #6a1b9a;
}
.history-controls {
  display: flex;
  gap: 10px;
  margin-bottom: 10px;
  flex-wrap: wrap;
}
.history-item {
  margin-bottom: 15px;
  padding: 10px;
  border: 1px solid #81c784;
  border-radius: 8px;
  background-color: white;
}
.history-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  padding: 5px;
}
.history-content {
  margin-top: 10px;
  padding: 10px;
  background-color: #f9f9f9;
  border-radius: 5px;
  white-space: pre-line;
  font-family: monospace;
}
.stats-section {
  background-color: #fff3e0;
  padding: 15px;
  border-radius: 8px;
  margin-top: 20px;
}
.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
  margin-top: 15px;
}
.stat-card {
  background: white;
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
.stat-value {
  font-size: 24px;
  font-weight: bold;
  color: #2e7d32;
}
.stat-label {
  font-size: 14px;
  color: #666;
  margin-top: 5px;
}
.price-info {
  font-size: 12px;
  color: #666;
  margin-top: 3px;
}
.menu-item-content {
  display: flex;
  flex-direction: column;
}
</style>
</head>
<body>
<header>☕ ENJOY COFFEE - MENU ORDER 💚</header>
<div class="container">
  <!-- BEST SELLER SECTION -->
  <h2>🔥 Best Seller</h2>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Sữa tươi cà phê Ly lớn</div>
      <div class="price-info">22.000đ</div>
    </div>
    <button onclick="addItem('Sữa tươi cà phê Ly lớn', 22000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cà phê muối</div>
      <div class="price-info">S: 18.000đ | L: 25.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="S">S</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cà phê muối', 18000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Matcha Latte</div>
      <div class="price-info">25.000đ</div>
    </div>
    <button onclick="addItem('Matcha Latte', 25000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà sữa truyền thống</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Trà sữa truyền thống', 20000)">Thêm</button>
  </div>

  <!-- CÀ PHÊ SECTION -->
  <h2>☕ Cà Phê</h2>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cà phê đá</div>
      <div class="price-info">M: 14.000đ | L: 18.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cà phê đá', 14000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cà phê sữa</div>
      <div class="price-info">M: 16.000đ | L: 20.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cà phê sữa', 16000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cà phê muối</div>
      <div class="price-info">M: 18.000đ | L: 24.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cà phê muối', 18000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Bạc xỉu</div>
      <div class="price-info">M: 18.000đ | L: 22.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Bạc xỉu', 18000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Bạc xỉu muối</div>
      <div class="price-info">M: 22.000đ | L: 26.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Bạc xỉu muối', 22000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cacao sữa</div>
      <div class="price-info">M: 17.000đ | L: 22.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cacao sữa', 17000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Cacao muối</div>
      <div class="price-info">M: 20.000đ | L: 25.000đ</div>
    </div>
    <div>
      <select class="size">
        <option value="M">M</option>
        <option value="L">L</option>
      </select>
      <button onclick="addItem('Cacao muối', 20000, this)">Thêm</button>
    </div>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Milo dầm trân châu trắng</div>
      <div class="price-info">17.000đ</div>
    </div>
    <button onclick="addItem('Milo dầm trân châu trắng', 17000)">Thêm</button>
  </div>

  <!-- TRÀ GIẢI KHÁT SECTION -->
  <h2>🍵 Trà Giải Khát</h2>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà đào</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Trà đào', 20000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà dâu</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Trà dâu', 20000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà vải</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Trà vải', 20000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà ổi</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Trà ổi', 20000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Chanh đá</div>
      <div class="price-info">15.000đ</div>
    </div>
    <button onclick="addItem('Chanh đá', 15000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Lipton chanh</div>
      <div class="price-info">15.000đ</div>
    </div>
    <button onclick="addItem('Lipton chanh', 15000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Lipton chanh mật ong</div>
      <div class="price-info">20.000đ</div>
    </div>
    <button onclick="addItem('Lipton chanh mật ong', 20000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà tắc</div>
      <div class="price-info">12.000đ</div>
    </div>
    <button onclick="addItem('Trà tắc', 12000)">Thêm</button>
  </div>
  <div class="menu-item">
    <div class="menu-item-content">
      <div>Trà tắc xí muội</div>
      <div class="price-info">15.000đ</div>
    </div>
    <button onclick="addItem('Trà tắc xí muội', 15000)">Thêm</button>
  </div>

  <h2>Danh sách Order</h2>
  <table id="order-table">
    <thead><tr><th>Món</th><th>Size</th><th>Giá</th><th>Xóa</th></tr></thead>
    <tbody id="order-body"></tbody>
  </table>
  <div class="total">Tổng: <span id="total">0</span>đ</div>
  <button onclick="printBill()">Xuất Bill</button>

  <div class="bill" id="bill-output"></div>

  <!-- Phần thống kê theo ngày -->
  <div class="stats-section">
    <h2>📊 Thống kê hôm nay</h2>
    <button class="stats-btn" onclick="showDailyStats()">Xem thống kê hôm nay</button>
    <div id="daily-stats" class="stats-grid"></div>
  </div>

  <h2>Lịch sử hóa đơn (Cập nhật theo thời gian thực)</h2>
  <div class="history-controls">
    <button class="export-btn" onclick="exportToExcel()">Xuất Excel Lịch sử</button>
  </div>
  <div class="history" id="history"></div>
</div>

<script>
let orders = [];

function addItem(name, basePrice, el){
  let price = basePrice;
  let size = "";
  
  // Kiểm tra nếu có dropdown size
  if (el) {
    const sizeSelect = el.parentElement.querySelector(".size");
    if (sizeSelect) {
      size = sizeSelect.value;
      // Tính giá dựa trên size được chọn
      if (size === "L") {
        // Tính toán giá cho size L dựa trên giá base (M)
        switch(name) {
          case "Cà phê muối":
            price = 25000;
            break;
          case "Cà phê đá":
            price = 18000;
            break;
          case "Cà phê sữa":
            price = 20000;
            break;
          case "Bạc xỉu":
            price = 22000;
            break;
          case "Bạc xỉu muối":
            price = 26000;
            break;
          case "Cacao sữa":
            price = 22000;
            break;
          case "Cacao muối":
            price = 25000;
            break;
          default:
            price = basePrice;
        }
      }
    }
  }
  
  orders.push({name, size, price});
  renderOrders();
}

function renderOrders(){
  const tbody = document.getElementById("order-body");
  tbody.innerHTML = "";
  orders.forEach((item, index)=>{
    const tr = document.createElement("tr");
    tr.innerHTML = `<td>${item.name}</td><td>${item.size||"-"}</td><td>${item.price.toLocaleString()}đ</td>
                    <td><button class="delete-btn" onclick="removeItem(${index})">X</button></td>`;
    tbody.appendChild(tr);
  });
  const total = orders.reduce((a,b)=>a+b.price,0);
  document.getElementById("total").innerText = total.toLocaleString();
}

function removeItem(i){
  orders.splice(i,1);
  renderOrders();
}

function printBill(){
  if(orders.length===0){ 
    alert("Chưa có món nào!"); 
    return; 
  }
  
  if(!confirm("Bạn có chắc muốn xuất bill và xóa các món đã đặt?")) {
    return;
  }
  
  const now = new Date();
  const dateStr = now.toLocaleString("vi-VN");
  let total = orders.reduce((a,b)=>a+b.price,0);
  let bill = `====================\n     ENJOY COFFEE ☕\n====================\n${dateStr}\n\n`;
  orders.forEach((o,i)=> bill += `${i+1}. ${o.name} ${o.size||""} - ${o.price.toLocaleString()}đ\n`);
  bill += `--------------------\nTổng cộng: ${total.toLocaleString()}đ\n❤️ Cảm ơn quý khách! ❤️`;
  document.getElementById("bill-output").innerText = bill;
  
  // Tạo bản sao của orders trước khi xóa
  const currentOrders = [...orders];
  saveBill(bill, total, currentOrders);
  
  // Xóa danh sách đặt hàng
  orders = [];
  renderOrders();
}

function saveBill(bill, total, currentOrders){
  const now = new Date();
  const billData = {
    billText: bill,
    date: now.toLocaleString("vi-VN"),
    items: currentOrders,
    total: total,
    timestamp: now.getTime()
  };
  
  const list = JSON.parse(localStorage.getItem("bills") || "[]");
  list.push(billData);
  localStorage.setItem("bills", JSON.stringify(list));
  
  // Cập nhật lịch sử ngay lập tức
  loadHistory();
}

function loadHistory(){
  const div = document.getElementById("history");
  const list = JSON.parse(localStorage.getItem("bills") || "[]");
  
  // Sắp xếp theo thời gian mới nhất trước
  list.sort((a, b) => b.timestamp - a.timestamp);
  
  if (list.length === 0) {
    div.innerHTML = "<p>Chưa có hóa đơn nào.</p>";
    return;
  }
  
  div.innerHTML = list.map((b, index) => {
    const totalFormatted = b.total.toLocaleString() + 'đ';
    return `
    <div class="history-item">
      <div class="history-header" onclick="toggleBillDetails(${index})">
        <span><strong>Hóa đơn ${list.length - index}</strong> - ${b.date} - Tổng: ${totalFormatted}</span>
        <button class="toggle-btn">Xem</button>
      </div>
      <div id="bill-details-${index}" class="history-content" style="display: none;">
        <pre>${b.billText}</pre>
        <button class="delete-btn" onclick="deleteBill(${index})">Xóa hóa đơn này</button>
      </div>
    </div>`;
  }).join("");
}

function toggleBillDetails(index) {
  const details = document.getElementById(`bill-details-${index}`);
  if (details.style.display === 'block') {
    details.style.display = 'none';
  } else {
    details.style.display = 'block';
  }
}

function deleteBill(index) {
  if (!confirm("Bạn có chắc muốn xóa hóa đơn này?")) {
    return;
  }
  const list = JSON.parse(localStorage.getItem("bills") || "[]");
  list.splice(index, 1);
  localStorage.setItem("bills", JSON.stringify(list));
  loadHistory();
}

function exportToExcel() {
  const list = JSON.parse(localStorage.getItem("bills") || "[]");
  if (list.length === 0) {
    alert("Không có dữ liệu để xuất!");
    return;
  }
  
  // Tạo dữ liệu CSV
  let csvContent = "STT,Ngày,Tên món,Size,Giá\n";
  
  let stt = 1;
  list.forEach(bill => {
    bill.items.forEach(item => {
      csvContent += `${stt},"${bill.date}","${item.name}","${item.size || ''}","${item.price}"\n`;
      stt++;
    });
  });
  
  // Tạo file và tải về
  const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
  const link = document.createElement("a");
  const url = URL.createObjectURL(blob);
  link.setAttribute("href", url);
  link.setAttribute("download", `lich_su_ban_hang_${new Date().toLocaleDateString('vi-VN')}.csv`);
  link.style.visibility = 'hidden';
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}

// Thống kê theo ngày
function showDailyStats() {
  const list = JSON.parse(localStorage.getItem("bills") || "[]");
  const today = new Date();
  const todayString = today.toLocaleDateString('vi-VN');
  
  // Lọc hóa đơn trong ngày hôm nay
  const todayBills = list.filter(bill => {
    const billDate = new Date(bill.timestamp).toLocaleDateString('vi-VN');
    return billDate === todayString;
  });
  
  if (todayBills.length === 0) {
    document.getElementById('daily-stats').innerHTML = '<p>Hôm nay chưa có hóa đơn nào.</p>';
    return;
  }
  
  // Tính toán thống kê
  let totalRevenue = 0;
  let totalOrders = todayBills.length;
  let productCount = {};
  let totalItems = 0;
  
  todayBills.forEach(bill => {
    totalRevenue += bill.total;
    bill.items.forEach(item => {
      totalItems++;
      const key = item.name + (item.size ? ` (${item.size})` : '');
      productCount[key] = (productCount[key] || 0) + 1;
    });
  });
  
  // Tìm sản phẩm bán chạy nhất
  let bestSeller = { name: '', count: 0 };
  Object.entries(productCount).forEach(([product, count]) => {
    if (count > bestSeller.count) {
      bestSeller = { name: product, count: count };
    }
  });
  
  // Hiển thị thống kê
  const statsContainer = document.getElementById('daily-stats');
  statsContainer.innerHTML = `
    <div class="stat-card">
      <div class="stat-value">${totalOrders}</div>
      <div class="stat-label">Hóa đơn</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">${totalRevenue.toLocaleString()}đ</div>
      <div class="stat-label">Doanh thu</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">${totalItems}</div>
      <div class="stat-label">Số món đã bán</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">${bestSeller.count}</div>
      <div class="stat-label">${bestSeller.name || 'Chưa có'}</div>
    </div>
  `;
  
  // Thêm chi tiết sản phẩm bán chạy
  let productDetails = '<div style="grid-column: 1 / -1; margin-top: 15px;"><h3>Chi tiết sản phẩm bán chạy:</h3><ul>';
  Object.entries(productCount)
    .sort((a, b) => b[1] - a[1])
    .forEach(([product, count]) => {
      productDetails += `<li>${product}: ${count} lượt</li>`;
    });
  productDetails += '</ul></div>';
  
  statsContainer.innerHTML += productDetails;
}

// Tải lịch sử khi trang được mở
loadHistory();

// Thêm sự kiện lắng nghe thay đổi localStorage để cập nhật thời gian thực
window.addEventListener('storage', function(e) {
  if (e.key === 'bills') {
    loadHistory();
  }
});
</script>
</body>
</html>

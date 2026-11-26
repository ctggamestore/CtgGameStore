## Hi there 👋

<!--
**ctggamestore/CtgGameStore** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
--><!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Rajia Game Store — Gaming Top-Up & Digital Shop</title>
  <style>
    :root {
      --bg: #0b0f19;
      --card: #131a2a;
      --card-2: #1a2338;
      --text: #f1f5f9;
      --muted: #94a3b8;
      --primary: #38bdf8;
      --primary-2: #0284c7;
      --success: #22c55e;
      --warning: #f59e0b;
      --danger: #ef4444;
      --border: rgba(148, 163, 184, 0.16);
      --radius: 14px;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
      background: linear-gradient(180deg, #090d16 0%, var(--bg) 100%);
      color: var(--text);
      line-height: 1.5;
      min-height: 100vh;
    }

    .container { max-width: 1120px; margin: 0 auto; padding: 20px 16px 64px; }

    /* Header */
    header {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 16px 20px;
      margin-bottom: 22px;
    }
    .brand h1 { font-size: 1.35rem; color: var(--primary); }
    .brand p { font-size: 0.85rem; color: var(--muted); }
    .header-actions { display: flex; flex-wrap: wrap; gap: 10px; align-items: center; }

    /* Buttons & Inputs */
    button, .btn {
      cursor: pointer;
      border: 1px solid transparent;
      border-radius: 10px;
      padding: 9px 14px;
      font-size: 0.9rem;
      font-weight: 600;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      transition: 0.15s ease;
    }
    .btn-primary { background: var(--primary); color: #06131f; }
    .btn-primary:hover { background: var(--primary-2); color: #fff; }
    .btn-outline {
      background: transparent;
      color: var(--text);
      border-color: var(--border);
    }
    .btn-outline:hover { background: var(--card-2); }
    .btn-success { background: var(--success); color: #052e16; }
    .btn-danger { background: var(--danger); color: #fff; }
    .btn-sm { padding: 6px 10px; font-size: 0.8rem; }

    input, select, textarea {
      width: 100%;
      background: var(--card-2);
      color: var(--text);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 10px 12px;
      font-size: 0.92rem;
      outline: none;
    }
    input:focus, select:focus, textarea:focus { border-color: var(--primary); }
    label { display: block; font-size: 0.85rem; color: var(--muted); margin-bottom: 5px; }

    /* Layout */
    .grid { display: grid; gap: 16px; }
    .products-grid { grid-template-columns: repeat(auto-fill, minmax(230px, 1fr)); }
    .two-col { grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); }

    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 18px;
    }
    .card h2, .card h3 { margin-bottom: 12px; font-size: 1.08rem; }

    .product-card {
      background: var(--card-2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 12px;
    }
    .product-card.selected { border-color: var(--primary); box-shadow: 0 0 0 1px var(--primary); }
    .tag {
      display: inline-block;
      font-size: 0.75rem;
      padding: 3px 8px;
      border-radius: 999px;
      background: rgba(56, 189, 248, 0.14);
      color: var(--primary);
      margin-bottom: 6px;
    }
    .price { font-size: 1.2rem; font-weight: 700; color: #4ade80; }

    /* Status Badges */
    .badge {
      padding: 4px 10px;
      border-radius: 999px;
      font-size: 0.78rem;
      font-weight: 700;
      display: inline-block;
    }
    .badge-pending { background: rgba(245, 158, 11, 0.18); color: var(--warning); }
    .badge-complete { background: rgba(34, 197, 94, 0.18); color: var(--success); }
    .badge-cancelled { background: rgba(239, 68, 68, 0.18); color: var(--danger); }

    /* Table */
    .table-wrap { overflow-x: auto; }
    table { width: 100%; border-collapse: collapse; font-size: 0.88rem; }
    th, td { padding: 10px 8px; border-bottom: 1px solid var(--border); text-align: left; }
    th { color: var(--muted); font-weight: 600; }

    .hidden { display: none !important; }
    .mt-2 { margin-top: 10px; }
    .mt-3 { margin-top: 16px; }
    .msg {
      padding: 10px 14px;
      border-radius: 10px;
      margin-top: 12px;
      font-size: 0.9rem;
      background: rgba(34, 197, 94, 0.15);
      border: 1px solid rgba(34, 197, 94, 0.4);
      color: #86efac;
    }
    .msg.error {
      background: rgba(239, 68, 68, 0.15);
      border-color: rgba(239, 68, 68, 0.4);
      color: #fca5a5;
    }

    /* Modal */
    .modal-backdrop {
      position: fixed; inset: 0;
      background: rgba(0, 0, 0, 0.7);
      display: flex; align-items: center; justify-content: center;
      padding: 16px; z-index: 50;
    }
    .modal {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 22px;
      width: 100%; max-width: 380px;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Top Header -->
    <header>
      <div class="brand">
        <h1 id="storeTitle">Rajia Game Store</h1>
        <p id="storeSubtitle">দ্রুত ও নিরাপদ গেমিং টপ-আপ এবং ডিজিটাল সার্ভিস</p>
      </div>
      <div class="header-actions">
        <a id="telegramLink" href="https://t.me/telegram" target="_blank" rel="noopener" class="btn btn-outline">
          টেলিগ্রাম সাপোর্ট
        </a>
        <button id="adminToggleBtn" class="btn btn-outline" onclick="handleAdminButton()">
          অ্যাডমিন প্যানেল
        </button>
      </div>
    </header>

    <!-- Customer View -->
    <section id="customerView">
      <div class="card">
        <h2>১. প্যাক বা প্রোডাক্ট নির্বাচন করুন</h2>
        <div id="productsGrid" class="grid products-grid mt-2"></div>
      </div>

      <div class="grid two-col mt-3">
        <!-- Order Form -->
        <div class="card">
          <h2>২. অর্ডার সাবমিট করুন</h2>
          <form id="orderForm" onsubmit="submitOrder(event)">
            <div class="mt-2">
              <label>নির্বাচিত প্যাক</label>
              <input type="text" id="selectedProductDisplay" readonly required />
            </div>
            <div class="mt-2">
              <label>Player UID / গেম আইডি</label>
              <input type="text" id="playerUid" placeholder="যেমন: 1234567890" required />
            </div>
            <div class="mt-2">
              <label>আপনার নম্বর বা TrxID (পেমেন্ট রেফারেন্স)</label>
              <input type="text" id="paymentRef" placeholder="bKash/Nagad নম্বর বা TrxID" required />
            </div>
            <button type="submit" class="btn btn-primary mt-3" style="width:100%">অর্ডার কনফার্ম করুন</button>
          </form>
          <div id="orderFeedback"></div>
        </div>

        <!-- UID / Order Search -->
        <div class="card">
          <h2>৩. Player UID বা অর্ডার আইডি দিয়ে স্ট্যাটাস চেক করুন</h2>
          <label>Player UID অথবা Order ID লিখুন</label>
          <div style="display:flex; gap:8px;">
            <input type="text" id="searchQuery" placeholder="UID বা ORD-..." />
            <button class="btn btn-primary" onclick="searchOrders()">খুঁজুন</button>
          </div>
          <div id="searchResults" class="mt-3"></div>
        </div>
      </div>
    </section>

    <!-- Admin Panel View -->
    <section id="adminView" class="hidden">
      <div class="card">
        <div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:center; gap:10px;">
          <h2>অ্যাডমিন ড্যাশবোর্ড</h2>
          <div style="display:flex; flex-wrap:wrap; gap:8px;">
            <button class="btn btn-outline btn-sm" onclick="exportBackupJSON()">JSON ব্যাকআপ ডাউনলোড</button>
            <label class="btn btn-outline btn-sm" style="margin:0;">
              JSON রিস্টোর
              <input type="file" accept=".json" style="display:none;" onchange="importBackupJSON(event)" />
            </label>
            <button class="btn btn-danger btn-sm" onclick="logoutAdmin()">লগআউট</button>
          </div>
        </div>
      </div>

      <!-- Manage Orders -->
      <div class="card mt-3">
        <h3>অর্ডার তালিকা (Pending → Complete)</h3>
        <div class="table-wrap mt-2">
          <table>
            <thead>
              <tr>
                <th>Order ID</th>
                <th>UID</th>
                <th>প্যাক</th>
                <th>মূল্য</th>
                <th>পেমেন্ট</th>
                <th>স্ট্যাটাস</th>
                <th>অ্যাকশন</th>
              </tr>
            </thead>
            <tbody id="adminOrdersBody"></tbody>
          </table>
        </div>
      </div>

      <div class="grid two-col mt-3">
        <!-- Add / Edit Product -->
        <div class="card">
          <h3>নতুন প্যাক বা প্রোডাক্ট যোগ করুন</h3>
          <form id="productForm" onsubmit="addProduct(event)">
            <div class="mt-2">
              <label>ক্যাটাগরি / গেম নাম</label>
              <input type="text" id="prodCategory" placeholder="যেমন: Free Fire" required />
            </div>
            <div class="mt-2">
              <label>প্যাকের নাম</label>
              <input type="text" id="prodName" placeholder="যেমন: 115 Diamonds" required />
            </div>
            <div class="mt-2">
              <label>মূল্য (৳)</label>
              <input type="number" id="prodPrice" min="1" placeholder="যেমন: 85" required />
            </div>
            <button type="submit" class="btn btn-primary mt-3" style="width:100%">প্রোডাক্ট যুক্ত করুন</button>
          </form>

          <h4 class="mt-3" style="font-size:0.95rem; color:var(--muted);">বিদ্যমান প্রোডাক্ট</h4>
          <div id="adminProductsList" class="mt-2"></div>
        </div>

        <!-- Store Settings -->
        <div class="card">
          <h3>স্টোর ও সিকিউরিটি সেটিংস</h3>
          <form id="settingsForm" onsubmit="saveSettings(event)">
            <div class="mt-2">
              <label>স্টোরের নাম</label>
              <input type="text" id="setStoreName" required />
            </div>
            <div class="mt-2">
              <label>সাবটাইটেল</label>
              <input type="text" id="setSubtitle" required />
            </div>
            <div class="mt-2">
              <label>টেলিগ্রাম সাপোর্ট লিংক</label>
              <input type="url" id="setTelegram" required />
            </div>
            <div class="mt-2">
              <label>নতুন অ্যাডমিন পিন/পাসওয়ার্ড</label>
              <input type="text" id="setAdminPin" required />
            </div>
            <button type="submit" class="btn btn-success mt-3" style="width:100%">সেটিংস সংরক্ষণ করুন</button>
          </form>
          <div id="settingsFeedback"></div>
        </div>
      </div>
    </section>
  </div>

  <!-- Admin Login Modal -->
  <div id="loginModal" class="modal-backdrop hidden">
    <div class="modal">
      <h3>অ্যাডমিন লগইন</h3>
      <p style="font-size:0.85rem; color:var(--muted); margin-top:4px;">ডিফল্ট পিন: <strong>1234</strong> (পরে সেটিংস থেকে বদলাতে পারবেন)</p>
      <div class="mt-3">
        <label>অ্যাডমিন পিন/পাসওয়ার্ড</label>
        <input type="password" id="adminPinInput" placeholder="পিন লিখুন" />
      </div>
      <div id="loginError" class="msg error hidden">ভুল পিন! আবার চেষ্টা করুন।</div>
      <div style="display:flex; justify-content:flex-end; gap:8px; margin-top:16px;">
        <button class="btn btn-outline" onclick="closeLoginModal()">বাতিল</button>
        <button class="btn btn-primary" onclick="verifyAdminLogin()">লগইন</button>
      </div>
    </div>
  </div>

  <script>
    const STORAGE_KEY = "rajia_game_store_data_v1";

    const defaultData = {
      settings: {
        storeName: "Rajia Game Store",
        subtitle: "দ্রুত ও নিরাপদ গেমিং টপ-আপ এবং ডিজিটাল সার্ভিস",
        telegramUrl: "https://t.me/telegram",
        adminPin: "1234"
      },
      products: [
        { id: "p1", category: "Free Fire", name: "115 Diamonds", price: 85 },
        { id: "p2", category: "Free Fire", name: "240 Diamonds", price: 170 },
        { id: "p3", category: "Free Fire", name: "Weekly Membership", price: 155 },
        { id: "p4", category: "PUBG / BGMI", name: "60 UC", price: 95 }
      ],
      orders: []
    };

    let state = loadState();
    let selectedProductId = state.products[0]?.id || null;
    let isAdminLoggedIn = false;

    function loadState() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        if (!raw) return structuredClone(defaultData);
        const parsed = JSON.parse(raw);
        return {
          settings: { ...defaultData.settings, ...(parsed.settings || {}) },
          products: Array.isArray(parsed.products) ? parsed.products : structuredClone(defaultData.products),
          orders: Array.isArray(parsed.orders) ? parsed.orders : []
        };
      } catch {
        return structuredClone(defaultData);
      }
    }

    function saveState() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
    }

    function escapeHTML(str = "") {
      return String(str).replace(/[&<>"']/g, m => ({
        "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;"
      }[m]));
    }

    function renderAll() {
      // Header & settings
      document.title = `${state.settings.storeName} — Gaming Top-Up & Digital Shop`;
      document.getElementById("storeTitle").textContent = state.settings.storeName;
      document.getElementById("storeSubtitle").textContent = state.settings.subtitle;
      document.getElementById("telegramLink").href = state.settings.telegramUrl;

      renderProducts();
      updateSelectedProductInput();

      if (isAdminLoggedIn) {
        document.getElementById("customerView").classList.add("hidden");
        document.getElementById("adminView").classList.remove("hidden");
        document.getElementById("adminToggleBtn").textContent = "স্টোর দেখুন";
        renderAdminDashboard();
      } else {
        document.getElementById("customerView").classList.remove("hidden");
        document.getElementById("adminView").classList.add("hidden");
        document.getElementById("adminToggleBtn").textContent = "অ্যাডমিন প্যানেল";
      }
    }

    function renderProducts() {
      const grid = document.getElementById("productsGrid");
      if (!state.products.length) {
        grid.innerHTML = `<p style="color:var(--muted);">কোনো প্রোডাক্ট যুক্ত করা হয়নি।</p>`;
        return;
      }
      grid.innerHTML = state.products.map(p => `
        <div class="product-card ${p.id === selectedProductId ? "selected" : ""}" onclick="selectProduct('${p.id}')">
          <div>
            <span class="tag">${escapeHTML(p.category)}</span>
            <h3>${escapeHTML(p.name)}</h3>
          </div>
          <div style="display:flex; justify-content:space-between; align-items:center;">
            <span class="price">৳${Number(p.price)}</span>
            <button type="button" class="btn btn-sm ${p.id === selectedProductId ? "btn-primary" : "btn-outline"}">
              ${p.id === selectedProductId ? "নির্বাচিত" : "নির্বাচন"}
            </button>
          </div>
        </div>
      `).join("");
    }

    function selectProduct(id) {
      selectedProductId = id;
      renderProducts();
      updateSelectedProductInput();
    }

    function updateSelectedProductInput() {
      const prod = state.products.find(p => p.id === selectedProductId) || state.products[0];
      const input = document.getElementById("selectedProductDisplay");
      if (prod) {
        selectedProductId = prod.id;
        input.value = `${prod.category} — ${prod.name} (৳${prod.price})`;
      } else {
        input.value = "";
      }
    }

    function submitOrder(e) {
      e.preventDefault();
      const prod = state.products.find(p => p.id === selectedProductId);
      const uid = document.getElementById("playerUid").value.trim();
      const paymentRef = document.getElementById("paymentRef").value.trim();
      const feedback = document.getElementById("orderFeedback");

      if (!prod) {
        feedback.innerHTML = `<div class="msg error">প্রথমে একটি প্যাক নির্বাচন করুন।</div>`;
        return;
      }

      const order = {
        id: "ORD-" + Math.floor(100000 + Math.random() * 900000),
        uid,
        productName: `${prod.category} - ${prod.name}`,
        price: Number(prod.price),
        paymentRef,
        status: "Pending",
        createdAt: new Date().toLocaleString("bn-BD")
      };

      state.orders.unshift(order);
      saveState();

      document.getElementById("orderForm").reset();
      updateSelectedProductInput();
      feedback.innerHTML = `
        <div class="msg">
          অর্ডার সফলভাবে জমা হয়েছে! আপনার Order ID: <strong>${escapeHTML(order.id)}</strong> (স্ট্যাটাস: Pending)। UID বা Order ID দিয়ে স্ট্যাটাস চেক করতে পারবেন।
        </div>
      `;
    }

    function searchOrders() {
      const q = document.getElementById("searchQuery").value.trim().toLowerCase();
      const box = document.getElementById("searchResults");
      if (!q) {
        box.innerHTML = `<p style="color:var(--muted); font-size:0.88rem;">অনুগ্রহ করে Player UID অথবা Order ID লিখুন।</p>`;
        return;
      }

      const matches = state.orders.filter(o =>
        o.uid.toLowerCase().includes(q) || o.id.toLowerCase().includes(q)
      );

      if (!matches.length) {
        box.innerHTML = `<div class="msg error">এই UID বা Order ID দিয়ে কোনো অর্ডার পাওয়া যায়নি।</div>`;
        return;
      }

      box.innerHTML = matches.map(o => `
        <div class="product-card mt-2">
          <div style="display:flex; justify-content:space-between; align-items:center; gap:8px;">
            <strong>${escapeHTML(o.id)}</strong>
            ${renderStatusBadge(o.status)}
          </div>
          <div style="font-size:0.88rem; color:var(--muted);">
            UID: <strong style="color:var(--text)">${escapeHTML(o.uid)}</strong> • ${escapeHTML(o.productName)} • ৳${o.price}
          </div>
          <div style="font-size:0.78rem; color:var(--muted);">${escapeHTML(o.createdAt)}</div>
        </div>
      `).join("");
    }

    function renderStatusBadge(status) {
      if (status === "Complete") return `<span class="badge badge-complete">Complete</span>`;
      if (status === "Cancelled") return `<span class="badge badge-cancelled">Cancelled</span>`;
      return `<span class="badge badge-pending">Pending</span>`;
    }

    /* Admin Auth */
    function handleAdminButton() {
      if (isAdminLoggedIn) {
        isAdminLoggedIn = false;
        renderAll();
      } else {
        document.getElementById("adminPinInput").value = "";
        document.getElementById("loginError").classList.add("hidden");
        document.getElementById("loginModal").classList.remove("hidden");
      }
    }

    function closeLoginModal() {
      document.getElementById("loginModal").classList.add("hidden");
    }

    function verifyAdminLogin() {
      const pin = document.getElementById("adminPinInput").value.trim();
      if (pin === state.settings.adminPin) {
        isAdminLoggedIn = true;
        closeLoginModal();
        renderAll();
      } else {
        document.getElementById("loginError").classList.remove("hidden");
      }
    }

    function logoutAdmin() {
      isAdminLoggedIn = false;
      renderAll();
    }

    /* Admin Dashboard */
    function renderAdminDashboard() {
      const tbody = document.getElementById("adminOrdersBody");
      if (!state.orders.length) {
        tbody.innerHTML = `<tr><td colspan="7" style="color:var(--muted);">এখনো কোনো অর্ডার নেই।</td></tr>`;
      } else {
        tbody.innerHTML = state.orders.map(o => `
          <tr>
            <td><strong>${escapeHTML(o.id)}</strong></td>
            <td>${escapeHTML(o.uid)}</td>
            <td>${escapeHTML(o.productName)}</td>
            <td>৳${o.price}</td>
            <td>${escapeHTML(o.paymentRef)}</td>
            <td>${renderStatusBadge(o.status)}</td>
            <td style="white-space:nowrap;">
              <button class="btn btn-success btn-sm" onclick="updateOrderStatus('${o.id}', 'Complete')">Complete</button>
              <button class="btn btn-danger btn-sm" onclick="updateOrderStatus('${o.id}', 'Cancelled')">Cancel</button>
            </td>
          </tr>
        `).join("");
      }

      const prodList = document.getElementById("adminProductsList");
      prodList.innerHTML = state.products.map(p => `
        <div style="display:flex; justify-content:space-between; align-items:center; padding:8px 0; border-bottom:1px solid var(--border);">
          <span><strong>${escapeHTML(p.name)}</strong> (${escapeHTML(p.category)}) — ৳${p.price}</span>
          <button class="btn btn-danger btn-sm" onclick="deleteProduct('${p.id}')">মুছুন</button>
        </div>
      `).join("");

      document.getElementById("setStoreName").value = state.settings.storeName;
      document.getElementById("setSubtitle").value = state.settings.subtitle;
      document.getElementById("setTelegram").value = state.settings.telegramUrl;
      document.getElementById("setAdminPin").value = state.settings.adminPin;
    }

    function updateOrderStatus(orderId, status) {
      const order = state.orders.find(o => o.id === orderId);
      if (!order) return;
      order.status = status;
      saveState();
      renderAdminDashboard();
    }

    function addProduct(e) {
      e.preventDefault();
      const category = document.getElementById("prodCategory").value.trim();
      const name = document.getElementById("prodName").value.trim();
      const price = Number(document.getElementById("prodPrice").value);
      if (!category || !name || !price) return;

      const newProd = { id: "p_" + Date.now(), category, name, price };
      state.products.push(newProd);
      selectedProductId = newProd.id;
      saveState();
      document.getElementById("productForm").reset();
      renderAll();
    }

    function deleteProduct(id) {
      state.products = state.products.filter(p => p.id !== id);
      if (selectedProductId === id) {
        selectedProductId = state.products[0]?.id || null;
      }
      saveState();
      renderAll();
    }

    function saveSettings(e) {
      e.preventDefault();
      state.settings.storeName = document.getElementById("setStoreName").value.trim();
      state.settings.subtitle = document.getElementById("setSubtitle").value.trim();
      state.settings.telegramUrl = document.getElementById("setTelegram").value.trim();
      state.settings.adminPin = document.getElementById("setAdminPin").value.trim() || "1234";
      saveState();
      renderAll();
      document.getElementById("settingsFeedback").innerHTML = `<div class="msg">সেটিংস সফলভাবে সংরক্ষিত হয়েছে!</div>`;
    }

    /* JSON Backup & Restore */
    function exportBackupJSON() {
      const blob = new Blob([JSON.stringify(state, null, 2)], { type: "application/json" });
      const url = URL.createObjectURL(blob);
      const a = document.createElement("a");
      a.href = url;
      a.download = `rajia-game-store-backup-${new Date().toISOString().slice(0, 10)}.json`;
      a.click();
      URL.revokeObjectURL(url);
    }

    function importBackupJSON(event) {
      const file = event.target.files?.[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = () => {
        try {
          const imported = JSON.parse(reader.result);
          if (!imported || !Array.isArray(imported.products) || !Array.isArray(imported.orders)) {
            alert("সঠিক ব্যাকআপ JSON ফাইল নয়।");
            return;
          }
          state = {
            settings: { ...defaultData.settings, ...(imported.settings || {}) },
            products: imported.products,
            orders: imported.orders
          };
          selectedProductId = state.products[0]?.id || null;
          saveState();
          renderAll();
          alert("JSON ব্যাকআপ সফলভাবে রিস্টোর হয়েছে!");
        } catch {
          alert("JSON ফাইল পড়তে সমস্যা হয়েছে।");
        }
      };
      reader.readAsText(file);
      event.target.value = "";
    }

    renderAll();
  </script>
</body>
</html>

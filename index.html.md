#   
<!DOCTYPE html>  
<html lang="ar" dir="rtl">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>متجر عُمراء | Omara Store</title>  
<link rel="preconnect" href="https://fonts.googleapis.com">  
<link href="https://fonts.googleapis.com/css2?family=Aref+Ruqaa:wght@400;700&family=Markazi+Text:wght@400;600;700&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">  
<style>  
  :root{  
    --cream:#F8EACB;  
    --cream-deep:#F1DDA6;  
    --card:#FFFBF0;  
    --ink:#20301C;  
    --ink-soft:#3B4A34;  
    --gold:#A9793C;  
    --gold-soft:#C9A96E;  
    --line:rgba(32,48,28,.16);  
    --danger:#9B3A2E;  
    --ok:#4C6B3E;  
    --shadow:0 10px 30px rgba(32,48,28,.10);  
  }  
  *{box-sizing:border-box;}  
  html,body{margin:0;padding:0;}  
  body{  
    background:  
      radial-gradient(1200px 500px at 50% -10%, var(--cream-deep), transparent 60%),  
      var(--cream);  
    color:var(--ink);  
    font-family:'Tajawal',sans-serif;  
    min-height:100vh;  
  }  
  h1,h2,h3,.display{font-family:'Aref Ruqaa',serif;}  
  .eyebrow{font-family:'Markazi Text',serif; letter-spacing:.04em;}  
  a{color:inherit;text-decoration:none;}  
  button{font-family:inherit;cursor:pointer;}  
  ::selection{background:var(--gold-soft);color:var(--ink);}  
  
  /* ---------- decorative sunrise divider (echoes the logo) ---------- */  
  .sunrise{width:100%; display:flex; justify-content:center; margin:6px 0;}  
  .sunrise svg{width:260px; max-width:70vw; opacity:.75;}  
  
  /* ---------- top bar ---------- */  
  header.topbar{  
    position:sticky; top:0; z-index:40;  
    background:rgba(248,234,203,.88); backdrop-filter:blur(8px);  
    border-bottom:1px solid var(--line);  
  }  
  .topbar-inner{  
    max-width:1180px; margin:0 auto; padding:14px 22px;  
    display:flex; align-items:center; justify-content:space-between; gap:14px;  
  }  
  .brand{display:flex; align-items:center; gap:10px;}  
  .brand-mark{font-family:'Aref Ruqaa',serif; font-size:30px; font-weight:700; color:var(--ink); line-height:1;}  
  .brand-sub{font-size:11px; color:var(--ink-soft); letter-spacing:.15em;}  
  nav.pillnav{display:flex; gap:6px; background:var(--card); padding:6px; border-radius:999px; box-shadow:var(--shadow); border:1px solid var(--line);}  
  nav.pillnav button{  
    background:transparent;border:none;padding:9px 18px;border-radius:999px;font-size:14px;color:var(--ink-soft);font-weight:700;transition:.2s;  
  }  
  nav.pillnav button.active,nav.pillnav button:hover{background:var(--ink); color:var(--cream);}  
  .cart-btn{  
    position:relative; background:var(--ink); color:var(--cream); border:none; border-radius:999px;  
    padding:11px 20px; font-weight:700; font-size:14px; display:flex; align-items:center; gap:8px; box-shadow:var(--shadow);  
  }  
  .cart-count{  
    background:var(--gold); color:#fff; font-size:11px; min-width:19px; height:19px; border-radius:999px;  
    display:inline-flex; align-items:center; justify-content:center; padding:0 4px;  
  }  
  
  /* ---------- hero ---------- */  
  .hero{max-width:900px; margin:50px auto 10px; text-align:center; padding:0 20px;}  
  .hero .eyebrow{font-size:19px; color:var(--gold); margin-bottom:6px;}  
  .hero h1{font-size:64px; margin:4px 0 10px; color:var(--ink);}  
  .hero p{font-size:16px; color:var(--ink-soft); max-width:520px; margin:0 auto; line-height:1.9;}  
  .hero .wa{  
    display:inline-flex; align-items:center; gap:8px; margin-top:22px; background:var(--ink); color:var(--cream);  
    padding:12px 26px; border-radius:999px; font-weight:700; font-size:14px; box-shadow:var(--shadow);  
  }  
  
  /* ---------- section shell ---------- */  
  .section{max-width:1180px; margin:0 auto; padding:36px 22px 70px;}  
  .section-head{display:flex; align-items:baseline; justify-content:space-between; margin-bottom:22px; flex-wrap:wrap; gap:10px;}  
  .section-head h2{font-size:34px; margin:0;}  
  .cats{display:flex; gap:8px; flex-wrap:wrap;}  
  .cats button{  
    background:var(--card); border:1px solid var(--line); padding:8px 16px; border-radius:999px; font-size:13px; font-weight:700; color:var(--ink-soft);  
  }  
  .cats button.active{background:var(--ink); color:var(--cream); border-color:var(--ink);}  
  
  /* ---------- product grid ---------- */  
  .grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(230px,1fr)); gap:22px;}  
  .card{  
    background:var(--card); border:1px solid var(--line); border-radius:20px; overflow:hidden; box-shadow:var(--shadow);  
    display:flex; flex-direction:column; transition:transform .25s ease;  
  }  
  .card:hover{transform:translateY(-4px);}  
  .card .imgwrap{aspect-ratio:1/1; background:linear-gradient(160deg,var(--cream-deep),var(--cream)); position:relative; overflow:hidden;}  
  .card .imgwrap img{width:100%; height:100%; object-fit:cover;}  
  .badge-discount{  
    position:absolute; top:10px; left:10px; background:var(--danger); color:#fff; font-size:12px; font-weight:700;  
    padding:4px 10px; border-radius:999px;  
  }  
  .badge-out{position:absolute; inset:0; background:rgba(32,48,28,.55); color:#fff; display:flex; align-items:center; justify-content:center; font-weight:700;}  
  .card .body{padding:16px; display:flex; flex-direction:column; gap:8px; flex:1;}  
  .card .name{font-family:'Aref Ruqaa',serif; font-size:22px; margin:0;}  
  .card .desc{font-size:12.5px; color:var(--ink-soft); line-height:1.7; min-height:34px;}  
  .swatches{display:flex; gap:6px; flex-wrap:wrap;}  
  .swatch{  
    font-size:11px; border:1px solid var(--line); padding:3px 9px; border-radius:999px; color:var(--ink-soft); background:#fff;  
  }  
  .swatch.sel{background:var(--ink); color:var(--cream); border-color:var(--ink);}  
  .price-row{display:flex; align-items:center; gap:8px; margin-top:auto; padding-top:6px;}  
  .price{font-weight:900; font-size:18px; color:var(--ink);}  
  .price-old{font-size:13px; color:var(--ink-soft); text-decoration:line-through; opacity:.7;}  
  .addbtn{  
    margin-top:6px; width:100%; background:var(--ink); color:var(--cream); border:none; padding:11px; border-radius:12px; font-weight:700; font-size:14px;  
  }  
  .addbtn:disabled{background:#c8c1ab; color:#7d7862;}  
  .empty{text-align:center; padding:60px 20px; color:var(--ink-soft);}  
  
  /* ---------- footer ---------- */  
  footer{border-top:1px solid var(--line); padding:36px 22px; text-align:center; color:var(--ink-soft); font-size:13px;}  
  footer .admin-link{display:block; margin-top:10px; font-size:11px; opacity:.55;}  
  
  /* ---------- drawer / modal shells ---------- */  
  .scrim{position:fixed; inset:0; background:rgba(20,26,16,.45); z-index:80; opacity:0; pointer-events:none; transition:.25s;}  
  .scrim.show{opacity:1; pointer-events:auto;}  
  .drawer{  
    position:fixed; top:0; bottom:0; left:0; width:min(420px,92vw); background:var(--cream); z-index:90;  
    transform:translateX(-100%); transition:.3s ease; box-shadow:20px 0 40px rgba(0,0,0,.15); display:flex; flex-direction:column;  
  }  
  .drawer.show{transform:translateX(0);}  
  .drawer-head{padding:20px; border-bottom:1px solid var(--line); display:flex; justify-content:space-between; align-items:center;}  
  .drawer-head h3{margin:0; font-size:24px;}  
  .x{background:none;border:none;font-size:22px;color:var(--ink-soft);}  
  .drawer-body{flex:1; overflow-y:auto; padding:16px 20px;}  
  .cart-item{display:flex; gap:12px; padding:12px 0; border-bottom:1px solid var(--line);}  
  .cart-item img{width:64px; height:64px; border-radius:10px; object-fit:cover; background:var(--cream-deep);}  
  .cart-item .info{flex:1;}  
  .cart-item .info .nm{font-weight:700; font-size:14px;}  
  .cart-item .info .meta{font-size:11.5px; color:var(--ink-soft);}  
  .qty{display:flex; align-items:center; gap:8px; margin-top:6px;}  
  .qty button{width:24px; height:24px; border-radius:8px; border:1px solid var(--line); background:#fff;}  
  .drawer-foot{padding:18px 20px; border-top:1px solid var(--line);}  
  .total-row{display:flex; justify-content:space-between; font-weight:900; font-size:18px; margin-bottom:12px;}  
  .btn{background:var(--ink); color:var(--cream); border:none; padding:13px; border-radius:12px; font-weight:700; font-size:15px; width:100%;}  
  .btn.secondary{background:transparent; border:1px solid var(--ink); color:var(--ink);}  
  .btn.danger{background:var(--danger); color:#fff;}  
  .btn.small{padding:8px 14px; font-size:13px; width:auto;}  
  
  .modal{  
    position:fixed; top:50%; left:50%; transform:translate(-50%,-46%); width:min(520px,92vw); max-height:88vh; overflow-y:auto;  
    background:var(--card); border-radius:20px; z-index:95; padding:26px; box-shadow:var(--shadow); opacity:0; pointer-events:none; transition:.25s;  
  }  
  .modal.show{opacity:1; pointer-events:auto; transform:translate(-50%,-50%);}  
  .modal h3{margin:0 0 16px; font-size:26px;}  
  label{display:block; font-size:12.5px; color:var(--ink-soft); margin:12px 0 5px; font-weight:700;}  
  input[type=text],input[type=tel],input[type=number],input[type=password],textarea,select{  
    width:100%; padding:10px 12px; border:1px solid var(--line); border-radius:10px; background:#fff; font-family:inherit; font-size:14px; color:var(--ink);  
  }  
  textarea{resize:vertical; min-height:70px;}  
  .radiorow{display:flex; gap:10px; margin-top:6px;}  
  .radiocard{flex:1; border:1px solid var(--line); border-radius:12px; padding:10px; font-size:13px; text-align:center; cursor:pointer;}  
  .radiocard.sel{border-color:var(--ink); background:var(--cream);}  
  .pay-details{background:var(--cream); border:1px dashed var(--gold); border-radius:12px; padding:12px; font-size:13px; margin-top:10px; line-height:1.9; white-space:pre-line;}  
  
  /* ---------- admin ---------- */  
  #adminView{display:none;}  
  .adminbar{max-width:1180px; margin:0 auto; padding:16px 22px 0; display:flex; gap:8px; flex-wrap:wrap;}  
  .adminbar button{background:var(--card); border:1px solid var(--line); padding:9px 16px; border-radius:999px; font-size:13px; font-weight:700; color:var(--ink-soft);}  
  .adminbar button.active{background:var(--ink); color:var(--cream);}  
  .adminbar .spacer{flex:1;}  
  .admin-panel{max-width:1180px; margin:0 auto; padding:20px 22px 70px;}  
  table{width:100%; border-collapse:collapse; background:var(--card); border-radius:14px; overflow:hidden; box-shadow:var(--shadow);}  
  th,td{padding:10px 12px; text-align:right; font-size:13px; border-bottom:1px solid var(--line);}  
  th{background:var(--cream-deep); font-weight:800;}  
  tr:last-child td{border-bottom:none;}  
  .tbl-img{width:42px; height:42px; object-fit:cover; border-radius:8px;}  
  .form-card{background:var(--card); border:1px solid var(--line); border-radius:16px; padding:20px; box-shadow:var(--shadow); margin-bottom:26px;}  
  .row2{display:grid; grid-template-columns:1fr 1fr; gap:12px;}  
  .thumbstrip{display:flex; gap:8px; flex-wrap:wrap; margin-top:8px;}  
  .thumbstrip .th{position:relative;}  
  .thumbstrip img{width:56px; height:56px; object-fit:cover; border-radius:8px; border:1px solid var(--line);}  
  .thumbstrip .rm{position:absolute; top:-6px; left:-6px; background:var(--danger); color:#fff; border-radius:999px; width:18px; height:18px; font-size:11px; border:none; line-height:1;}  
  .status-pill{font-size:11px; padding:3px 10px; border-radius:999px; font-weight:700;}  
  .status-pending{background:#F3E3B8; color:#7A5B10;}  
  .status-confirmed{background:#D6E7CC; color:var(--ok);}  
  .status-shipped{background:#CFE1F0; color:#2C5A82;}  
  .toast{position:fixed; bottom:20px; left:50%; transform:translateX(-50%); background:var(--ink); color:var(--cream); padding:12px 22px; border-radius:999px; font-size:13px; font-weight:700; z-index:200; opacity:0; transition:.3s; pointer-events:none;}  
  .toast.show{opacity:1; bottom:34px;}  
  .hint{font-size:11.5px; color:var(--ink-soft); margin-top:4px;}  
  .actions{display:flex; gap:6px;}  
  .icon-btn{background:#fff; border:1px solid var(--line); border-radius:8px; padding:5px 9px; font-size:12px;}  
  .icon-btn.danger{color:var(--danger); border-color:var(--danger);}  
  #loginModal .msg{font-size:12px; color:var(--danger); min-height:16px;}  
</style>  
</head>  
<body>  
  
<!-- ============ STOREFRONT ============ -->  
<div id="storeView">  
  
  <header class="topbar">  
    <div class="topbar-inner">  
      <div class="brand">  
        <span class="brand-mark">عُمراء</span>  
        <span class="brand-sub">OMARA&nbsp;STORE</span>  
      </div>  
      <nav class="pillnav">  
        <button class="active" onclick="scrollToSection('shop')">المتجر</button>  
        <button onclick="scrollToSection('about')">من نحن</button>  
      </nav>  
      <button class="cart-btn" onclick="openCart()">  
        🛍️ السلة <span class="cart-count" id="cartCount">0</span>  
      </button>  
    </div>  
  </header>  
  
  <section class="hero">  
    <div class="eyebrow">متجر عُمراء</div>  
    <h1>عطور تُروى، لا تُقال</h1>  
    <p>تشكيلة عطور ومنتجات مختارة بعناية، بروح شرقية أصيلة ولمسة عصرية فاخرة. كل قطعة في متجرنا تُختار لتبقى.</p>  
    <a class="wa" id="waLink" href="#" target="_blank">تواصل عبر واتساب</a>  
  </section>  
  <div class="sunrise">  
    <svg viewBox="0 0 200 90" fill="none" stroke="#20301C" stroke-width="1">  
      <path d="M100 70 A45 45 0 0 1 10 70" />  
      <path d="M20 74 Q60 60 100 74 Q140 60 180 74" />  
      <circle cx="70" cy="58" r="2" fill="#20301C" stroke="none"/>  
      <circle cx="130" cy="58" r="2" fill="#20301C" stroke="none"/>  
      <g stroke-width=".8" opacity=".7">  
        <path d="M100 22 v-14"/><path d="M80 26 l-9-12"/><path d="M120 26 l9-12"/>  
        <path d="M62 34 l-12-8"/><path d="M138 34 l12-8"/>  
        <path d="M46 50 l-14-4"/><path d="M154 50 l14-4"/>  
      </g>  
    </svg>  
  </div>  
  
  <section class="section" id="shop">  
    <div class="section-head">  
      <h2>تشكيلتنا</h2>  
      <div class="cats" id="catFilters"></div>  
    </div>  
    <div class="grid" id="productGrid"><div class="empty">جارِ تحميل المنتجات…</div></div>  
  </section>  
  
  <section class="section" id="about">  
    <div class="sunrise"><svg viewBox="0 0 200 40" fill="none" stroke="#20301C" stroke-width="1"><path d="M10 20 Q100 5 190 20"/></svg></div>  
    <div style="max-width:640px;margin:0 auto;text-align:center;">  
      <h2 style="font-size:28px;">قصة عُمراء</h2>  
      <p style="color:var(--ink-soft);line-height:2;">متجر عُمراء برئاسة عامر الشعيبي، وجهتك للعطور الفاخرة والمنتجات المختارة بعناية. نلتزم بالجودة والأصالة في كل تفصيل.</p>  
    </div>  
  </section>  
  
  <footer>  
    <div>متجر عُمراء © <span id="yr"></span> — جميع الحقوق محفوظة</div>  
    <div>صاحب المتجر: عامر الشعيبي</div>  
    <a class="admin-link" href="#admin" onclick="openAdminLogin()">لوحة التحكم</a>  
  </footer>  
</div>  
  
<!-- ============ CART DRAWER ============ -->  
<div class="scrim" id="cartScrim" onclick="closeCart()"></div>  
<div class="drawer" id="cartDrawer">  
  <div class="drawer-head"><h3>سلة المشتريات</h3><button class="x" onclick="closeCart()">✕</button></div>  
  <div class="drawer-body" id="cartBody"></div>  
  <div class="drawer-foot">  
    <div class="total-row"><span>الإجمالي</span><span id="cartTotal">0.000 ر.ع</span></div>  
    <button class="btn" onclick="openCheckout()">إتمام الطلب</button>  
  </div>  
</div>  
  
<!-- ============ CHECKOUT MODAL ============ -->  
<div class="scrim" id="checkoutScrim" onclick="closeCheckout()"></div>  
<div class="modal" id="checkoutModal">  
  <h3>إتمام الطلب</h3>  
  <label>الاسم الكامل</label><input type="text" id="ckName">  
  <label>رقم الهاتف</label><input type="tel" id="ckPhone" placeholder="7XXXXXXX">  
  <label>العنوان / الولاية</label><input type="text" id="ckAddress">  
  <label>ملاحظات (اختياري)</label><textarea id="ckNotes"></textarea>  
  <label>طريقة الدفع</label>  
  <div class="radiorow">  
    <div class="radiocard sel" id="payBankCard" onclick="selectPay('bank')">تحويل بنكي</div>  
    <div class="radiocard" id="payDepositCard" onclick="selectPay('deposit')">إيداع بنكي</div>  
  </div>  
  <div class="pay-details" id="payDetailsBox"></div>  
  <button class="btn" style="margin-top:18px;" onclick="submitOrder()">تأكيد الطلب</button>  
  <div class="hint" style="text-align:center;margin-top:8px;">سيتم التواصل معك لتأكيد الطلب بعد إرساله</div>  
</div>  
  
<!-- ============ ADMIN LOGIN ============ -->  
<div class="scrim" id="loginScrim" onclick="closeAdminLogin()"></div>  
<div class="modal" id="loginModal">  
  <h3>دخول لوحة التحكم</h3>  
  <label>كلمة المرور</label>  
  <input type="password" id="loginPass" onkeydown="if(event.key==='Enter')adminLogin()">  
  <div class="msg" id="loginMsg"></div>  
  <button class="btn" style="margin-top:14px;" onclick="adminLogin()">دخول</button>  
</div>  
  
<!-- ============ ADMIN VIEW ============ -->  
<div id="adminView">  
  <div class="adminbar">  
    <button class="active" data-tab="products" onclick="showTab('products')">المنتجات</button>  
    <button data-tab="orders" onclick="showTab('orders')">الطلبات</button>  
    <button data-tab="payment" onclick="showTab('payment')">طرق الدفع</button>  
    <button data-tab="settings" onclick="showTab('settings')">الإعدادات</button>  
    <div class="spacer"></div>  
    <button onclick="viewStore()">مشاهدة المتجر ↗</button>  
    <button onclick="adminLogout()">خروج</button>  
  </div>  
  
  <div class="admin-panel">  
  
    <!-- products tab -->  
    <div id="tab-products">  
      <div class="form-card">  
        <h3 id="pfTitle" style="margin-top:0;">إضافة منتج جديد</h3>  
        <input type="hidden" id="pfId">  
        <div class="row2">  
          <div><label>اسم المنتج</label><input type="text" id="pfName"></div>  
          <div><label>الفئة</label><input type="text" id="pfCategory" placeholder="عطور رجالية / نسائية / منتجات أخرى"></div>  
        </div>  
        <label>الوصف</label><textarea id="pfDesc"></textarea>  
        <div class="row2">  
          <div><label>السعر (ر.ع)</label><input type="number" step="0.001" id="pfPrice"></div>  
          <div><label>نسبة الخصم %</label><input type="number" step="1" id="pfDiscount" value="0"></div>  
        </div>  
        <div class="row2">  
          <div><label>الألوان (افصل بفاصلة)</label><input type="text" id="pfColors" placeholder="أسود, ذهبي, كهرماني"></div>  
          <div><label>الأحجام (افصل بفاصلة)</label><input type="text" id="pfSizes" placeholder="50ml, 100ml"></div>  
        </div>  
        <label>الكمية المتوفرة</label><input type="number" id="pfStock" value="10">  
        <label>صور المنتج</label>  
        <input type="file" id="pfImages" accept="image/*" multiple>  
        <div class="thumbstrip" id="pfThumbs"></div>  
        <div class="hint">يمكنك اختيار أكثر من صورة، وسيتم رفعها تلقائيًا لمساحة التخزين الخاصة بالمتجر.</div>  
        <div style="display:flex; gap:10px; margin-top:16px;">  
          <button class="btn" style="width:auto;padding:11px 26px;" onclick="saveProduct()">حفظ المنتج</button>  
          <button class="btn secondary" style="width:auto;padding:11px 26px;" onclick="resetProductForm()">إلغاء / جديد</button>  
        </div>  
      </div>  
  
      <table>  
        <thead><tr><th></th><th>الاسم</th><th>الفئة</th><th>السعر</th><th>الخصم</th><th>المخزون</th><th></th></tr></thead>  
        <tbody id="adminProductRows"></tbody>  
      </table>  
    </div>  
  
    <!-- orders tab -->  
    <div id="tab-orders" style="display:none;">  
      <table>  
        <thead><tr><th>التاريخ</th><th>العميل</th><th>الهاتف</th><th>الإجمالي</th><th>الدفع</th><th>الحالة</th><th></th></tr></thead>  
        <tbody id="adminOrderRows"></tbody>  
      </table>  
    </div>  
  
    <!-- payment tab -->  
    <div id="tab-payment" style="display:none;">  
      <div class="form-card">  
        <h3 style="margin-top:0;">بيانات التحويل البنكي</h3>  
        <label>اسم البنك</label><input type="text" id="payBankName">  
        <label>اسم صاحب الحساب</label><input type="text" id="payAccName">  
        <label>رقم الحساب / الآيبان</label><input type="text" id="payAccNumber">  
        <label>تعليمات إضافية</label><textarea id="payBankNotes" placeholder="مثال: يرجى إرسال صورة الإيصال عبر واتساب بعد التحويل"></textarea>  
      </div>  
      <div class="form-card">  
        <h3 style="margin-top:0;">بيانات الإيداع البنكي</h3>  
        <label>اسم البنك</label><input type="text" id="payDepBankName">  
        <label>رقم الحساب</label><input type="text" id="payDepAccNumber">  
        <label>تعليمات إضافية</label><textarea id="payDepNotes"></textarea>  
      </div>  
      <button class="btn" style="width:auto;padding:11px 26px;" onclick="savePaymentSettings()">حفظ طرق الدفع</button>  
    </div>  
  
    <!-- settings tab -->  
    <div id="tab-settings" style="display:none;">  
      <div class="form-card">  
        <h3 style="margin-top:0;">إعدادات عامة</h3>  
        <label>رقم واتساب المتجر</label><input type="text" id="setWhatsapp" placeholder="96877XXXXXXX">  
        <label>كلمة مرور لوحة التحكم الجديدة</label><input type="password" id="setNewPass" placeholder="اتركه فارغًا إن لم ترغب بالتغيير">  
        <button class="btn" style="width:auto;padding:11px 26px;margin-top:14px;" onclick="saveGeneralSettings()">حفظ الإعدادات</button>  
      </div>  
    </div>  
  
  </div>  
</div>  
  
<div class="toast" id="toast"></div>  
  
<!-- ============ FIREBASE ============ -->  
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-app-compat.js"></script>  
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore-compat.js"></script>  
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-storage-compat.js"></script>  
<script>  
const firebaseConfig = {  
  apiKey: "AIzaSyChdhF-qg2rH6pkORO-Yj0UhjrCnNBAz4E",  
  authDomain: "amer-8ef1e.firebaseapp.com",  
  projectId: "amer-8ef1e",  
  storageBucket: "amer-8ef1e.firebasestorage.app",  
  messagingSenderId: "1022495404469",  
  appId: "1:1022495404469:web:a41ef3e1ec7542027229fc",  
  measurementId: "G-TLY478287J"  
};  
firebase.initializeApp(firebaseConfig);  
const db = firebase.firestore();  
const storage = firebase.storage();  
  
const DEFAULT_ADMIN_PASSWORD = "776881748"; // غيّرها من الإعدادات فور الدخول لأول مرة  
  
let products = [];  
let orders = [];  
let paymentSettings = {};  
let generalSettings = { whatsapp: "96877881748" };  
let cart = JSON.parse(localStorage.getItem('omara_cart') || '[]');  
let activeCategory = 'الكل';  
let pendingImageFiles = [];  
let existingImageUrls = [];  
let selectedPayMethod = 'bank';  
  
function toast(msg){  
  const t = document.getElementById('toast');  
  t.textContent = msg; t.classList.add('show');  
  setTimeout(()=>t.classList.remove('show'), 2200);  
}  
document.getElementById('yr').textContent = new Date().getFullYear();  
  
/* ---------------- realtime data ---------------- */  
db.collection('products').orderBy('createdAt','desc').onSnapshot(snap=>{  
  products = snap.docs.map(d=>({id:d.id, ...d.data()}));  
  renderCategories();  
  renderProducts();  
  renderAdminProducts();  
}, err=>{  
  document.getElementById('productGrid').innerHTML = '<div class="empty">تعذّر تحميل المنتجات. تأكد من تفعيل Firestore في مشروع Firebase.</div>';  
});  
  
db.collection('orders').orderBy('createdAt','desc').onSnapshot(snap=>{  
  orders = snap.docs.map(d=>({id:d.id, ...d.data()}));  
  renderAdminOrders();  
});  
  
db.collection('settings').doc('payment').onSnapshot(doc=>{  
  paymentSettings = doc.exists ? doc.data() : {};  
  fillPaymentForm();  
  renderPayDetails();  
});  
  
db.collection('settings').doc('general').onSnapshot(doc=>{  
  if(doc.exists){  
    generalSettings = doc.data();  
    document.getElementById('setWhatsapp').value = generalSettings.whatsapp || '';  
    document.getElementById('waLink').href = 'https://wa.me/'+(generalSettings.whatsapp||'96877881748');  
  } else {  
    document.getElementById('waLink').href = 'https://wa.me/'+generalSettings.whatsapp;  
  }  
});  
  
/* ---------------- storefront rendering ---------------- */  
function renderCategories(){  
  const cats = ['الكل', ...new Set(products.map(p=>p.category).filter(Boolean))];  
  const box = document.getElementById('catFilters');  
  box.innerHTML = cats.map(c=>`<button class="${c===activeCategory?'active':''}" onclick="setCategory('${c.replace(/'/g,"\\'")}')">${c}</button>`).join('');  
}  
function setCategory(c){ activeCategory = c; renderCategories(); renderProducts(); }  
  
function renderProducts(){  
  const grid = document.getElementById('productGrid');  
  let list = products;  
  if(activeCategory !== 'الكل') list = list.filter(p=>p.category===activeCategory);  
  if(!list.length){ grid.innerHTML = '<div class="empty">لا توجد منتجات حالياً في هذا القسم.</div>'; return; }  
  grid.innerHTML = list.map(p=>{  
    const price = Number(p.price||0);  
    const disc = Number(p.discount||0);  
    const finalPrice = disc>0 ? price*(1-disc/100) : price;  
    const img = (p.images && p.images[0]) || '';  
    const colors = p.colors || [];  
    const sizes = p.sizes || [];  
    const out = Number(p.stock||0) <= 0;  
    return `  
    <div class="card">  
      <div class="imgwrap">  
        ${img?`<img src="${img}" alt="${p.name}">`:''}  
        ${disc>0?`<div class="badge-discount">خصم ${disc}%</div>`:''}  
        ${out?`<div class="badge-out">نفدت الكمية</div>`:''}  
      </div>  
      <div class="body">  
        <p class="name">${p.name||''}</p>  
        <div class="desc">${p.description||''}</div>  
        ${colors.length?`<div class="swatches" data-role="colors">${colors.map((c,i)=>`<span class="swatch ${i===0?'sel':''}" onclick="pickOpt(this)">${c}</span>`).join('')}</div>`:''}  
        ${sizes.length?`<div class="swatches" data-role="sizes">${sizes.map((s,i)=>`<span class="swatch ${i===0?'sel':''}" onclick="pickOpt(this)">${s}</span>`).join('')}</div>`:''}  
        <div class="price-row">  
          <span class="price">${finalPrice.toFixed(3)} ر.ع</span>  
          ${disc>0?`<span class="price-old">${price.toFixed(3)}</span>`:''}  
        </div>  
        <button class="addbtn" ${out?'disabled':''} onclick='addToCart(${JSON.stringify(p.id)}, this)'>${out?'غير متوفر':'أضف للسلة'}</button>  
      </div>  
    </div>`;  
  }).join('');  
}  
function pickOpt(el){  
  [...el.parentElement.children].forEach(s=>s.classList.remove('sel'));  
  el.classList.add('sel');  
}  
function addToCart(id, btn){  
  const p = products.find(x=>x.id===id);  
  if(!p) return;  
  const card = btn.closest('.card');  
  const colorEl = card.querySelector('[data-role=colors] .sel');  
  const sizeEl = card.querySelector('[data-role=sizes] .sel');  
  const color = colorEl ? colorEl.textContent : null;  
  const size = sizeEl ? sizeEl.textContent : null;  
  const key = id+'|'+color+'|'+size;  
  const existing = cart.find(c=>c.key===key);  
  if(existing){ existing.qty++; }  
  else {  
    const price = Number(p.price||0);  
    const disc = Number(p.discount||0);  
    cart.push({key, id, name:p.name, image:(p.images&&p.images[0])||'', price:disc>0?price*(1-disc/100):price, color, size, qty:1});  
  }  
  saveCart(); toast('أُضيف إلى السلة'); openCart();  
}  
function saveCart(){ localStorage.setItem('omara_cart', JSON.stringify(cart)); renderCart(); }  
function renderCart(){  
  document.getElementById('cartCount').textContent = cart.reduce((s,c)=>s+c.qty,0);  
  const body = document.getElementById('cartBody');  
  if(!cart.length){ body.innerHTML = '<div class="empty">السلة فارغة</div>'; }  
  else {  
    body.innerHTML = cart.map(c=>`  
      <div class="cart-item">  
        ${c.image?`<img src="${c.image}">`:'<div class="tbl-img" style="width:64px;height:64px;background:var(--cream-deep);border-radius:10px;"></div>'}  
        <div class="info">  
          <div class="nm">${c.name}</div>  
          <div class="meta">${[c.color,c.size].filter(Boolean).join(' · ')}</div>  
          <div class="meta">${c.price.toFixed(3)} ر.ع</div>  
          <div class="qty">  
            <button onclick="changeQty('${c.key}',-1)">−</button>  
            <span>${c.qty}</span>  
            <button onclick="changeQty('${c.key}',1)">+</button>  
            <button onclick="removeItem('${c.key}')" style="margin-right:8px;color:var(--danger);border:none;background:none;">حذف</button>  
          </div>  
        </div>  
      </div>`).join('');  
  }  
  const total = cart.reduce((s,c)=>s+c.price*c.qty,0);  
  document.getElementById('cartTotal').textContent = total.toFixed(3)+' ر.ع';  
}  
function changeQty(key,d){ const it = cart.find(c=>c.key===key); if(!it) return; it.qty+=d; if(it.qty<=0) cart = cart.filter(c=>c.key!==key); saveCart(); }  
function removeItem(key){ cart = cart.filter(c=>c.key!==key); saveCart(); }  
function openCart(){ document.getElementById('cartDrawer').classList.add('show'); document.getElementById('cartScrim').classList.add('show'); }  
function closeCart(){ document.getElementById('cartDrawer').classList.remove('show'); document.getElementById('cartScrim').classList.remove('show'); }  
function scrollToSection(id){ document.getElementById(id).scrollIntoView({behavior:'smooth'}); }  
  
/* ---------------- checkout ---------------- */  
function openCheckout(){  
  if(!cart.length){ toast('السلة فارغة'); return; }  
  closeCart();  
  document.getElementById('checkoutModal').classList.add('show');  
  document.getElementById('checkoutScrim').classList.add('show');  
  renderPayDetails();  
}  
function closeCheckout(){ document.getElementById('checkoutModal').classList.remove('show'); document.getElementById('checkoutScrim').classList.remove('show'); }  
function selectPay(m){  
  selectedPayMethod = m;  
  document.getElementById('payBankCard').classList.toggle('sel', m==='bank');  
  document.getElementById('payDepositCard').classList.toggle('sel', m==='deposit');  
  renderPayDetails();  
}  
function renderPayDetails(){  
  const box = document.getElementById('payDetailsBox');  
  if(selectedPayMethod==='bank'){  
    box.textContent = `البنك: ${paymentSettings.bankName||'—'}\nاسم الحساب: ${paymentSettings.accName||'—'}\nرقم الحساب/الآيبان: ${paymentSettings.accNumber||'—'}\n${paymentSettings.bankNotes||''}`;  
  } else {  
    box.textContent = `البنك: ${paymentSettings.depBankName||'—'}\nرقم الحساب: ${paymentSettings.depAccNumber||'—'}\n${paymentSettings.depNotes||''}`;  
  }  
}  
async function submitOrder(){  
  const name = document.getElementById('ckName').value.trim();  
  const phone = document.getElementById('ckPhone').value.trim();  
  const address = document.getElementById('ckAddress').value.trim();  
  const notes = document.getElementById('ckNotes').value.trim();  
  if(!name || !phone || !address){ toast('يرجى تعبئة الاسم والهاتف والعنوان'); return; }  
  const total = cart.reduce((s,c)=>s+c.price*c.qty,0);  
  try{  
    await db.collection('orders').add({  
      name, phone, address, notes,  
      items: cart, total,  
      payMethod: selectedPayMethod,  
      status:'pending',  
      createdAt: firebase.firestore.FieldValue.serverTimestamp()  
    });  
    cart = []; saveCart();  
    closeCheckout();  
    toast('تم إرسال طلبك بنجاح، سنتواصل معك قريباً');  
  }catch(e){ toast('حدث خطأ أثناء إرسال الطلب'); }  
}  
  
/* ---------------- admin: auth ---------------- */  
function openAdminLogin(){ document.getElementById('loginModal').classList.add('show'); document.getElementById('loginScrim').classList.add('show'); }  
function closeAdminLogin(){ document.getElementById('loginModal').classList.remove('show'); document.getElementById('loginScrim').classList.remove('show'); }  
  
async function adminLogin(){  
  const msgEl = document.getElementById('loginMsg');  
  const pass = document.getElementById('loginPass').value;  
    
  msgEl.style.color = '#2C5A82';   
  msgEl.textContent = 'جارِ الاتصال بقاعدة البيانات... يرجى الانتظار.';  
  
  try {  
    const ref = db.collection('settings').doc('admin');  
    const doc = await ref.get();  
    let ok = false;  
      
    if(!doc.exists){  
      if(pass === DEFAULT_ADMIN_PASSWORD){   
        await ref.set({password: DEFAULT_ADMIN_PASSWORD});   
        ok = true;   
      }  
    } else {  
      ok = (pass === doc.data().password);  
    }  
      
    if(ok){  
      sessionStorage.setItem('omara_admin','1');  
      closeAdminLogin();  
      enterAdmin();  
      msgEl.textContent = '';   
    } else {  
      msgEl.style.color = 'var(--danger)';  
      msgEl.textContent = 'كلمة المرور غير صحيحة';  
    }  
  } catch (error) {  
    msgEl.style.color = 'var(--danger)';  
    msgEl.textContent = 'خطأ في الاتصال: ' + error.message;  
  }  
}  
  
function adminLogout(){ sessionStorage.removeItem('omara_admin'); viewStore(); }  
function enterAdmin(){  
  document.getElementById('storeView').style.display='none';  
  document.getElementById('adminView').style.display='block';  
}  
function viewStore(){  
  document.getElementById('adminView').style.display='none';  
  document.getElementById('storeView').style.display='block';  
  history.replaceState(null,null,' ');  
}  
if(location.hash==='#admin' && sessionStorage.getItem('omara_admin')==='1'){ enterAdmin(); }  
  
function showTab(name){  
  ['products','orders','payment','settings'].forEach(t=>{  
    document.getElementById('tab-'+t).style.display = (t===name)?'block':'none';  
  });  
  document.querySelectorAll('.adminbar button[data-tab]').forEach(b=>b.classList.toggle('active', b.dataset.tab===name));  
}  
  
/* ---------------- admin: products ---------------- */  
document.getElementById('pfImages').addEventListener('change', e=>{  
  pendingImageFiles = [...e.target.files];  
  renderThumbs();  
});  
function renderThumbs(){  
  const box = document.getElementById('pfThumbs');  
  let html = existingImageUrls.map((u,i)=>`<div class="th"><img src="${u}"><button class="rm" onclick="removeExistingImage(${i})">✕</button></div>`).join('');  
  html += pendingImageFiles.map(f=>`<div class="th"><img src="${URL.createObjectURL(f)}"></div>`).join('');  
  box.innerHTML = html;  
}  
function removeExistingImage(i){ existingImageUrls.splice(i,1); renderThumbs(); }  
  
function resetProductForm(){  
  document.getElementById('pfId').value='';  
  document.getElementById('pfName').value='';  
  document.getElementById('pfCategory').value='';  
  document.getElementById('pfDesc').value='';  
  document.getElementById('pfPrice').value='';  
  document.getElementById('pfDiscount').value='0';  
  document.getElementById('pfColors').value='';  
  document.getElementById('pfSizes').value='';  
  document.getElementById('pfStock').value='10';  
  document.getElementById('pfImages').value='';  
  pendingImageFiles=[]; existingImageUrls=[];  
  renderThumbs();  
  document.getElementById('pfTitle').textContent='إضافة منتج جديد';  
}  
function editProduct(id){  
  const p = products.find(x=>x.id===id);  
  if(!p) return;  
  document.getElementById('pfId').value=p.id;  
  document.getElementById('pfName').value=p.name||'';  
  document.getElementById('pfCategory').value=p.category||'';  
  document.getElementById('pfDesc').value=p.description||'';  
  document.getElementById('pfPrice').value=p.price||'';  
  document.getElementById('pfDiscount').value=p.discount||0;  
  document.getElementById('pfColors').value=(p.colors||[]).join(', ');  
  document.getElementById('pfSizes').value=(p.sizes||[]).join(', ');  
  document.getElementById('pfStock').value=p.stock||0;  
  existingImageUrls=[...(p.images||[])]; pendingImageFiles=[];  
  document.getElementById('pfImages').value='';  
  renderThumbs();  
  document.getElementById('pfTitle').textContent='تعديل المنتج';  
  window.scrollTo({top:0,behavior:'smooth'});  
}  
async function deleteProduct(id){  
  if(!confirm('حذف هذا المنتج نهائياً؟')) return;  
  await db.collection('products').doc(id).delete();  
  toast('تم حذف المنتج');  
}  
async function saveProduct(){  
  const name = document.getElementById('pfName').value.trim();  
  const price = Number(document.getElementById('pfPrice').value);  
  if(!name || !price){ toast('يرجى إدخال اسم وسعر المنتج'); return; }  
  toast('جارٍ الحفظ…');  
  try{  
    let urls = [...existingImageUrls];  
    for(const file of pendingImageFiles){  
      const path = 'products/'+Date.now()+'_'+file.name;  
      const ref = storage.ref().child(path);  
      await ref.put(file);  
      urls.push(await ref.getDownloadURL());  
    }  
    const data = {  
      name,  
      category: document.getElementById('pfCategory').value.trim() || 'منتجات أخرى',  
      description: document.getElementById('pfDesc').value.trim(),  
      price,  
      discount: Number(document.getElementById('pfDiscount').value)||0,  
      colors: document.getElementById('pfColors').value.split(',').map(s=>s.trim()).filter(Boolean),  
      sizes: document.getElementById('pfSizes').value.split(',').map(s=>s.trim()).filter(Boolean),  
      stock: Number(document.getElementById('pfStock').value)||0,  
      images: urls  
    };  
    const id = document.getElementById('pfId').value;  
    if(id){ await db.collection('products').doc(id).update(data); }  
    else { data.createdAt = firebase.firestore.FieldValue.serverTimestamp(); await db.collection('products').add(data); }  
    resetProductForm();  
    toast('تم حفظ المنتج بنجاح');  
  }catch(e){ toast('تعذّر الحفظ، تأكد من تفعيل Firebase Storage'); }  
}  
function renderAdminProducts(){  
  document.getElementById('adminProductRows').innerHTML = products.map(p=>`  
    <tr>  
      <td>${p.images&&p.images[0]?`<img class="tbl-img" src="${p.images[0]}">`:''}</td>  
      <td>${p.name}</td>  
      <td>${p.category||''}</td>  
      <td>${Number(p.price||0).toFixed(3)}</td>  
      <td>${p.discount||0}%</td>  
      <td>${p.stock||0}</td>  
      <td class="actions">  
        <button class="icon-btn" onclick="editProduct('${p.id}')">تعديل</button>  
        <button class="icon-btn danger" onclick="deleteProduct('${p.id}')">حذف</button>  
      </td>  
    </tr>`).join('');  
}  
  
/* ---------------- admin: orders ---------------- */  
function renderAdminOrders(){  
  document.getElementById('adminOrderRows').innerHTML = orders.map(o=>{  
    const date = o.createdAt && o.createdAt.toDate ? o.createdAt.toDate().toLocaleString('ar-OM') : '—';  
    return `<tr>  
      <td>${date}</td>  
      <td>${o.name}<div class="hint">${o.address||''}</div></td>  
      <td>${o.phone}</td>  
      <td>${Number(o.total||0).toFixed(3)} ر.ع</td>  
      <td>${o.payMethod==='bank'?'تحويل بنكي':'إيداع بنكي'}</td>  
      <td><span class="status-pill status-${o.status}">${{pending:'قيد الانتظار',confirmed:'مؤكد',shipped:'تم الشحن'}[o.status]||o.status}</span></td>  
      <td>  
        <select onchange="updateOrderStatus('${o.id}',this.value)">  
          <option value="pending" ${o.status==='pending'?'selected':''}>قيد الانتظار</option>  
          <option value="confirmed" ${o.status==='confirmed'?'selected':''}>مؤكد</option>  
          <option value="shipped" ${o.status==='shipped'?'selected':''}>تم الشحن</option>  
        </select>  
      </td>  
    </tr>`;  
  }).join('') || '<tr><td colspan="7" class="empty">لا توجد طلبات بعد</td></tr>';  
}  
async function updateOrderStatus(id,status){ await db.collection('orders').doc(id).update({status}); toast('تم تحديث حالة الطلب'); }  
  
/* ---------------- admin: payment settings ---------------- */  
function fillPaymentForm(){  
  document.getElementById('payBankName').value = paymentSettings.bankName||'';  
  document.getElementById('payAccName').value = paymentSettings.accName||'';  
  document.getElementById('payAccNumber').value = paymentSettings.accNumber||'';  
  document.getElementById('payBankNotes').value = paymentSettings.bankNotes||'';  
  document.getElementById('payDepBankName').value = paymentSettings.depBankName||'';  
  document.getElementById('payDepAccNumber').value = paymentSettings.depAccNumber||'';  
  document.getElementById('payDepNotes').value = paymentSettings.depNotes||'';  
}  
async function savePaymentSettings(){  
  const data = {  
    bankName: document.getElementById('payBankName').value.trim(),  
    accName: document.getElementById('payAccName').value.trim(),  
    accNumber: document.getElementById('payAccNumber').value.trim(),  
    bankNotes: document.getElementById('payBankNotes').value.trim(),  
    depBankName: document.getElementById('payDepBankName').value.trim(),  
    depAccNumber: document.getElementById('payDepAccNumber').value.trim(),  
    depNotes: document.getElementById('payDepNotes').value.trim(),  
  };  
  await db.collection('settings').doc('payment').set(data, {merge:true});  
  toast('تم حفظ طرق الدفع');  
}  
  
/* ---------------- admin: general settings ---------------- */  
async function saveGeneralSettings(){  
  const wa = document.getElementById('setWhatsapp').value.trim();  
  await db.collection('settings').doc('general').set({whatsapp:wa}, {merge:true});  
  const newPass = document.getElementById('setNewPass').value.trim();  
  if(newPass){  
    await db.collection('settings').doc('admin').set({password:newPass});  
    document.getElementById('setNewPass').value='';  
    toast('تم حفظ الإعدادات وتغيير كلمة المرور');  
  } else {  
    toast('تم حفظ الإعدادات');  
  }  
}  
  
renderCart();  
</script>  
</body>  
</html>  

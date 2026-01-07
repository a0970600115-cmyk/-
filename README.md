<!DOCTYPE html>
<html>
  <head>
    <base target="_top">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <style>
      body { background-color: #f8f9fa; font-family: "Microsoft JhengHei", sans-serif; }
      .club-card { 
        transition: 0.3s; 
        border-left: 5px solid #0d6efd;
        cursor: pointer;
        background-color: white;
      }
      .club-card:hover { 
        background-color: #f1f3f5;
        transform: translateY(-3px);
        box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      }
      .card h5 { color: #333; font-weight: bold; }
    </style>
  </head>
  <body class="p-4">
    <div class="container bg-white shadow p-4 rounded">
      <div class="d-flex justify-content-between align-items-center mb-4 border-bottom pb-3">
        <h2 class="text-primary fw-bold">🔍 7 大特色社團介紹</h2>
        <button class="btn btn-outline-secondary" onclick="navBack()">回首頁</button>
      </div>

      <div class="row g-3">
        <div class="col-12">
          <div class="card p-3 club-card" onclick="goClub('🎸 熱音社')">
            <h5>🎸 熱音社</h5>
            <p class="text-muted mb-2">提供專業練團室，每年固定舉辦期初與期末成果發表會。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#6610f2;" onclick="goClub('💃 現代舞社')">
            <h5>💃 現代舞社</h5>
            <p class="text-muted mb-2">由專業導師帶領，從零基礎開始學習各種舞風。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#198754;" onclick="goClub('🏀 籃球社')">
            <h5>🏀 籃球社</h5>
            <p class="text-muted mb-2">定期舉辦校內聯賽，與外校進行友誼賽交流技術。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#20c997;" onclick="goClub('💻 程式設計社')">
            <h5>💻 程式設計社</h5>
            <p class="text-muted mb-2">學習網頁開發、AI 應用，並參與各類黑客松競賽。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#fd7e14;" onclick="goClub('📸 攝影社')">
            <h5>📸 攝影社</h5>
            <p class="text-muted mb-2">走訪全台景點外拍，學習構圖、修圖與光影運用。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#6f42c1;" onclick="goClub('☕ 咖啡品評社')">
            <h5>☕ 咖啡品評社</h5>
            <p class="text-muted mb-2">認識世界各國手沖豆，學習拉花技巧與品飲文化。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
        
        <div class="col-12">
          <div class="card p-3 club-card" style="border-left-color:#0dcaf0;" onclick="goClub('🏸 羽球社')">
            <h5>🏸 羽球社</h5>
            <p class="text-muted mb-2">熱血揮灑汗水，提供多個場地供社員切磋球技。</p>
            <small class="text-primary text-end d-block">點擊進入留言板 →</small>
          </div>
        </div>
      </div>
    </div>

    <script>
      /**
       * 跳轉至留言板頁面
       * @param {string} name - 社團名稱
       */
      function goClub(name) {
  google.script.run.withSuccessHandler(url => {
    // 這裡必須包含 &club=... 
    // 而且跳轉的 page 必須叫做 Comment (如果你的檔名是 Comment.html)
    const targetUrl = url + '?page=Comment&club=' + encodeURIComponent(name);
    
    // 強力建議使用 window.top 進行跳轉
    if (window.top) {
      window.top.location.href = targetUrl;
    } else {
      window.location.href = targetUrl;
    }
  }).getScriptUrl();
}

      /**
       * 返回首頁
       */
      function navBack() {
        google.script.run.withSuccessHandler(function(url) {
          const targetUrl = url + '?page=Index';
          if (window.top) {
            window.top.location.href = targetUrl;
          } else {
            window.location.href = targetUrl;
          }
        }).getScriptUrl();
      }
    </script>
  </body>
</html>

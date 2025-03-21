<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>査定フォーム</title>
  <!-- LIFF SDK読み込み -->
  <script charset="utf-8" src="https://static.line-scdn.net/liff/edge/2/sdk.js"></script>
</head>
<body>
  <!-- フォーム内容 -->
  <script>
    // LIFF初期化
    document.addEventListener('DOMContentLoaded', function() {
      liff.init({ liffId: "あなたのLIFF ID" })
        .then(() => {
          // 初期化成功
          if (liff.isLoggedIn()) {
            // ユーザーがログイン済みの場合の処理
            getUserProfile();
          } else {
            // 未ログインの場合はログイン促す
            liff.login();
          }
        })
        .catch((err) => {
          console.error("LIFF initialization failed", err);
        });
    });
  </script>
</body>
</html>

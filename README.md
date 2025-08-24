# Booth用Twitter検索ブックマークレット

エゴサや、他の人の着こなしを参考にするために作りました✨  
Boothの商品ページを開いた状態でブックマークに登録したコードを実行すると、その商品のIDを使ってTwitterで検索できます💌  
自分のアイテムのエゴサや、他ユーザーのコーディネート例を手軽に見たい方におすすめです💖

｡ﾟ•┈୨୧┈•ﾟ｡ ♡ ｡ﾟ•┈୨୧┈•ﾟ｡｡ﾟ•┈୨୧┈•ﾟ｡ ♡ ｡ﾟ•┈୨୧┈•ﾟ｡

### 🎀 ブックマークレットコード
以下のコードをコピーして、ブラウザのブックマークに登録してください💡

```javascript
javascript:(function(){
  if(!location.href.includes("booth.pm")){
    alert("このページでは使用できません");
    return;
  }
  var matchChk = location.href.match(/\/items\/(\d+)/);
  if(matchChk){
    var id = matchChk[1];
    var url = "https://twitter.com/search?q=" + encodeURIComponent(id + " booth");
    window.open(url, "_blank");
  } else {
    alert("商品IDが取得できませんでした");
  }
})();
```

### 🎀 作成の経緯
実はboothの商品URLは複数あります！  
検索するときは丸ごとURLより「booth 商品ID」で検索する方がHITします。  
いちいち商品IDだけ抜き出すのは面倒だったのでブックマークレットをつくることにしました✨   

①https://booth.pm/言語コード/items/商品ID  
②https://ショップのサブドメイン/booth.pm/items/商品ID  

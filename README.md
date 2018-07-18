# s_html_accordion01
シンプルなアコーディオン

https://webmoyou.com/web/124/

## HTML

```
<div class="accordion">
     
      <section>
        <h2 class="switch">ご注文の流れ</h2>
        <div class="contentWrap">
          ここにアコーディオン01の中身が入ります。
        </div>
      </section>
      <section>
        <h2 class="switch">お支払い方法について</h2>
        <div class="contentWrap displayNone">
          ここにアコーディオン02の中身が入ります。
        </div>
      </section>
      <section>
        <h2 class="switch">送料・配送方法</h2>
        <div class="contentWrap displayNone">
          ここにアコーディオン02の中身が入ります。
        </div>
      </section>
      <section>
        <h2 class="switch">ギフト包装について</h2>
        <div class="contentWrap displayNone">
          ここにアコーディオン02の中身が入ります。
        </div>
      </section>
      <section>
        <h2 class="switch">返品・交換について</h2>
        <div class="contentWrap displayNone">
          <p>当店で取り扱う商品は手作りのため、ひとつひとつ模様や大きさ、色、形が異なります。十分ご検討いただいた上でのご注文をお願いいたします。<br>商品写真はできる限り実物に近いように調整しておりますが、お客さまのモニターの環境などにより、色味が変わって見える場合がございますので、予めご了承ください。</p>

          <p>返品の対象となるのは、以下の場合のみです。<br>・注文と違う商品が届いた<br>・商品の不良<br>・配送中の破損</p>

          <p>商品到着日より一週間以内に、お問い合わせよりご連絡ください。返品後、在庫のある商品は交換、在庫のない商品は返金とさせて頂きます。</p>

          <p>※お客さまのご都合による返品・交換はお受けしておりません<br>※商品到着日より7日以内にご連絡いただかない場合も返品・交換はお受けしておりません</p>
        </div>
      </section>
      <section id="security">
        <h2 class="switch">セキュリティについて</h2>
        <div class="contentWrap displayNone">
          <p>ご購入手続き画面で入力される個人情報は、これらの情報が傍受・妨害または改ざんされることを防ぐためGMOグローバルサイン社のSSLを使用しています。SSLにより暗号化されてから安全に送受信されますので、お客様の個人情報が保護されます。<br>お預かりしたお客様の個人情報は、弊社の個人情報保護方針に則り、適切かつ安全な管理を行っておりますので、安心してお買い物をお楽しみください。</p>
        </div>
      </section>
    
    </div>
```

## js

```

//アコーディオン
  $(function() {
    var accordion = $(".accordion");
    accordion.each(function () {
      var noTargetAccordion = $(this).siblings(accordion);
      $(this).find(".switch").click(function() {
        $(this).next(".contentWrap").slideToggle();
        $(this).toggleClass("open");
        noTargetAccordion.find(".contentWrap").slideUp();
        noTargetAccordion.find(".switch").removeClass("open");
      });
    });
  });
  
```

## CSS

```

/* 以下アコーディオン用 */
  .displayNone {
    display: none;
  }
  .accordion li {
    border-bottom: 1px solid #ccc;
    padding: 10px;
  }
  .accordion a {
    display: block;
  }
  .contentWrap {
    margin: 10px;
  }
  .switch {
    cursor:pointer;
    font-weight: bold;
    padding:10px 40px 10px 10px;
    font-size: 14px;
    background: #eee;
    border-bottom: 1px solid #ccc;
    position: relative;
  }
  .switch:after {
    position: absolute;
    top: 60%;
    right: 10px;
    margin-top: -18px;
    content: '>';
    font-size: 18px;
    font-weight: bold;
    -moz-transform: rotate(90deg);
    -ms-transform: rotate(90deg);
    -webkit-transform: rotate(90deg);
    transform: rotate(90deg);
    -moz-transition: all, 0.25s, linear;
    -o-transition: all, 0.25s, linear;
    -webkit-transition: all, 0.25s, linear;
    transition: all, 0.25s, linear;
    font-family: sans-serif;
    color: #FF6685;
  }
  .switch.open:after {
    -moz-transform: translate(0, 50%);
    -ms-transform: translate(0, 50%);
    -webkit-transform: translate(0, 50%);
    transform: translate(0, 50%);
    -moz-transform: rotate(-90deg);
    -ms-transform: rotate(-90deg);
    -webkit-transform: rotate(-90deg);
    transform: rotate(-90deg);
    font-family: sans-serif;
  }
  
```

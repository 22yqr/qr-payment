# 个人微信收款说明页

在 PyCharm 中打开 `index.html` 后直接点击运行，或在浏览器中打开，即可查看手机端页面。

这是个人收款码的说明页：客户扫码进入后填写 QQ 号、确认默认 ¥13.00（可自行修改），再识别页面中展示的个人微信收款码付款。付款状态只能由收款方在微信收款记录中人工核验，页面不会读取、确认或保存付款信息。

## 配置个人收款码

1. 原始微信收款码海报保存为 `assets/wechat-payment-code.jpg`；可识别的二维码主体已裁切为 `assets/wechat-payment-qr-only.png`。
2. `index.html` 底部的 `PAYMENT_CONFIG.qrImageSrc` 已配置为裁切后的高清二维码。
3. 按需修改下列配置：

   - `merchantName`：收款方名称
   - `itemName`：付款项目
   - `defaultAmount`：默认金额
   - `minAmount`、`maxAmount`：允许输入的金额范围

要让客户扫描“入口二维码”打开本页面，还需要把页面部署到自己的公开 HTTPS 地址，再用该页面地址生成入口二维码。个人微信收款码仍由页面中的二维码图片展示；本项目不会生成微信支付订单或伪造付款成功小票。

## 固定入口二维码

启用 GitHub Pages 后，本页面地址为 `https://22yqr.github.io/qr-payment/`。入口二维码图片保存为 `assets/entry-qr.png`，可下载、打印或转发给客户；该二维码附带版本参数，以避免微信继续使用旧页面缓存。客户扫码后会先进入本说明页，再识别其中的个人微信收款码。

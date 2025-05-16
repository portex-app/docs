---
description: >-
  portex.pay 是一个允许用户为虚拟商品付费的功能。（目前仅支持 telegram stars）
icon: cart-shopping
---

# 支付

![portex.pay](../assets/pay_star.png)

## 功能

* 可自定义支付商品
* 无服务器支付流程
* 支付状态跟踪
* 支付异常处理

## API 文档

* 打开支付对话框

```typescript
pay(
    options: PaymentOptions,
    callback?: (result: InvoiceClosedResult) => void,
): Promise<PaymentResult>
```

* 查询支付订单

```typescript
queryOrder(orderId: string): Promise<OrderResult>
```

* 恢复支付

```typescript
resumePayment(
    callback?: (result: InvoiceClosedResult) => void,
): Promise<null | PaymentResult>
```

* 检查待处理支付

```typescript
hasPendingPayment(): boolean
```

## 接口

```typescript
interface PaymentOptions {
    tg_use_id: string; // telegram 用户 ID
    amount: number; // 金额（卢布）
    label: string; // 标签
    title: string; // 标题
    description: string; // 描述
    payload?: string; // 负载
    photo_height?: number; // 图片高度
    photo_width?: number; // 图片宽度
    photo_size?: number; // 图片大小
    photo_url?: string; // 图片链接
    callback_url?: string; // 回调链接
}

interface PaymentResult {
    tg_payment_id: number; // telegram 支付 ID
    tg_payment_url: string; // telegram 支付链接
}

interface InvoiceClosedResult {
    orderId: number; // 订单 ID
    status: "failed" | "paid" | "cancelled" | "pending"; // 状态
}

interface OrderResult {
    amount: number; // 金额（卢布）
    application_id: string; // 应用 ID
    description: string; // 描述
    label: string; // 标签
    payload: string; // 负载
    status: number; // 状态
    status_description: string; // 状态描述
    tg_payment_id: string; // telegram 支付 ID
    tg_use_id: string; // telegram 用户 ID
    title: string; // 标题
}
```

## 示例

```typescript
const portex = new Portex({
    appId: 'your-app-id',
});

await portex.init();

const requiredObject = {
    tg_use_id: portex.webApp.initDataUnsafe.user.id,
    amount: 1,
    label: 'item',
    title: 'Book',
    description: 'Magic book'
};

const result = await portex.pay({
    ...requiredObject,
    payload: 'your-payload',
    photo_url: 'https://your-photo-url.com'
},(result) => {
    if (portex.hasPendingPayment()) {
        // 支付待处理或已取消
    }else{
        // 支付已完成
        // 获取支付结果
        const paymentResult = await portex.queryOrder(result.orderId);
    }
});
```

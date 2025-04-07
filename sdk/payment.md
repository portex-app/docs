# Portex SDK Payment

* `portex.pay` is a feature that allows users to pay for virtual goods. (now only for telegram StarFi)

![portex.pay](../assets/pay_star.png)

## Features
* customizable payment goods
* serverless payment process
* payment status tracking
* payment exception handling

## API Documentation

* open payment dialog
```typescript
pay(
    options: PaymentOptions,
    callback?: (result: InvoiceClosedResult) => void,
): Promise<PaymentResult>
```

* query payment order
```typescript
queryOrder(orderId: string): Promise<OrderResult>
```

* resume payment
```typescript
resumePayment(
    callback?: (result: InvoiceClosedResult) => void,
): Promise<null | PaymentResult>
```

* check pending payment
```typescript
hasPendingPayment(): boolean
```

## Interface

```typescript
interface PaymentOptions {
    tg_use_id: string; // telegram user id
    amount: number; // amount in rubles
    label: string; // label
    title: string; // title
    description: string; // description
    payload?: string; // payload
    photo_height?: number; // photo height
    photo_width?: number; // photo width
    photo_size?: number; // photo size
    photo_url?: string; // photo url
    callback_url?: string; // callback url
}

interface PaymentResult {
    tg_payment_id: number; // telegram payment id
    tg_payment_url: string; // telegram payment url
}

interface InvoiceClosedResult {
    orderId: number; // order id
    status: "failed" | "paid" | "cancelled" | "pending"; // status
}

interface OrderResult {
    amount: number; // amount in rubles
    application_id: string; // application id
    description: string; // description
    label: string; // label
    payload: string; // payload
    status: number; // status
    status_description: string; // status description
    tg_payment_id: string; // telegram payment id
    tg_use_id: string; // telegram user id
    title: string; // title
}
```

## Example

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
        // payment is pending or cancelled
    }else{
        // payment is paid
        // get payment result
        const paymentResult = await portex.queryOrder(result.orderId);
    }
});
```
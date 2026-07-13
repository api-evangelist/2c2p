# 2C2P (2c2p)

2C2P is a Singapore-headquartered payments platform serving merchants across Southeast Asia and beyond. Its Payment Gateway (PGW) API - currently **Payment v4.3** - lets merchants accept cards, e-wallets, QR, installments, and alternative payment methods through a server-to-server REST interface. 2C2P is part of Ant International.

## Access Model (Read This First)

- **Merchant onboarding, not self-serve keys.** Production access requires a 2C2P merchant account (commercial onboarding / KYC). 2C2P issues a **Merchant ID** and a **Secret Key** from the merchant profile - there is no public "get an API key" button in the docs.
- **JWT-signed requests.** The PGW API does **not** use an `Authorization` header. Every request body is a **JSON Web Token (JWS)** whose payload carries the transaction fields and whose signature authenticates the merchant. The merchant signs the JWT with its Secret Key using **HMAC SHA-256 (HS256)**; 2C2P returns a JWT signed the same way, which the merchant verifies and decodes. The merchant is identified by the `merchantID` inside the signed payload. Select endpoints also support a JWT+JWS (asymmetric) variant.
- **Sandbox then production.** Build and test against the sandbox, then switch hosts for production:
  - Sandbox: `https://sandbox-pgw.2c2p.com/payment/4.3`
  - Production: `https://pgw.2c2p.com/payment/4.3`
- **Async results are webhooks, not sockets.** Payment outcomes are delivered as a **backend notification**: 2C2P POSTs a signed JWT to the merchant's `backendReturnUrl`, and the browser is redirected to `frontendReturnUrl`. There is no WebSocket or SSE API.
- **PCI-reducing card capture.** With **Secure Fields**, card input elements are loaded from 2C2P directly into the merchant's checkout page, returning an `encryptedCardInfo` / `securePayToken` that is submitted inside the signed Do Payment request - raw PAN never touches the merchant server.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/2c2p/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/2c2p/refs/heads/main/apis.yml)

## Tags

- Payments
- Payment Gateway
- Southeast Asia
- Singapore
- Thailand
- Cards
- E-Wallet
- Payment Token
- Cross-Border
- Fintech

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

All PGW v4.3 operations are HTTPS `POST` with JWT (JWS) request/response bodies. Base URL: `https://pgw.2c2p.com/payment/4.3` (production) or `https://sandbox-pgw.2c2p.com/payment/4.3` (sandbox).

### 2C2P Payment Token API

Server-to-server POST that initializes a payment and returns a `paymentToken` plus a `webPaymentUrl` for the hosted payment page. Carries `invoiceNo`, `amount`, `currencyCode`, `description`, and channel / tokenize options.

- **Human URL:** [https://developer.2c2p.com/docs/api-payment-token](https://developer.2c2p.com/docs/api-payment-token)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoint: `POST /paymentToken`

### 2C2P Do Payment API

Executes a payment against a `paymentToken`, selecting the channel (card, e-wallet, QR, installment, pay-later, loyalty) via the payment code and supplying card, customer, browser, and return-URL data. Supports the direct / Secure Fields integration.

- **Human URL:** [https://developer.2c2p.com/docs/sdk-api-do-payment](https://developer.2c2p.com/docs/sdk-api-do-payment)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoint: `POST /payment`

### 2C2P Payment Option API

Returns the payment options and channel details available for a given `paymentToken` - methods, groupings, and per-channel metadata used to render a custom checkout (`paymentOption`, `paymentOptionDetails`).

- **Human URL:** [https://developer.2c2p.com/docs/api-payment-option](https://developer.2c2p.com/docs/api-payment-option)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoints: `POST /paymentOption`, `POST /paymentOptionDetails`

### 2C2P Payment Inquiry API

Retrieves the full result of a transaction by `merchantID` and `invoiceNo` (or `paymentToken` via `transactionStatus`), returning amount, status, approval and reference codes, masked account / card token, installment, and FX details.

- **Human URL:** [https://developer.2c2p.com/docs/api-payment-inquiry](https://developer.2c2p.com/docs/api-payment-inquiry)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoints: `POST /paymentInquiry`, `POST /transactionStatus`

### 2C2P Payment Maintenance API

Post-authorization maintenance - void / cancel a transaction via `cancelTransaction`, plus refund and settle operations covered by the payment maintenance guides.

- **Human URL:** [https://developer.2c2p.com/docs/payment-maintenance-refund-guide](https://developer.2c2p.com/docs/payment-maintenance-refund-guide)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoint: `POST /cancelTransaction`

### 2C2P Card Token & Recurring API

Card tokenization and stored-credential operations - `cardTokenInfo` for saved card tokens and `cardInstallmentPlanInfo` for installment plans - together with the recurring payment plans used for subscriptions and returning buyers.

- **Human URL:** [https://developer.2c2p.com/docs/payment-maintenance-recurring-payment-guide](https://developer.2c2p.com/docs/payment-maintenance-recurring-payment-guide)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoints: `POST /cardTokenInfo`, `POST /cardInstallmentPlanInfo`

### 2C2P Exchange Rate API

Retrieves currency exchange rates for a transaction, supporting dynamic currency conversion (DCC) and alternative-payment-method MCC exchange rates. A JWT+JWS secured variant is available.

- **Human URL:** [https://developer.2c2p.com/reference/post_payment-4-3-exchangerate](https://developer.2c2p.com/reference/post_payment-4-3-exchangerate)
- **Base URL:** `https://pgw.2c2p.com/payment/4.3`
- Endpoint: `POST /exchangeRate`

### 2C2P Secure Fields

Browser-side card capture that loads 2C2P-hosted input elements into the merchant's own checkout page, returning an `encryptedCardInfo` / `securePayToken` that is passed to the Do Payment (or SecurePay) API so raw PAN never touches the merchant server. Reduces merchant PCI scope.

- **Human URL:** [https://developer.2c2p.com/docs/using-securefields](https://developer.2c2p.com/docs/using-securefields)
- **Base URL:** `https://pgw.2c2p.com`

## Artifacts

- [OpenAPI](openapi/2c2p-openapi.yml) — models the decoded JSON payloads for the confirmed PGW v4.3 endpoints (real requests/responses are JWT-encoded)
- [Postman Collection](collections/2c2p.postman_collection.json)
- [Open Collection](collections/2c2p.opencollection.json)
- [Authentication](authentication/2c2p-authentication.yml)
- [Plans](plans/2c2p-plans-pricing.yml)
- [Rate Limits](rate-limits/2c2p-rate-limits.yml)
- [FinOps](finops/2c2p-finops.yml)
- [Domain Security](security/2c2p-domain-security.yml)
- [Review](review.yml)

## Real vs. Modeled

- **Confirmed:** the base hosts (`pgw.2c2p.com`, `sandbox-pgw.2c2p.com`), the Payment v4.3 endpoint paths, the JWT (JWS) HMAC SHA-256 auth model, and the Merchant ID + Secret Key credential flow are all documented on developer.2c2p.com.
- **Modeled:** the request/response field schemas in the OpenAPI and collections are a representative subset derived from the documented parameters, presented as decoded JSON for readability. Verify exact payloads against the 2C2P developer portal. Per-transaction pricing is not publicly published and is **not reconciled**.

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/2c2p)
- [Website](https://www.2c2p.com)
- [Documentation](https://developer.2c2p.com)
- [Plans](plans/2c2p-plans-pricing.yml)
- [Rate Limits](rate-limits/2c2p-rate-limits.yml)
- [Fin Ops](finops/2c2p-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

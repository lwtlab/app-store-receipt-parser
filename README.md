# Apple Receipt Parser

[![Latest Version on NPM][ico-version]][link-npm]
[![Scrutinizer build][ico-scrutinizer-build]][link-scrutinizer]
[![Scrutinizer quality][ico-scrutinizer-quality]][link-scrutinizer]
[![Scrutinizer coverage][ico-scrutinizer-coverage]][link-scrutinizer]
[![Software License][ico-license]](./LICENSE)
[![Total Downloads][ico-downloads]][link-downloads]

A lightweight TypeScript library for extracting transaction IDs from Apple's ASN.1 encoded Unified Receipts.

> [!IMPORTANT]
> This library is not a full-fledged receipt parser.
> It only extracts some information from Apple's ASN.1 encoded Unified Receipts.
> It does not work with the old-style transaction receipts.

> [!NOTE]
> Documentation for the version 1.x of the library can be found [here](https://github.com/tamtamchik/app-store-receipt-parser/tree/1.x/README.md).

## Installation

Using npm:

```shell
npm install @lwtlab/app-store-receipt-parser
```

Using yarn:

```shell
yarn add @lwtlab/app-store-receipt-parser
```

## Usage

```typescript
import { parseReceipt } from "@lwtlab/app-store-receipt-parser";

// Unified Receipt string
const receiptString = "MII...";
const data = parseReceipt(receiptString);

console.log(data);
// {
//   ENVIRONMENT: 'ProductionSandbox',
//   IN_APP_RECEIPTS: [
//     {
//       IN_APP_EXPIRES_DATE: '',
//       IN_APP_CANCELLATION_DATE: '',
//       IN_APP_QUANTITY: '020101',
//       IN_APP_WEB_ORDER_LINE_ITEM_ID: '020100',
//       IN_APP_TRANSACTION_ID: '2000000603939834',
//       IN_APP_ORIGINAL_TRANSACTION_ID: '2000000603939834',
//       IN_APP_PURCHASE_DATE: '2024-05-20T14:24:06Z',
//       IN_APP_ORIGINAL_PURCHASE_DATE: '2024-05-20T14:24:06Z',
//       IN_APP_PRODUCT_ID: 'net.thucydides.lwt.hear.lifetime'
//     },
//     {
//       IN_APP_CANCELLATION_DATE: '',
//       IN_APP_QUANTITY: '020101',
//       IN_APP_WEB_ORDER_LINE_ITEM_ID: '0207071afd4d39adb3',
//       IN_APP_TRANSACTION_ID: '2000000603961220',
//       IN_APP_ORIGINAL_TRANSACTION_ID: '2000000603894887',
//       IN_APP_PURCHASE_DATE: '2024-05-20T14:45:06Z',
//       IN_APP_ORIGINAL_PURCHASE_DATE: '2024-05-20T13:45:06Z',
//       IN_APP_EXPIRES_DATE: '2024-05-20T17:45:06Z',
//       IN_APP_PRODUCT_ID: 'net.thucydides.lwt.hear.yearly'
//     },
//     {
//       IN_APP_CANCELLATION_DATE: '',
//       IN_APP_QUANTITY: '020101',
//       IN_APP_WEB_ORDER_LINE_ITEM_ID: '0207071afd4d39adb2',
//       IN_APP_TRANSACTION_ID: '2000000603894887',
//       IN_APP_ORIGINAL_TRANSACTION_ID: '2000000603894887',
//       IN_APP_PURCHASE_DATE: '2024-05-20T13:45:06Z',
//       IN_APP_ORIGINAL_PURCHASE_DATE: '2024-05-20T13:45:06Z',
//       IN_APP_EXPIRES_DATE: '2024-05-20T14:45:06Z',
//       IN_APP_PRODUCT_ID: 'net.thucydides.lwt.hear.monthly'
//     }
//   ],
//   ORIGINAL_APP_VERSION: '1.0',
//   APP_VERSION: '1.0.3',
//   OPAQUE_VALUE: '0de406e477e58c820500623f96a71faf',
//   SHA1_HASH: '13475b0e82b1b0f5156092aa6831884d23b0f100',
//   RECEIPT_CREATION_DATE: '2024-05-21T09:12:52Z',
//   ORIGINAL_PURCHASE_DATE: '2013-08-01T07:00:00Z',
//   BUNDLE_ID: 'net.thucydides.lwt.hear'
// }
```

## Special Thanks

- [@Jurajzovinec](https://github.com/Jurajzovinec) for his superb contribution to the project.
- [@fechy](https://github.com/fechy) for bringing environment variable support to the lib.

## Contributing

Pull requests are always welcome. If you have bigger changes, please open an issue first to discuss your ideas.

## License

Apple Receipt Parser is [MIT licensed](./LICENSE).

## Third-Party Licenses

This project uses `ASN1.js`, licensed under the BSD-3-Clause License. The license text can be found in [LICENSE](./LICENSE).

---

[![Buy Me A Coffee][ico-coffee]][link-coffee]

[ico-coffee]: https://img.shields.io/badge/Buy%20Me%20A-Coffee-%236F4E37.svg?style=flat-square
[ico-version]: https://img.shields.io/npm/v/@tamtamchik/app-store-receipt-parser.svg?style=flat-square
[ico-license]: https://img.shields.io/npm/l/@tamtamchik/app-store-receipt-parser.svg?style=flat-square
[ico-downloads]: https://img.shields.io/npm/dt/@tamtamchik/app-store-receipt-parser.svg?style=flat-square
[ico-scrutinizer-build]: https://img.shields.io/scrutinizer/build/g/tamtamchik/app-store-receipt-parser/main.svg?style=flat-square
[ico-scrutinizer-quality]: https://img.shields.io/scrutinizer/quality/g/tamtamchik/app-store-receipt-parser/main.svg?style=flat-square
[ico-scrutinizer-coverage]: https://img.shields.io/scrutinizer/coverage/g/tamtamchik/app-store-receipt-parser/main.svg?style=flat-square
[link-coffee]: https://www.buymeacoffee.com/tamtamchik
[link-npm]: https://www.npmjs.com/package/@tamtamchik/app-store-receipt-parser
[link-downloads]: https://www.npmjs.com/package/@tamtamchik/app-store-receipt-parser
[link-scrutinizer]: https://scrutinizer-ci.com/g/tamtamchik/app-store-receipt-parser/

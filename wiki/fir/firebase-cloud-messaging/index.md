---
title: Firebase Cloud Messaging
layout: wiki-page
tags: [firebase, fcm, messaging, notification, push-notification]
---

## Prosedur Umum
### Memulai Firebase Project

### Firebase Javascript API (Client Web App)
#### Catatan:
- Firebase Cloud Messaging Client App https://firebase.google.com/docs/cloud-messaging/js/client
- **Cloud Messaging dapat digunakan tanpa harus menggunakan Firebase Auth**. Beda https://firebase.google.com/docs/auth/web/start dengan https://firebase.google.com/docs/cloud-messaging/js/client

#### Prosedur penerimaan pesan di aplikasi client:
  - Instalasi dan inisiasi firebase js library
    - [Instalasi dan inisiasi firebase js ke web client](https://firebase.google.com/docs/web/setup#add-sdk-and-initialize)
    - [Membuat firebaseConfig](https://firebase.google.com/docs/web/learn-more#config-object)
  - [Konfigurasi firebase messaging web client](https://firebase.google.com/docs/cloud-messaging/js/client)
    <details>
      <summary>Lihat Kode</summary>

      ```javascript
      import { initializeApp } from "firebase/app";
      import { getMessaging } from "firebase/messaging";

      // TODO: Replace the following with your app's Firebase project configuration
      // See: https://firebase.google.com/docs/web/learn-more#config-object
      const firebaseConfig = {
        // ...
      };

      // Initialize Firebase
      const app = initializeApp(firebaseConfig);


      // Initialize Firebase Cloud Messaging and get a reference to the service
      const messaging = getMessaging(app);
      ```

    </details>
  - Instalasi service worker Firebase firebase-messaging-sw.js
  - Client menyetujui pengiriman notifikasi
    - [Contoh script NotifyMe()](https://developer.mozilla.org/en-US/docs/Web/API/Notification/requestPermission)

### Firebase Admin SDK
#### Catatan:
  - Untuk pengiriman pesan, menggunakan Firebase Admin SDK for FCM
  - Terdiri dari 2 komponen
    - **FCM backend** disediain Google
    - Server app milik kita / [Trusted Server Environment](https://firebase.google.com/docs/cloud-messaging/server#firebase-admin-sdk-for-fcm)
  - Paling lengkap librarynya yang Node.js

#### Prosedur pengiriman pesan:
  1. Server app milik kita mengirimkan **message requests** ke **FCM backend**
  2. **FCM backend** mengirimkan pesan ke aplikasi client di devicenya client (PWA / Android / Iphone)

## Implementasi di React
- https://buttercms.com/blog/react-firebase-google-analytics-set-up-log-events

## Istilah
- console
- Firebase Admin SDK

## Artikel Terkait
- [JWT](/wiki/wiki/jwt/jwt/)
- [Public JSON Web Key Set](https://docs.cidaas.com/standard-endpoints/server-jwk-set.html)
- [Firebase - Authenticate with Firebase in JavaScript Using a Custom Authentication System](https://firebase.google.com/docs/auth/web/custom-auth)
- [Firebase - Creating custom tokens using a third-party JWT library](https://cloud.google.com/identity-platform/docs/admin/create-custom-tokens#creating_custom_tokens_using_a_third-party_jwt_library)
- [Dev.to - React & Firebase: Add Firebase to a React App](https://dev.to/farazamiruddin/react-firebase-add-firebase-to-a-react-app-4nc9)
- [Symmetric Key](https://github.com/Spomky-Labs/jose/blob/master/doc/object/jwk.md#symmetric-key-oct)
- [How to create JWKS public/private key pair in python?](https://stackoverflow.com/questions/67589495/how-to-create-jwks-public-private-key-pair-in-python)
- [Firebase Analytics](https://firebase.google.com/docs/reference/js/analytics)

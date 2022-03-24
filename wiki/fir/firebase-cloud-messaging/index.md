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
  - [Membuat VAPID key untuk otorisasi send message request ke push service](https://firebase.google.com/docs/cloud-messaging/js/client#configure_web_credentials_with)
  - [Instalasi service worker Firebase firebase-messaging-sw.js](https://firebase.google.com/docs/cloud-messaging/js/send-multiple#handle_messages_when_your_web_app_is_in_the_foreground), [Receive messages in a JavaScript client](https://firebase.google.com/docs/cloud-messaging/js/receive)
    <details>
      <summary>Lihat Kode</summary>
  
      ```javascript
      import { initializeApp } from "firebase/app";
      import { getMessaging } from "firebase/messaging/sw";

      // Initialize the Firebase app in the service worker by passing in
      // your app's Firebase config object.
      // https://firebase.google.com/docs/web/setup#config-object
      const firebaseApp = initializeApp({
        apiKey: 'api-key',
        authDomain: 'project-id.firebaseapp.com',
        databaseURL: 'https://project-id.firebaseio.com',
        projectId: 'project-id',
        storageBucket: 'project-id.appspot.com',
        messagingSenderId: 'sender-id',
        appId: 'app-id',
        measurementId: 'G-measurement-id',
      });

      // Retrieve an instance of Firebase Messaging so that it can handle background
      // messages.
      const messaging = getMessaging(firebaseApp);
      ```
  
    </details>
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
- Pada React PWA, untuk service worker gunakan yang telah disediakan React PWA, pada bagian registerValidSW
  - gunakan function getToken(vapidKey, serviceWorkerRegistration) dari firebase/messaging untuk memilih service worker tersebut, bukan menggunakan default firebase-messaging-sw.js
- https://buttercms.com/blog/react-firebase-google-analytics-set-up-log-events

## Istilah
- console
- Firebase Admin SDK

## Artikel Terkait
- [Firebase - Send messages to multiple devices](https://firebase.google.com/docs/cloud-messaging/js/send-multiple)
- [JWT](/wiki/wiki/jwt/jwt/)
- [Public JSON Web Key Set](https://docs.cidaas.com/standard-endpoints/server-jwk-set.html)
- [Firebase - Authenticate with Firebase in JavaScript Using a Custom Authentication System](https://firebase.google.com/docs/auth/web/custom-auth)
- [Firebase - Creating custom tokens using a third-party JWT library](https://cloud.google.com/identity-platform/docs/admin/create-custom-tokens#creating_custom_tokens_using_a_third-party_jwt_library)
- [Dev.to - React & Firebase: Add Firebase to a React App](https://dev.to/farazamiruddin/react-firebase-add-firebase-to-a-react-app-4nc9)
- [Symmetric Key](https://github.com/Spomky-Labs/jose/blob/master/doc/object/jwk.md#symmetric-key-oct)
- [How to create JWKS public/private key pair in python?](https://stackoverflow.com/questions/67589495/how-to-create-jwks-public-private-key-pair-in-python)
- [Firebase Analytics](https://firebase.google.com/docs/reference/js/analytics)

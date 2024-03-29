---
title: Push Notification 
layout: wiki-page
tags: [push, notification, android, browser, notif]
---

## Definisi
- Push API : API di browser untuk server kirim message ke client
- Notification API : API di browser untuk client kirim notification ke client 

## Push API
- Butuh
  - HTTPS
  - VAPID keys

### Objek Browser Terkait
- [Navigator - window.navigator](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)
  - [ServiceWorkerContainer - window.navigator.serviceWorker](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer)
  - [ServiceWorkerRegistration](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration)
    - [PushManager - ServiceWorkerRegistration.pushManager](https://developer.mozilla.org/en-US/docs/Web/API/PushManager): Interface dari Push API. Ngelola push message dari server.
      - getSubscription()
      - subscribe()
    - [PushSubscription](https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription)

### Tahapan
Sisi client
1. Registrasi [service worker](/wiki/wiki/ser/service-worker)
2. Cek o. Subscription udah ada atau belum
   - Jika belum, ambil VAPID public key dari server
3. Bikin o. Subscription pake VAPID public key via pushManager
4. Kirim o. Subscription ke server, untuk dipake server kirim push message ke client 

Sisi server
1. Buat VAPID public & private keys
2. Buat route http dimana client bisa minta VAPID public key
3. Buat route http dimana client bisa kirim info Subscription nya
4. Buat route http dimana client bisa minta hapus Subscription nya
5. Pake Subscription info untuk kirim push notifications ke subscriber

## Catatan
- Push API
- Web socket dapat digunakan untuk push data ke client menggunakan Push API

## Artikel Terkait
- [Google - The Web Push Protocol](https://developers.google.com/web/fundamentals/push-notifications/web-push-protocol)
- [Notifications, Server Side Events, Web Sockets (SocketIO), and Push API](https://abaganon.com/tutorials/sse_ws_push.html)
- [Push Backend - Gorush](https://github.com/appleboy/gorush)
- [ProgrammableWeb - What Is a WebSockets Push-Styled API and How Does It Work?](https://www.programmableweb.com/news/what-websockets-push-styled-api-and-how-does-it-work/analysis/2017/04/20)
- [Google - Sending Messages with Web Push Libraries](https://developers.google.com/web/fundamentals/push-notifications/sending-messages-with-web-push-libraries)

### Praktik
- [How to make PWAs re-engageable using Notifications and Push](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push)
- [Add push notifications to your web app with Node.js and service workers](https://pusher.com/tutorials/push-notifications-node-service-workers/#prerequisites)
- [A 5-minute guide to Push notifications in Progressive Web Apps](https://www.educative.io/blog/5-minute-guide-to-push-notifications-in-pwa)
- [React js PWA tutorial #12 push notification popup | Progressive web app](https://www.youtube.com/watch?v=gvN3SA3CaWE)

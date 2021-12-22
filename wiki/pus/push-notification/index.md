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

### Objek Terkait

### Tahapan
Sisi client
1. Registrasi [service worker](/wiki/wiki/ser/service-worker)
2. Cek o. Subscription udah ada atau belum
   - Jika belum, ambil VAPID public key dari server
3. Bikin o. Subscription pake VAPID public key via pushManager
4. Kirim o. Subscription ke server, untuk dipake server kirim push message ke client 

## Catatan
- Push API
- Web socket dapat digunakan untuk push data ke client menggunakan Push API

## Artikel Terkait
[HMAC Algorithm in Computer Network](https://www.geeksforgeeks.org/hmac-algorithm-in-computer-network/)
[Push Backend - Gorush](https://github.com/appleboy/gorush)
[Notifications, Server Side Events, Web Sockets (SocketIO), and Push API](https://abaganon.com/tutorials/sse_ws_push.html)
[ProgrammableWeb - What Is a WebSockets Push-Styled API and How Does It Work?](https://www.programmableweb.com/news/what-websockets-push-styled-api-and-how-does-it-work/analysis/2017/04/20)

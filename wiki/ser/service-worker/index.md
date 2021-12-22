---
title: Service Worker
layout: wiki-page
tags: [service-worker, pwa, notifications]
---

## Definisi

### Dari Berbagai Sumber
- Google web fundamentals: <b>Script</b> that your browser <b>runs in the background</b>, separate from a web page, <b>opening the door to features that don't need a web page or user interaction</b>
- Google PWA: <b>JavaScript file</b> that runs separately from the main browser [thread](/wiki/wiki/thr/thread/), intercepting <b>network requests</b>, <b>caching</b> or retrieving resources from the cache, and <b>delivering push messages</b> 
- Mozilla dev: Event-driven worker registered against an origin and a path. It takes the form of a <b>JavaScript file</b> that can control the web-page/site that it is associated with, intercepting and modifying navigation and resource requests, and caching resources in a very granular fashion to give you complete control over how your app behaves in certain situations (the most obvious one being when the network is not available).

### Formulasi
- File Javascript
- Jalan di background dengan thread terpisah
- Ngatur hal-hal yang ga butuh interaksi UI
  - proxy network
  - caching
  - menangkap push message
  - mengirim notification

## Penggunaan
- Untuk menangkap Push API dari server ke client
- Untuk mengirim Notif API dari client ke client

## Artikel Terkait
- [Google - Service Workers: an Introduction](https://developers.google.com/web/fundamentals/primers/service-workers) 
- [Google - Introduction to Service Worker](https://developers.google.com/web/ilt/pwa/introduction-to-service-worker)
- [Mozilla - Service Worker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
- [Google - Web Push Notifications: Timely, Relevant, and Precise](https://developers.google.com/web/fundamentals/push-notifications)
- [Mozilla - Using the Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API)
- [Mozilla - Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)
- [Notifications, Server Side Events, Web Sockets (SocketIO), and Push API](https://abaganon.com/tutorials/sse_ws_push.html)

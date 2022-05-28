---
title: AWS DynamoDB
layout: wiki-page
tags: [aws, dynamodb, nosql]
---

## Catatan
- Rekomendasi desain basis data di DynamoDB adalah single table design
- Timestamp untuk query dan range bisa dalam format string
- Timestamp number yang ditaruh di atribut yang di TTL kan adalah waktu penghapusan item tersebut.
  Jadi yang ditaruh di kolom TTL itu misal timestamp 2 minggu dari saat ini

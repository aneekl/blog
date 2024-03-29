---
title: "เก็บกวาด Selfhosted"
slug: "cleanup-my-server"
weight: 5
author: "Nattapong.K"
date: 2022-01-29T12:17:31+07:00
description: "โฮสตัวเองไปวันๆ"
tags: ["Selfhosted"]
categories: ["Diary"]
draft: false
---
วันลบไฟล์ไปก้อนใหญ่
<!--more-->

### เผลอลบไฟล์ไปแล้ว งั้นเริ่มใหม่เลยดีกว่า

เมื่อวันก่อนเผลอลบไฟล์ในเซิฟเวอร์ของที่บ้านไป เลยคิดว่าคงถึงเวลาที่จะต้องยกเครื่องใหม่แล้วมั้ง ก็เลยลง OS ใหม่แล้วเริ่มใหม่

จะเรียกเซิฟเวอร์ก็อะไรอยู่เพราะตัวเครื่องเป็นแค่ Raspberry Pi4 8GB ซื้อมาตั้งแต่ราคามันถูกๆ ไม่แพงแบบปัจจุบัน ที่ราคา 2,600 บาท ปัจจุบันตัว 4GB ราคาก็ปาไป 5พัน 6พันแล้ว OS เดิมเป็น Dietpi 32bit จะลงใหม่เป็น 64bit ตัวเซอร์วิส 90% จะเป็น Docker แทบทั้งหมด

ต่อ SSD ไว้บูตกับต่อ HDD 12 TB ไว้เก็บข้อมูล ซื้อมาตอนราคายังไม่พุ่งเหมือนกัน โควิดนี่พาอุปกรณ์อิเล็กทรอนิกส์ราคาขึ้นยกแผงจริงๆ โดยเฉพาะ HDD นี่มีอยู่ช่วงหนึ่งที่ราคาพุ่งไปไกลมากเพราะพวกซื้อไปขุดเหรียญกัน แล้วพ่อค้าก็เลยซื้อไปตุนเก็งกำไรกัน ราคามันถึงพุ่งแบบที่เห็น

อย่างที่บอกไว้ว่าจะเริ่มต้นใหม่ใน 64bit OS นึกได้ว่า [Nginx Proxy Manager](https://nginxproxymanager.com/) นี่วุ่นวายเอาเรื่องเวลาจะลงพวกเซอร์วิสใหม่ เพราะหลังจากลงใหม่แล้วต้องเข้าเว็บไปสร้าง routes ชี้ไปที่ตัวเซอร์วิสนั้นเองอีก

#### Traefik

[Traefik](https://doc.traefik.io/traefik/) เป็นโปรแกรมคล้ายๆ Nginx Proxy Manager นี่แหละ แต่แทนที่เราจะเข้าเว็บไปชี้ทางหลังจากรันเซอร์วิส เราก็กำหนดลงไปในเซอร์วิสนั่นเลยว่าจะให้เป็นยังไง ตัวโปรแกรมมันจะคอยอ่านแล้วตั้งให้ ไม่ต้องทำซ้ำซ้อน แต่ข้อจำกัดคือต้องอยู่ใน Network เดียวกันเหมือนเดิม ส่วนที่ยากที่สุดคือการทำความเข้าใจ เพราะตัวเองก็ไม่ค่อยเข้าใจเหมือนกัน อาศัยดูคริปยูทูปพวกนี้แล้วก็อปวางเอา ถ้ามันใช้ได้ก็โอเคแล้ว

[Is this the BEST Reverse Proxy for Docker? // Traefik Tutorial - YouTube](https://www.youtube.com/watch?v=wLrmmh1eI94&t=559s)

[Put Wildcard Certificates and SSL on EVERYTHING - Traefik Tutorial - YouTube](https://www.youtube.com/watch?v=liV3c9m_OX8)

---

ถ้าผ่านขั้นตอนที่ยากที่สุดไปได้ ซึ่งก็คือการทำความเข้าใจมันไปได้ก็ง่ายแล้ว ไม่ต้องทำซ้ำซ้อนหลายขั้นตอน จากนั้นก็ก็อปวางตั้งค่าของเซอร์วิสทั้งหมดที่ใช้เว็บไว้ แล้วลง OS ใหม่ จากนั้นก็เอาไปวางที่เดิมแล้วรันก็เรียบร้อย พร้อมใช้งานเหมือนเดิม Docker นี่มันสะดวกจริงๆ

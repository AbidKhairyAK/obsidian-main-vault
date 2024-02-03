---
page-title: "Devops - Monorepo, menurut saya... // mazipan.space"
url: https://mazipan.space/monorepo-menurut-saya
date: "2023-08-02 14:39:33"
---
## 2023-08-02 14:42:14

> ## Monorepo seharusnya
> 
> Monorepo memiliki use-case terbaik bagi repo-repo semacam Babel dan beberapa open-source repo yang kita sudah sebutkan di awal. Mereka punya banyak (terlalu banyak sih) package, saling terkait satu dengan yang lain, ukurannya mini-mini.
> 
> Monorepo bisa menjadi sangat brutal ketika perkembangannya tidak terkontrol atau tidak terduga di awal. Dikira akan berisi satu-dua package, ternyata ada 50 package pada akhirnya.
> 
> Bagi saya, monorepo sangat baik untuk package, dan bukan untuk aplikasi. Package yang saya maksud adalah pustaka-pustaka yang akan didistribusikan. Aplikasi sendiri adalah satu website utuh yang berisi banyak alur di dalamnya. Cukup langka ada satu aplikasi dependent ke aplikasi lain, dan memang tidak seharusnya. Ya kalau aplikasinya satu dua okelah ya. Kalau aplikasinya ada puluhan, sudahlah jangan berani-berani bermain api.

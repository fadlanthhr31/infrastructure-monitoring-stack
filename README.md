# Enterprise Infrastructure Monitoring & Alerting System

## Overview
Proyek ini mendokumentasikan implementasi sistem pemantauan infrastruktur IT Operasional skala enterprise. Sistem ini dirancang untuk melakukan pemantauan kesehatan server secara real-time, pengelolaan log terpusat, serta pengiriman notifikasi gangguan otomatis (*automated alerting*) guna memastikan ketersediaan layanan (*uptime*) dan mempercepat proses penanganan insiden (*Mean Time to Resolve / MTTR*).

---

## Tech Stack & Core Modules
* **Zabbix**: Digunakan untuk pemantauan kesehatan server, ketersediaan jaringan, dan konsumsi sumber daya (*CPU, RAM, Disk, Network I/O*).
* **Elasticsearch & Kibana**: Digunakan untuk pengumpulan, pemrosesan, dan analisis log sistem/aplikasi secara terpusat untuk mempermudah deteksi anomali.
* **Automated Alerting**: Integrasi skrip notifikasi otomatis yang meneruskan informasi gangguan secara *real-time* ke saluran komunikasi tim operasional.

---

## Key Implementations & Highlights

### 1. Infrastructure & Server Monitoring (Zabbix)
* Menerapkan konfigurasi Zabbix Agent pada node server internal.
* Mengatur *trigger* dan ambang batas (*threshold*) kustom untuk performa sistem.
* Mengelompokkan tingkat keparahan insiden (*Severity Levels*: Information, Warning, High, Disaster) guna mengurangi *alert fatigue*.

### 2. Centralized Log Management (Elasticsearch & Kibana)
* Melakukan agregasi log dari berbagai server ke Elasticsearch.
* Membuat struktur query (DSL) dan *index patterns* di Kibana untuk mempercepat pencarian *root cause* saat terjadi *error*.

### 3. Real-Time Alerting Engine
* Mengintegrasikan notifikasi otomatis ketika status sistem mengalami gangguan (*DOWN*) maupun saat sistem kembali normal (*RECOVERY*).
* Memformat pesan alert agar mencakup detail metrik kritis untuk mempermudah analisis awal oleh tim on-call.

---

## Key Benefits
* **Proactive Monitoring**: Memungkinkan deteksi potensi kegagalan sistem sebelum berdampak pada pengguna akhir.
* **Centralized Visibility**: Memberikan visibilitas menyeluruh terhadap kondisi infrastruktur dan log aplikasi dalam satu platform.
* **Faster Incident Response**: Mempercepat respon dan pemulihan gangguan melalui pemantauan dan notifikasi terintegrasi.

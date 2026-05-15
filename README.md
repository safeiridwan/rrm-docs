# Proposal Aplikasi Backoffice Travel Umroh

---

# 1. Overview

## Latar Belakang

Operasional travel umroh umumnya melibatkan banyak proses administratif, seperti:

- Pendaftaran jamaah
- Pengelolaan paket keberangkatan
- Booking seat
- Pembayaran DP / cicilan / pelunasan
- Pengelolaan dokumen passport
- Penyusunan manifest
- Monitoring referral reward
- Monitoring revenue perusahaan

Proses yang masih manual berpotensi menimbulkan:

- Human error
- Double booking seat
- Data pembayaran tidak sinkron
- Sulit monitoring jamaah belum lunas
- Sulit tracking referral dan free seat

Aplikasi ini dibuat untuk membantu operasional travel agar lebih terstruktur, cepat, dan terukur.

---

## Struktur Menu Sistem

```text
Dashboard

Master Data
 ├── Jamaah
 ├── Paket Program
 ├── Agen

Booking
 ├── Booking
 ├── Seat Monitoring

Finance
 ├── Invoice
 ├── Payment
 ├── Outstanding

Operations
 ├── Manifest
 ├── Passport Documents

Marketing
 ├── Referral Reward

Reports
 ├── Revenue
 ├── Departure Report

Settings
 ├── User Management
 ├── Roles & Permission
```

---

# 2. Effort Task, Mandays & Cost Estimation

## Development Rate

| Item | Value |
|------|------:|
| Standard Rate | Rp 375.000 / MD |
| Special Discount Rate | Rp 250.000 / MD |
| Discount | Rp 125.000 / MD (33%) |
| Total Mandays | 35.5 MD |
| Total Development Cost | Rp 8.875.000 |

---

## Notes

- Harga normal pengembangan adalah **Rp 375.000 / manday**
- Untuk proyek ini diberikan **harga khusus Rp 250.000 / manday**
- Total nilai proyek sebelum diskon:

  **35.5 MD × Rp 375.000 = Rp 13.312.500**

- Total nilai proyek setelah diskon:

  **35.5 MD × Rp 250.000 = Rp 8.875.000**

- Total diskon yang diberikan:

  **Rp 4.437.500 (~33%)**

---

| No | Menu | Task | Mandays | Cost |
|----|------|------|---------:|------:|
| 1 | Dashboard | Dashboard KPI Summary | 1 | Rp 250.000 |
| 2 | Dashboard | Recent Activity | 1 | Rp 250.000 |
| 3 | Dashboard | Alert Notification | 1 | Rp 250.000 |
| 4 | Master Data > Jamaah | Create Data Jamaah | 0.5 | Rp 125.000 |
| 5 | Master Data > Jamaah | Read List Data Jamaah | 0.25 | Rp 62.500 |
| 6 | Master Data > Jamaah | Read Detail Data Jamaah | 0.25 | Rp 62.500 |
| 7 | Master Data > Jamaah | Update Data Jamaah | 0.25 | Rp 62.500 |
| 8 | Master Data > Jamaah | Delete Data Jamaah | 0.25 | Rp 62.500 |
| 9 | Master Data > Jamaah | Search & Filter Jamaah | 0.5 | Rp 125.000 |
| 10 | Master Data > Jamaah | Upload Passport / Documents | 1 | Rp 250.000 |
| 11 | Master Data > Paket Program | Create Paket Program | 0.5 | Rp 125.000 |
| 12 | Master Data > Paket Program | Read List Paket Program | 0.25 | Rp 62.500 |
| 13 | Master Data > Paket Program | Read Detail Paket Program | 0.25 | Rp 62.500 |
| 14 | Master Data > Paket Program | Update Paket Program | 0.25 | Rp 62.500 |
| 15 | Master Data > Paket Program | Delete Paket Program | 0.25 | Rp 62.500 |
| 16 | Master Data > Paket Program | Package Quota Management | 0.5 | Rp 125.000 |
| 17 | Master Data > Paket Program | Package Price Management | 0.5 | Rp 125.000 |
| 18 | Master Data > Agen | Create Agen | 0.5 | Rp 125.000 |
| 19 | Master Data > Agen | Read List Agen | 0.25 | Rp 62.500 |
| 20 | Master Data > Agen | Read Detail Agen | 0.25 | Rp 62.500 |
| 21 | Master Data > Agen | Update Agen | 0.25 | Rp 62.500 |
| 22 | Master Data > Agen | Delete Agen | 0.25 | Rp 62.500 |
| 23 | Master Data > Agen | Agent Performance View | 0.5 | Rp 125.000 |
| 24 | Booking > Booking | Create Booking | 0.5 | Rp 125.000 |
| 25 | Booking > Booking | Read Booking List | 0.25 | Rp 62.500 |
| 26 | Booking > Booking | Read Booking Detail | 0.25 | Rp 62.500 |
| 27 | Booking > Booking | Update Booking Status | 0.25 | Rp 62.500 |
| 28 | Booking > Booking | Cancel Booking | 0.25 | Rp 62.500 |
| 29 | Booking > Booking | Booking Validation Engine | 1 | Rp 250.000 |
| 30 | Booking > Seat Monitoring | Seat Occupancy Calculation | 1 | Rp 250.000 |
| 31 | Booking > Seat Monitoring | Seat Availability Monitoring | 0.5 | Rp 125.000 |
| 32 | Booking > Seat Monitoring | Seat Alert | 0.5 | Rp 125.000 |
| 33 | Finance > Invoice | Generate Invoice | 1 | Rp 250.000 |
| 34 | Finance > Invoice | Preview Invoice | 0.5 | Rp 125.000 |
| 35 | Finance > Invoice | Download PDF Invoice | 1 | Rp 250.000 |
| 36 | Finance > Payment | Create DP Payment | 0.5 | Rp 125.000 |
| 37 | Finance > Payment | Create Installment Payment | 0.5 | Rp 125.000 |
| 38 | Finance > Payment | Create Full Payment | 0.5 | Rp 125.000 |
| 39 | Finance > Payment | Upload Payment Proof | 1 | Rp 250.000 |
| 40 | Finance > Payment | Payment History | 0.5 | Rp 125.000 |
| 41 | Finance > Outstanding | Outstanding List | 0.5 | Rp 125.000 |
| 42 | Finance > Outstanding | Outstanding Detail | 0.5 | Rp 125.000 |
| 43 | Finance > Outstanding | H-35 Due Monitoring | 1 | Rp 250.000 |
| 44 | Finance > Outstanding | Outstanding Alert | 0.5 | Rp 125.000 |
| 45 | Operations > Manifest | Generate Excel Manifest | 1 | Rp 250.000 |
| 46 | Operations > Manifest | Generate PDF Manifest | 1 | Rp 250.000 |
| 47 | Operations > Manifest | Package Filter | 0.5 | Rp 125.000 |
| 48 | Operations > Passport Documents | Download Single Passport | 0.5 | Rp 125.000 |
| 49 | Operations > Passport Documents | Bulk Download ZIP | 1.5 | Rp 375.000 |
| 50 | Marketing > Referral Reward | Assign Referrer | 0.5 | Rp 125.000 |
| 51 | Marketing > Referral Reward | Referral Tracking | 1 | Rp 250.000 |
| 52 | Marketing > Referral Reward | Referral Qualification Engine | 2 | Rp 500.000 |
| 53 | Marketing > Referral Reward | Claim Free Seat | 1 | Rp 250.000 |
| 54 | Settings > User Management | Create User | 0.5 | Rp 125.000 |
| 55 | Settings > User Management | Read User List | 0.25 | Rp 62.500 |
| 56 | Settings > User Management | Update User | 0.25 | Rp 62.500 |
| 57 | Settings > User Management | Disable User | 0.25 | Rp 62.500 |
| 58 | Settings > Roles & Permission | Create Role | 0.5 | Rp 125.000 |
| 59 | Settings > Roles & Permission | Assign Permission | 1 | Rp 250.000 |
| 60 | Settings > Roles & Permission | Update Permission | 0.5 | Rp 125.000 |
| 61 | System | Functional Testing | 3 | Rp 750.000 |
| 62 | System | Bug Fixing | 2 | Rp 500.000 |
| 63 | System | Deployment | 2 | Rp 500.000 |
|  |  | **TOTAL** | **35.5 MD** | **Rp 8.875.000** |

---
# 3. Project Timeline

## Project Information

| Item | Value |
|------|------|
| Project Start | 01 June 2026 |
| Capacity | 4 Man Days / Week |
| Total Effort | 35.5 Man Days |
| Estimated Duration | 9 Weeks |
| Estimated Finish | 03 August 2026 |

---

## Development Timeline

| Week | Period | Scope | MD |
|------|------|------|----:|
| Week 1 | 01 Jun - 07 Jun 2026 | Project Setup, Authentication, Dashboard | 4 |
| Week 2 | 08 Jun - 14 Jun 2026 | Master Data → Jamaah | 4 |
| Week 3 | 15 Jun - 21 Jun 2026 | Master Data → Paket Program + Agen | 4 |
| Week 4 | 22 Jun - 28 Jun 2026 | Booking + Seat Monitoring | 4 |
| Week 5 | 29 Jun - 05 Jul 2026 | Finance → Invoice | 4 |
| Week 6 | 06 Jul - 12 Jul 2026 | Finance → Payment | 4 |
| Week 7 | 13 Jul - 19 Jul 2026 | Finance → Outstanding | 4 |
| Week 8 | 20 Jul - 26 Jul 2026 | Operations + Marketing | 4 |
| Week 9 | 27 Jul - 03 Aug 2026 | Settings + Testing + Deployment | 3.5 |

---

## Timeline Overview

```text
Jun 2026                                     Jul 2026                              Aug 2026
|---------------------------------------------|--------------------------------------|

W1  ████  Setup + Dashboard
W2  ████  Jamaah
W3  ████  Paket Program + Agen
W4  ████  Booking + Seat Monitoring
W5  ████  Invoice
W6  ████  Payment
W7  ████  Outstanding
W8  ████  Operations + Referral
W9  ███▌  Settings + Testing + Deployment
```

---

## Delivery Milestones

### Milestone 1 — Core Master Data
**Target: Week 3**

Completed modules:

- Dashboard
- Jamaah
- Paket Program
- Agen

---

### Milestone 2 — Core Transaction
**Target: Week 7**

Completed modules:

- Booking
- Seat Monitoring
- Invoice
- Payment
- Outstanding

---

### Milestone 3 — Go Live
**Target: Week 9**

Completed modules:

- Operations
- Referral Reward
- Settings
- Testing
- Production Deployment

---

# 4. ERD

```mermaid
erDiagram

    AGENTS ||--o{ PILGRIMS : owns
    PILGRIMS ||--o{ BOOKINGS : books
    PACKAGES ||--o{ BOOKINGS : contains

    BOOKINGS ||--|| INVOICES : billed
    INVOICES ||--o{ PAYMENTS : receives

    PILGRIMS ||--o{ DOCUMENTS : has
    PILGRIMS ||--o{ REWARDS : earns


    AGENTS {
        bigint id PK
        string name
        string phone
    }

    PILGRIMS {
        bigint id PK
        bigint agent_id FK
        string full_name
        string passport_number
        string phone
    }

    PACKAGES {
        bigint id PK
        string name
        date departure_date
        int quota
        decimal base_price
    }

    BOOKINGS {
        bigint id PK
        bigint pilgrim_id FK
        bigint package_id FK
        string booking_type
        string status
        decimal agreed_price
    }

    INVOICES {
        bigint id PK
        bigint booking_id FK
        string invoice_number
        decimal total_amount
        decimal paid_amount
        decimal outstanding_amount
    }

    PAYMENTS {
        bigint id PK
        bigint invoice_id FK
        decimal amount
        string payment_type
        datetime paid_at
    }

    DOCUMENTS {
        bigint id PK
        bigint pilgrim_id FK
        string file_url
    }

    REWARDS {
        bigint id PK
        bigint pilgrim_id FK
        string status
    }
```

---

# 5. High Level Business Sequence Diagram

---

# Dashboard

```mermaid
sequenceDiagram

    actor User as Admin / Owner
    participant System as Backoffice System

    User->>System: Login ke sistem
    User->>System: Buka dashboard

    System->>System: Ambil data jamaah aktif
    System->>System: Hitung revenue berjalan
    System->>System: Hitung seat tersedia
    System->>System: Hitung outstanding payment
    System->>System: Ambil aktivitas terbaru

    System-->>User: Tampilkan dashboard summary
```

---

# Master Data → Jamaah

```mermaid
sequenceDiagram

    actor Admin as Staff Admin
    participant System as Backoffice System

    Admin->>System: Tambah data jamaah

    System->>System: Validasi data identitas
    System->>System: Validasi passport
    System->>System: Simpan data jamaah

    System-->>Admin: Data berhasil disimpan

    Admin->>System: Upload passport / dokumen

    System->>System: Simpan dokumen

    System-->>Admin: Dokumen berhasil tersimpan
```

---

# Master Data → Paket Program

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Tambah paket keberangkatan

    System->>System: Validasi tanggal keberangkatan
    System->>System: Validasi quota seat
    System->>System: Simpan paket

    System-->>Admin: Paket berhasil dibuat

    Admin->>System: Lihat detail paket

    System-->>Admin: Informasi quota, booked, available
```

---

# Master Data → Agen

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Tambah / ubah data agen

    System->>System: Validasi data agen
    System->>System: Simpan data agen

    System-->>Admin: Data agen tersimpan

    Admin->>System: Lihat performa agen

    System-->>Admin: Total jamaah & omzet agen
```

---

# Booking

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Pilih jamaah
    Admin->>System: Pilih paket

    System->>System: Cek quota paket
    System->>System: Cek seat tersedia
    System->>System: Cek status jamaah

    alt Seat tersedia
        System-->>Admin: Seat tersedia

        Admin->>System: Konfirmasi booking

        System->>System: Reserve seat
        System->>System: Buat data booking
        System->>System: Generate invoice awal

        System-->>Admin: Booking berhasil
    else Seat penuh
        System-->>Admin: Seat tidak tersedia
    end
```

---

# Seat Monitoring

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Buka seat monitoring

    System->>System: Hitung quota total
    System->>System: Hitung seat booked
    System->>System: Hitung seat available

    System-->>Admin: Tampilkan occupancy seat
```

---

# Finance → Invoice

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Generate invoice

    System->>System: Ambil data booking
    System->>System: Hitung harga paket
    System->>System: Hitung diskon / reward

    System-->>Admin: Preview invoice

    Admin->>System: Download invoice

    System-->>Admin: File invoice PDF
```

---

# Finance → Payment

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Input pembayaran

    System->>System: Validasi nominal
    System->>System: Update histori pembayaran
    System->>System: Hitung sisa tagihan
    System->>System: Update status invoice

    alt Sudah lunas
        System->>System: Update status paid off
    else Belum lunas
        System->>System: Update outstanding balance
    end

    System-->>Admin: Pembayaran berhasil tercatat
```

---

# Finance → Outstanding

```mermaid
sequenceDiagram

    actor User as Admin / Owner
    participant System

    User->>System: Buka outstanding payment

    System->>System: Ambil invoice aktif
    System->>System: Hitung sisa pembayaran
    System->>System: Cek deadline H-35

    System-->>User: Daftar jamaah belum lunas

    alt Melewati deadline
        System-->>User: Alert pembayaran terlambat
    end
```

---

# Operations → Manifest

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Pilih paket keberangkatan

    System->>System: Ambil jamaah confirmed
    System->>System: Ambil data passport
    System->>System: Susun manifest

    System-->>Admin: Preview manifest

    Admin->>System: Download manifest

    System-->>Admin: File Excel / PDF
```

---

# Operations → Passport Documents

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Pilih jamaah / paket

    System->>System: Ambil file passport
    System->>System: Compress file (ZIP)

    System-->>Admin: File siap diunduh
```

---

# Marketing → Referral Reward

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Input referral jamaah

    System->>System: Hubungkan referrer dengan jamaah baru

    loop Setiap jamaah melakukan DP
        System->>System: Hitung referral valid
    end

    alt Referral >= 4
        System->>System: Update status qualified
        System-->>Admin: Reward qualified
    else Belum memenuhi syarat
        System-->>Admin: Referral masih berjalan
    end

    Admin->>System: Claim free seat

    System->>System: Generate booking reward

    System-->>Admin: Reward berhasil digunakan
```

---

# Reports → Revenue

```mermaid
sequenceDiagram

    actor Owner
    participant System

    Owner->>System: Pilih periode laporan

    System->>System: Ambil seluruh pembayaran
    System->>System: Hitung revenue per paket
    System->>System: Hitung revenue per agen

    System-->>Owner: Tampilkan revenue report
```

---

# Reports → Departure Report

```mermaid
sequenceDiagram

    actor Owner
    participant System

    Owner->>System: Pilih periode keberangkatan

    System->>System: Ambil booking confirmed
    System->>System: Kelompokkan per paket

    System-->>Owner: Tampilkan departure report
```

---

# Settings → User Management

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Tambah user baru

    System->>System: Validasi email
    System->>System: Generate akun

    System-->>Admin: User berhasil dibuat
```

---

# Settings → Roles & Permission

```mermaid
sequenceDiagram

    actor Admin
    participant System

    Admin->>System: Atur role user

    System->>System: Update permission
    System->>System: Terapkan hak akses

    System-->>Admin: Permission berhasil diperbarui
```

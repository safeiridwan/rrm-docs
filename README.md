# rrm-docs

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

# 2. Effort Task & Mandays

## Dashboard

| Task | MD |
|------|----|
| Dashboard KPI Summary | 1 |
| Dashboard Recent Activity | 1 |
| Dashboard Alert Notification | 1 |

Subtotal: **3 MD**

---

## Master Data → Jamaah

| Task | MD |
|------|----|
| Create Data Jamaah | 1 |
| Read List Data Jamaah | 1 |
| Read Detail Data Jamaah | 1 |
| Update Data Jamaah | 1 |
| Delete Data Jamaah | 0.5 |
| Search & Filter Jamaah | 1 |
| Upload Passport / Dokumen | 1.5 |

Subtotal: **7 MD**

---

## Master Data → Paket Program

| Task | MD |
|------|----|
| Create Paket Program | 1 |
| Read List Paket Program | 1 |
| Read Detail Paket Program | 1 |
| Update Paket Program | 1 |
| Delete Paket Program | 0.5 |
| Package Quota Management | 1 |
| Package Price Management | 1 |

Subtotal: **6.5 MD**

---

## Master Data → Agen

| Task | MD |
|------|----|
| Create Agen | 0.5 |
| Read List Agen | 0.5 |
| Read Detail Agen | 0.5 |
| Update Agen | 0.5 |
| Delete Agen | 0.5 |
| Agent Performance View | 1 |

Subtotal: **3.5 MD**

---

## Booking

| Task | MD |
|------|----|
| Create Booking | 1.5 |
| Read Booking List | 1 |
| Read Booking Detail | 1 |
| Update Booking Status | 1 |
| Cancel Booking | 1 |
| Booking Validation | 1 |

Subtotal: **6.5 MD**

---

## Seat Monitoring

| Task | MD |
|------|----|
| Seat Occupancy Calculation | 1 |
| Seat Availability Monitoring | 1 |
| Seat Alert | 1 |

Subtotal: **3 MD**

---

## Finance → Invoice

| Task | MD |
|------|----|
| Generate Invoice | 1 |
| Preview Invoice | 1 |
| Download PDF Invoice | 1.5 |

Subtotal: **3.5 MD**

---

## Finance → Payment

| Task | MD |
|------|----|
| DP Payment | 1 |
| Installment Payment | 1.5 |
| Full Payment | 1 |
| Upload Payment Proof | 1 |
| Payment History | 1 |

Subtotal: **5.5 MD**

---

## Finance → Outstanding

| Task | MD |
|------|----|
| Outstanding List | 1 |
| Outstanding Detail | 1 |
| H-35 Due Date Monitoring | 1.5 |
| Reminder Alert | 1 |

Subtotal: **4.5 MD**

---

## Operations → Manifest

| Task | MD |
|------|----|
| Generate Excel Manifest | 1 |
| Generate PDF Manifest | 1 |
| Package Manifest Filtering | 1 |

Subtotal: **3 MD**

---

## Operations → Passport Documents

| Task | MD |
|------|----|
| Download Single Passport | 1 |
| Bulk Download ZIP | 2 |

Subtotal: **3 MD**

---

## Marketing → Referral Reward

| Task | MD |
|------|----|
| Assign Referrer | 1 |
| Referral Tracking | 1 |
| Qualification Engine | 2 |
| Claim Free Seat | 1.5 |

Subtotal: **5.5 MD**

---

## Reports

| Task | MD |
|------|----|
| Revenue Report | 2 |
| Departure Report | 2 |
| Export Excel | 1 |

Subtotal: **5 MD**

---

## Settings

| Task | MD |
|------|----|
| User Management | 2 |
| Roles & Permission | 2 |

Subtotal: **4 MD**

---

## Testing & Deployment

| Task | MD |
|------|----|
| Functional Testing | 3 |
| Bug Fixing | 2 |
| Deployment | 2 |

Subtotal: **7 MD**

---

# TOTAL ESTIMASI

**Total: ± 63 - 65 Man Days**

---

# 3. ERD

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

# 4. High Level Business Sequence Diagram

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

---
name: Checkout dengan keranjang kosong
about: Laporkan bug terkait proses checkout dengan kondisi keranjang belanja kosong
title: ''
labels: bug, Major, Needs-Triage, P2
assignees: ''

---

## ENVIRONMENT (Lingkungan Pengujian)
**URL / Environment:** https://saucedemo.com
**Platform / OS:** Windows 11, Android 13, iOS 17
**Browser / App Version:** Google Chrome v120.0, Aplikasi v2.1.0
**Test Account / Data:** Akun standard_user, email testing

## STEPS TO REPRODUCE (Langkah Reproduksi)
1. Login menggunakan akun standard_user
2. Pastikan keranjang belanja dalam kondisi kosong (tidak ada produk ditambahkan)
3. Klik ikon keranjang belanja
4. Klik tombol "Checkout"
5. Isi form data diri (First Name, Last Name, Zip Code), klik "Continue"
6. Klik tombol "Finish" untuk menyelesaikan transaksi

## EXPECTED RESULT (Hasil yang Diharapkan)
Sistem seharusnya menampilkan pesan peringatan/error bahwa keranjang kosong, dan tidak mengizinkan pengguna melanjutkan proses checkout.

## ACTUAL RESULT (Hasil Aktual)
Sistem tidak melakukan validasi terhadap kondisi keranjang yang kosong. Setelah login, meskipun tidak ada produk apapun di dalam keranjang, pengguna tetap dapat mengklik tombol "Checkout" dan diarahkan ke halaman pengisian data diri (First Name, Last Name, Zip Code). Setelah data diri diisi dan pengguna melanjutkan proses ("Continue" lalu "Finish"), sistem menampilkan halaman konfirmasi bahwa transaksi telah berhasil diselesaikan, meskipun tidak ada satupun produk di keranjang dan tidak ada total biaya yang dikenakan kepada pengguna.

## CLASSIFICATION & IMPACT
**Severity:** Major
**Priority:** P2
**Status:** Open
**Business Impact:** Sistem memungkinkan terjadinya "transaksi berhasil" tanpa adanya produk dan tanpa ada biaya yang tercatat. Hal ini dapat menyebabkan data transaksi palsu/tidak valid tersimpan di sistem, membingungkan proses rekapitulasi penjualan dan pelacakan pesanan pelanggan.
**Workaround:** Tidak Ada

## ATTACHMENT & TRACEABILITY
**Related Test Case:** TC-001 – Checkout dengan keranjang kosong

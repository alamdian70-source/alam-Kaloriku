# Kaloriku

Aplikasi penghitung kalori untuk program diet dan penurunan berat badan (IF, OMAD, 5:2, Keto, dan lainnya).

Satu berkas statis (`index.html`), tanpa proses build. Login dan data memakai Supabase.

## Database (Supabase)

Tabel sudah dibuat di proyek Supabase `howsfdyflolnavdqasuz`, semuanya dengan Row Level Security (tiap pengguna hanya bisa membaca dan mengubah barisnya sendiri):

- `kalori_profiles`: data diri, target, program aktif, timer puasa berjalan
- `kalori_entries`: catatan makan harian
- `kalori_weights`: riwayat berat badan
- `kalori_fasts`: riwayat puasa
- `kalori_foods`: makanan buatan sendiri

Kunci `anon` di `index.html` memang publik. Jangan pernah menaruh kunci `service_role` di repo.

## Deploy ke Vercel

1. Push repo ini ke GitHub.
2. Di Vercel: Add New, Project, pilih repo ini.
3. Framework Preset: Other. Kosongkan Build Command dan Output Directory. Deploy.
4. Di Supabase: Authentication, URL Configuration. Isi Site URL dengan alamat Vercel-mu, dan tambahkan ke Redirect URLs, supaya tautan konfirmasi email mengarah ke aplikasi ini.

## Catatan

- Login memakai email dan kata sandi (Supabase Auth). Akun di proyek Supabase yang sama bisa dipakai di aplikasi lain.
- Nilai gizi makanan adalah perkiraan rata-rata dan bukan pengganti saran dokter atau ahli gizi.

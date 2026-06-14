# Prompt Pack: Build Portfolio Website dengan Claude

Kumpulan prompt yang digunakan dalam workshop "Optimasi Claude" (90 menit).
Setiap prompt dirancang untuk menghasilkan satu bagian dari website portfolio.

---

## Prompt 1: Setup & Struktur Dasar (10 menit)

```
Buatkan saya sebuah website portfolio one-page dengan struktur HTML/CSS yang modern dan clean.
Spesifikasi:

1. Pakai Google Fonts "Geist" weight 300,400,500,600 dan font monospace "Geist Mono"
2. Design system: clean, modern, white background, dark text (#171717)
3. Gunakan CSS custom properties (variabel) untuk warna
4. Gunakan teknik box-shadow untuk border, bukan border CSS
5. Sertakan navigasi sticky di atas
6. Sertakan section-section berikut (kosongkan kontennya dulu):
   - Hero / header
   - About me
   - Skills & tools
   - Projects / portfolio
   - Contact
   - Footer
7. Responsive: mobile-first, breakpoint di 768px dan 480px
8. Animasi fade-in sederhana untuk hero section

Output: satu file index.html lengkap dengan semua CSS inline di dalam <style> tag.
```

## Prompt 2: Hero Section (10 menit)

```
Di file index.html yang sudah ada, isi bagian hero section dengan:

1. Badge kecil di atas judul: teks "Open for Opportunities" dengan dot indikator hijau/merah
2. Judul utama (h1): format dua baris, baris kedua pakai warna aksen. 
   Contoh: "Full-stack Developer &<br><span class='highlight'>AI Enthusiast</span>"
3. Deskripsi singkat 1-2 kalimat tentang saya
4. Dua tombol CTA: 
   - Primary (dark background): "Lihat Portfolio" dengan icon panah
   - Secondary (outline): "Hubungi Saya"

Tampilkan data placeholder dulu — saya akan ganti nanti dengan data asli.
Pastikan styling tetap clean, spacing generous, tipografi bold.
```

## Prompt 3: About & Stats Section (10 menit)

```
Tambahkan section "About Me" di dalam index.html:

1. Layout dua kolom: kiri = teks tentang saya, kanan = statistik dalam grid 2x2
2. Kolom kiri: 2 paragraf tentang background & passion saya
3. Kolom kanan: 4 kartu statistik dengan:
   - Angka besar (warna aksen)
   - Label kecil di bawahnya
   - Background putih, border halus, rounded corner
4. Style kartu statistik pakai box-shadow untuk depth

Data placeholder:
- "XX+ Projects"
- "XX Clients"
- "XX Years Experience"  
- "XX Technologies"

Saya akan isi data asli nanti.
```

## Prompt 4: Skills Grid (10 menit)

```
Tambahkan section "Skills & Tools" dengan:

1. Background section pakai abu-abu sangat muda (#fafafa) — full width
2. Judul dan subjudul rata kiri
3. Grid skill items: 4 kolom di desktop, 2 kolom di mobile
4. Setiap skill item:
   - Icon (emoji) + nama skill
   - Background putih, rounded 8px
   - Shadow border halus
   - Hover: shadow lebih tegas + naik 2px

Skill yang ditampilkan (pakai data placeholder):
- React / Next.js
- TypeScript
- Tailwind CSS
- Node.js
- PostgreSQL
- Docker
- Git / GitHub
- Figma

Ganti icon emoji yang relevan untuk masing-masing skill.
```

## Prompt 5: Projects Showcase (15 menit)

```
Tambahkan section "Projects" dengan grid 2 kolom (1 kolom di mobile):

Setiap project card:
1. Placeholder image di atas (gradient background + inisial project)
2. Tag / badge (contoh: "Web App", "Mobile", "Design")
3. Judul project
4. Deskripsi singkat
5. Tech stack dalam tag kecil (monospace font)
6. Seluruh card bisa di-klik (link ke project)
7. Hover effect: shadow lebih kuat + geser naik 2px

Buat 4 project card dengan data placeholder — saya akan isi nanti.
Pastikan jarak antar card konsisten dan responsif.
```

## Prompt 6: Contact & Footer (10 menit)

```
Tambahkan section "Contact" dan footer:

Contact section:
1. Background dark (#171717), teks putih
2. Judul: "Let's Work Together"
3. Subjudul: ajakan singkat
4. 3 tombol link horizontal: Website, Email, LinkedIn
5. Style tombol: background semi-transparent white, rounded

Footer:
1. Background putih, border atas tipis
2. Kiri: copyright text
3. Kanan: link sosial media
4. Font kecil, warna abu-abu
```

## Prompt 7: Polish & Responsive (15 menit)

```
Tolong perbaiki aspek responsive dan visual berikut:

1. Cek semua spacing — pastikan konsisten (gunakan multiple 8px)
2. Tipografi: 
   - Judul section: 2.5rem, weight 600, letter-spacing -0.04em
   - Body: 1rem, weight 400, line-height 1.8
   - Pastikan tidak ada teks yang terlalu kecil di mobile
3. Mobile navigation: tambahkan hamburger menu untuk layar < 768px
4. Animasi: tambahkan animasi fade-in-up untuk semua section (pakai Intersection Observer atau CSS animation dengan delay)
5. Favicon: tambahkan placeholder
6. Meta tags: title, description
7. Pastikan semua link buttons punya hover state
8. Test di lebar 375px, 768px, 1024px, 1440px — harus tetap bagus
```

## Prompt 8: Deploy ke Netlify (10 menit)

```
Saya punya file index.html yang sudah jadi. Bantu saya deploy ke Netlify:

1. Pastikan file sudah siap di folder project
2. Buat file _redirects (opsional, untuk SPA routing)
3. Drag-and-drop deploy atau pakai Netlify CLI
4. Set custom domain kalau ada
5. Pastikan HTTPS aktif

Steps detail:
1. Buka https://app.netlify.com
2. Klik "Deploy manually" → drag folder project
3. Atau pakai CLI: `npx netlify-cli deploy --prod --dir=.`
4. Share link yang sudah live
```

---

## Tips Buat Peserta Workshop

1. **GANTI semua placeholder** — ini yang bikin portfolio kamu unik
2. **Warna aksen** — pilih 1 warna yang mencerminkan personal brand kamu
3. **Foto & konten asli** — siapkan sebelum workshop: foto profil, bio, link project
4. **Jangan overthink design** — template ini udah clean, fokus ke konten
5. **Commit ke GitHub** — simpan semua progress di repo biar aman

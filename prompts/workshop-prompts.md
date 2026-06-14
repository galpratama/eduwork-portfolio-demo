# Prompt Pack: Build Portfolio Website dengan Claude

Kumpulan prompt untuk workshop "Optimasi Claude" (90 menit) — kolaborasi Galih Pratama × Eduwork.
Setiap prompt dirancang menghasilkan satu bagian website portfolio dengan design modern, gradasi subtle, dan animasi meaningful.

---

## Prompt 1: Setup & Struktur Dasar dengan Design System (10 menit)

```
Buatkan website portfolio one-page dengan HTML/CSS inline. Gunakan design system berikut:

**Typography:**
- Font: Geist (Google Fonts) — weights 300, 400, 500, 600, 700
- Font monospace: Geist Mono (Google Fonts) — weights 400, 500
- Judul: 2.5rem, weight 600, letter-spacing -0.04em
- Body: 16px, weight 400

**Color palette (CSS custom properties):**
- Background: white (#ffffff), light gray (#fafafa)
- Text: near-black (#171717), gray (#4d4d4d, #666666)
- Accent: deep red (#e63946) dengan hover (#c1121f)
- Gunakan variabel CSS untuk semua warna

**Gradients (key):**
- Hero background: subtle vertical gradient (white → very light warm)
- Button utama: gradient accent (merah tua → merah terang)
- Section skills: subtle light gray gradient
- Contact section: dark gradient (#1a1a1a → #0a0a0a)
- Card stats: subtle gradient background

**Shadows:**
- Gunakan teknik multi-layer shadow, bukan border tebal
- Shadow-border: 0px 0px 0px 1px rgba(0,0,0,0.07)
- Card shadow: 0px 0px 0px 1px + 0px 2px 4px + 0px 8px 16px -8px

**Struktur section:**
- Sticky navigation (blur backdrop)
- Hero (dengan background gradient + glow orbs)
- About (2 kolom: teks + stats grid)
- Skills (full-width gradient background)
- Projects (grid cards)
- Contact (dark gradient background)
- Footer

**Responsive:** mobile-first, breakpoint 768px & 480px

Output: satu file index.html lengkap dengan semua CSS di dalam <style>.
Gunakan placeholder content dulu — nanti kita isi.
```

## Prompt 2: Hero Section dengan Gradasi & Animasi (10 menit)

```
Di hero section, tambahkan:

**Background:**
1. Subtle gradient dari putih ke sangat light warm (#ffffff → #faf8f8)
2. DUA "glow orb" di belakang — radial-gradient circle posisi absolute, 
   satu di kanan atas, satu di kiri bawah
3. Animasi float pada glow orbs: @keyframes floatGlow — geser perlahan + scale subtle

**Konten:**
1. Badge kecil: teks + dot indikator (pulse animation pada dot)
2. Judul utama dua baris dengan highlight: 
   - Baris kedua pakai gradient text (background-clip: text)
   - Gradient dari merah tua ke merah terang
3. Deskripsi 1-2 kalimat
4. Dua tombol CTA:
   - Primary: gradient accent background, shadow glow, hover lift
   - Secondary: white background, hover subtle gradient
5. Semua elemen animasi fadeInUp (dari bawah, opacity 0→1)

**Animasi yang harus ada:**
- Glow orbs: float animation (8s & 10s infinite, alternate direction)
- Badge dot: pulse scale animation (2s)
- Hero elements: staggered fade-in-up (delay 0s, 0.1s, 0.2s, 0.3s)
- Button arrow: geser kanan 3px pas hover
```

## Prompt 3: About & Stats dengan Hover Effects (10 menit)

```
Tambahkan section About Me:

**Layout:**
- 2 kolom: kiri = about text, kanan = stats grid 2x2
- Grid responsive

**Stats cards (per card):**
1. Background: subtle gradient (putih ke gray-50)
2. Shadow card multi-layer
3. Angka: gradient text (sama kaya accent) — bold, besar
4. Label kecil di bawah
5. Hover effect: 
   - Card naik 4px (translateY)
   - Shadow lebih tegas
   - Glow radial muncul dari pojok kanan atas card (::before pseudo-element, opacity 0→1)
6. Counter animation: angka count-up dari 0 ke target (pakai Intersection Observer + requestAnimationFrame)

**Teks about:**
- 2 paragraf dengan line-height relaxed (1.85)
- Warna gray-600
```

## Prompt 4: Skills Grid dengan Gradient Background (10 menit)

```
Tambahkan section Skills dengan:

**Background section:**
- Full-width gradient (#fafafa → #f7f5f5 → #fafafa)
- Garis tipis di atas: horizontal gradient (transparent → accent → transparent)

**Skills grid:**
- 4 kolom desktop, 2 kolom tablet, 2 kolom mobile
- Setiap skill item:
  - Background: gradient subtle (putih ke gray-50)
  - Icon emoji dalam kotak kecil (background gradient, rounded)
  - Nama skill
  - Hover: naik 3px + shadow lebih kuat
  - Hover: icon scale up 1.1 (transform)
  - Hover: overlay gradient accent subtle via ::after pseudo
  - Staggered reveal animation (masing-masing delay 0.05s bertahap)
- Semua skill items pakai scroll reveal (Intersection Observer — opacity 0, translateY 30px → visible)

**Icons (PENTING — jangan pakai emoji):**
Gunakan inline SVG untuk semua icon. Setiap icon:
- `viewBox="0 0 24 24"` — ukuran konsen
- `fill="none"` dengan `stroke="currentColor"` (line icon style) atau `fill="currentColor"` (solid)
- `stroke-width="1.5"` untuk line icons
- Ukuran 20x20 atau 18x18 tergantung konteks
- Letakkan di dalam `.skill-icon` container (40x40, rounded, background gradient)
- Warna: `currentColor` agar inherit dari parent (`var(--accent)`)

Contoh icon patterns:
```html
<!-- Atom (React) -->
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
  <circle cx="12" cy="12" r="1.5"/>
  <ellipse cx="12" cy="12" rx="10" ry="4"/>
  <ellipse cx="12" cy="12" rx="10" ry="4" transform="rotate(60 12 12)"/>
  <ellipse cx="12" cy="12" rx="10" ry="4" transform="rotate(120 12 12)"/>
</svg>

<!-- Database -->
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
  <ellipse cx="12" cy="5" rx="9" ry="3"/>
  <path d="M3 5v6c0 1.7 4 3 9 3s9-1.3 9-3V5"/>
  <path d="M3 11v6c0 1.7 4 3 9 3s9-1.3 9-3v-6"/>
</svg>
```

Sumber icon: Lucide (lucide.dev), Heroicons, atau Feather Icons — semua free & open source.
Cukup copy path SVG-nya dan inline di HTML.

**Data skills (placeholder):**
React, TypeScript, Tailwind CSS, Node.js, PostgreSQL, Docker, Git, Figma
```

## Prompt 5: Projects Grid dengan Card Effects (15 menit)

```
Tambahkan section Projects:

**Grid:** 2 kolom desktop, 1 kolom mobile

**Setiap project card:**
1. Placeholder top: gradient background + inisial (huruf besar, putih)
   - Di atasnya overlay: gradient transparent → subtle black (depth)
2. Body: padding comfortable
3. Tag/badge: background gradient accent-light, rounded pill
4. Judul: weight 600
5. Deskripsi: warna gray-600
6. Tech stack tags: font monospace, background gradient subtle
   - Pas hover card, tech tags berubah ke background accent-light

**Hover effects:**
- Card: translateY(-6px) + shadow lebih kuat + gradient overlay halus
- Timing: cubic-bezier(0.25, 0.8, 0.25, 1.2) — subtle bounce feel
- Tech tags: transisi background ke accent-light

**Animasi:**
- Card reveal: staggered (delay 0s, 0.1s, 0.15s, 0.2s)
- Scroll-triggered via Intersection Observer

Buat 4 project card dengan data placeholder.
```

## Prompt 6: Contact & Footer (10 menit)

```
Tambahkan Contact section + Footer:

**Contact section:**
1. Background: dark gradient (#1a1a1a → #111111 → #0a0a0a)
2. Dua glow orbs (radial gradient, accent, posisi absolute, animasi float)
3. Teks putih: judul + subjudul (gray-400)
4. 3 link button:
   - Background: semi-transparent white gradient
   - Border: subtle white ring
   - Hover: background jadi accent gradient + glow shadow + lift 2px
   - Backdrop-filter blur
   - **Icon: inline SVG** sebelum text (globe, mail, calendar)
   - JANGAN pakai emoji — pakai SVG line icons (Lucide style)

**Footer:**
1. Background putih, border atas tipis
2. Text kecil, gray-400
3. Link sosial: hover ke accent color
4. Responsive: stack di mobile
```

## Prompt 7: Polish — Animasi Scroll & Micro-interactions (15 menit)

```
Tambahkan animasi dan polish berikut:

**1. Scroll Reveal (Intersection Observer):**
- Semua section elements punya class "reveal"
- Default state: opacity 0, translateY 30px
- Saat masuk viewport (threshold 0.15): opacity 1, translateY 0
- Transisi: 0.7s ease, cubic-bezier(0.22, 0.61, 0.36, 1)
- Staggered delays untuk children (reveal-delay-1 s/d reveal-delay-4)
- Observer dibersihkan setelah element revealed (unobserve)

**2. Nav scroll effect:**
- Saat scroll > 20px: background lebih solid + shadow lebih tegas
- Transisi: 0.3s ease

**3. Nav link underline animation:**
- ::after pseudo-element — garis 2px gradient accent
- Default: scaleX(0), hover: scaleX(1)
- Transisi: 0.25s ease

**4. Counter animation:**
- Stats angka count-up pakai requestAnimationFrame
- Easing: ease-out cubic (1 - (1-progress)^3)
- Trigger via Intersection Observer (threshold 0.5)

**5. Hardware acceleration:**
- Gunakan transform & opacity (bukan top/left) untuk animasi performant
- will-change atau backface-visibility untuk element yang dianimasi

**6. Button interactions:**
- Primary: hover lift 2px + shadow glow membesar
- Secondary: hover lift 2px + background subtle gradient
- Arrow icon: translateX(3px) pas hover primary button
- Active state: translateY(0) (klik)

Pastikan semua animasi smooth, tidak mengganggu accessibility (prefers-reduced-motion).
```

## Prompt 8: Deploy ke Netlify (10 menit)

```
Saya sudah punya file index.html yang siap deploy. Bantu deploy ke Netlify:

**Option A — Drag & drop (paling gampang):**
1. Buka https://app.netlify.com
2. Login / signup
3. Klik area "Drag and drop your site folder here"
4. Drop folder yang berisi index.html
5. Netlify auto-deploy dan kasih URL random
6. Bisa custom domain nanti

**Option B — Netlify CLI:**
```bash
npm i -g netlify-cli
netlify deploy --prod --dir=.
```

**Option C — GitHub:**
1. Push project ke GitHub repo
2. Di Netlify: "Import from Git" → pilih repo
3. Auto-deploy setiap push

**After deploy:**
- Pastikan HTTPS aktif (otomatis di Netlify)
- Cek semua link dan asset loading
- Custom domain kalau ada
```

---

## Tips untuk Peserta Workshop

1. **Siapin konten dulu** — foto, bio, skill list, project links — biar workshop fokus ke teknis
2. **Jangan ganti struktur** — modifikasi konten + warna aja, struktur udah optimal
3. **Warna aksen itu kunci** — pilih 1 warna yang jadi identitas kamu, semua gradient turunan dari itu
4. **Animasi itu bumbu** — jangan berlebihan, cukup reveal + hover
5. **Deploy duluan** — meskipun belum perfect, deploy aja dulu biar ada URL yang bisa dishare

## Checklist Sebelum Share

- [ ] Nama & role sudah diganti
- [ ] Warna aksen sudah disesuaikan
- [ ] Foto/logo sudah ditambahkan
- [ ] Teks about me sudah personal
- [ ] Stats angka sudah akurat
- [ ] Skills sudah sesuai
- [ ] Projects ada link yang bener
- [ ] Link kontak (email, sosmed) sudah diganti
- [ ] Sudah deploy dan HTTPS aktif
- [ ] Test di HP (responsive)

# Prompt untuk AI: Buatkan Generator Prompt Landing Page Premium

Buatkan aplikasi web **Generator Prompt Landing Page Premium** yang akan menghasilkan prompt AI untuk membuat landing page produk. Aplikasi ini harus bisa menghasilkan prompt yang sangat detail dan lengkap yang bisa langsung digunakan di Claude, ChatGPT, atau AI builder lainnya.

## SPESIFIKASI LENGKAP APLIKASI

### 1. HEADER & BRANDING
- **Title**: "🚀 Generator Prompt Landing Page Premium"
- **Subtitle**: "Buat landing page profesional dengan AI dalam hitungan detik"
- **Background**: Gradient biru-ungu yang premium (#667eea ke #764ba2)
- **Header style**: Modern dengan glassmorphism effect

### 2. FORM INPUT SECTIONS

#### A. Informasi Produk Dasar
```html
- Nama Produk (required, text input)
- Kategori Produk (required, dropdown):
  * Fashion & Aksesoris
  * Elektronik  
  * Rumah & Dekorasi
  * Kecantikan & Kesehatan
  * Makanan & Minuman
  * Buku & Edukasi
  * Olahraga & Outdoor
  * Otomotif
  * Layanan Jasa
  * Produk Digital

- Style Tampilan (required, dropdown):
  * Premium & Mewah
  * Minimalist & Clean
  * Modern & Trendy
  * Classic & Elegant
  * Colorful & Vibrant
  * Dark & Professional
  * Retro & Vintage
  * Futuristic & Tech

- Deskripsi Produk (required, textarea)
- Harga Modal (text input)
```

#### B. Desain & Tampilan
```html
- Skema Warna (dropdown):
  * Modern Blue (Biru Premium)
  * Elegant Gold (Emas Mewah)
  * Minimalist Gray (Abu-abu Elegan)
  * Vibrant Orange (Oranye Energik)
  * Nature Green (Hijau Alami)
  * Luxury Purple (Ungu Mewah)
  * Classic Black (Hitam Klasik)
  * Warm Red (Merah Hangat)

- Diskon (opsional, text input)
```

#### C. Link & Kontak
```html
- Link Order (orderonline.id) (required, URL input)
  Placeholder: "https://orderonline.id/produk-anda atau link toko online lainnya"

- Link Mentahan (opsional, URL input)
  Placeholder: "Link file mentahan, template, atau resource tambahan"

- Link GIF Galeri Model (opsional, URL input)
  Placeholder: "Link GIF atau video model menggunakan produk"

- Link Gambar Testimoni (opsional, textarea)
  Placeholder: "https://example.com/testimoni1.jpg, https://example.com/testimoni2.jpg"
  Info: "pisahkan dengan koma"

- Info Kontak (text input)
  Placeholder: "WhatsApp: 0812-3456-7890 atau info kontak lainnya"
```

#### D. Fitur Landing Page (Checkboxes - default checked)
```html
☑️ Testimoni Pelanggan
☑️ Galeri Produk
☑️ Fitur & Keunggulan  
☑️ FAQ (Tanya Jawab)
☑️ Timer Countdown
☑️ Garansi & Jaminan
☑️ Info Pengiriman
☑️ Metode Pembayaran
☐ Social Media Links
☐ Video Demo
```

#### E. Target & Positioning
```html
- Target Audience (text input)
- Unique Selling Point (text input)  
- Catatan Tambahan (textarea)
```

### 3. STYLING & DESIGN

#### CSS Framework
```css
/* Modern Premium Design */
:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --accent-color: #28a745;
  --text-primary: #2d3748;
  --bg-glass: rgba(255, 255, 255, 0.95);
  --border-color: #e0e6ed;
}

/* Glassmorphism Effect */
.container {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(20px);
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

/* Form Styling */
input, textarea, select {
  padding: 15px;
  border: 2px solid #e0e6ed;
  border-radius: 12px;
  transition: all 0.3s ease;
}

input:focus, textarea:focus, select:focus {
  border-color: #667eea;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
  transform: translateY(-1px);
}

/* Button Styling */
.generate-btn {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 18px 40px;
  border-radius: 12px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.generate-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
}
```

#### Layout Structure
- **Grid system** untuk responsive design
- **Section dividers** dengan gradient background
- **Floating animations** untuk visual appeal
- **Mobile-first** responsive approach
- **Smooth transitions** di semua elements

### 4. JAVASCRIPT FUNCTIONALITY

#### Form Handling
```javascript
document.getElementById('promptForm').addEventListener('submit', function(e) {
    e.preventDefault();
    generatePrompt();
});

function generatePrompt() {
    const formData = {
        productName: document.getElementById('productName').value,
        productCategory: document.getElementById('productCategory').value,
        styleTemplate: document.getElementById('styleTemplate').value,
        colorScheme: document.getElementById('colorScheme').value,
        price: document.getElementById('price').value,
        discount: document.getElementById('discount').value,
        productDescription: document.getElementById('productDescription').value,
        orderLink: document.getElementById('orderLink').value,
        rawLink: document.getElementById('rawLink').value,
        galleryLink: document.getElementById('galleryLink').value,
        testimonialImages: document.getElementById('testimonialImages').value,
        contactInfo: document.getElementById('contactInfo').value,
        targetAudience: document.getElementById('targetAudience').value,
        uniqueSelling: document.getElementById('uniqueSelling').value,
        additionalNotes: document.getElementById('additionalNotes').value
    };
    
    // Generate detailed prompt
    const prompt = generateDetailedPrompt(formData, features);
    
    // Display result
    document.getElementById('promptOutput').textContent = prompt;
    document.getElementById('resultContainer').style.display = 'block';
}
```

#### Copy to Clipboard Function
```javascript
document.getElementById('copyBtn').addEventListener('click', function() {
    const promptText = document.getElementById('promptOutput').textContent;
    navigator.clipboard.writeText(promptText).then(function() {
        const btn = document.getElementById('copyBtn');
        const originalText = btn.textContent;
        btn.textContent = '✅ Copied!';
        btn.style.background = '#28a745';
        setTimeout(() => {
            btn.textContent = originalText;
            btn.style.background = '#28a745';
        }, 2000);
    });
});
```

### 5. PROMPT GENERATION ENGINE

#### Template Mapping
```javascript
const styleTemplates = {
    'premium': 'premium mewah dengan elemen luxury dan elegant',
    'minimalist': 'minimalist clean dengan space yang luas dan focus pada content',
    'modern': 'modern trendy dengan clean design dan interactive elements',
    'classic': 'classic elegant dengan typography serif dan traditional elements',
    'colorful': 'colorful vibrant dengan playful design dan energetic vibes',
    'dark': 'dark professional dengan contrast tinggi dan modern appeal',
    'retro': 'retro vintage dengan nostalgic elements dan classic styling',
    'futuristic': 'futuristic tech dengan modern animations dan tech elements'
};

const colorSchemes = {
    'modern-blue': 'gradien biru modern (#667eea ke #764ba2)',
    'elegant-gold': 'gradien emas elegan (#f7971e ke #ffd200)',
    'minimalist-gray': 'gradien abu-abu minimalis (#bdc3c7 ke #2c3e50)',
    'vibrant-orange': 'gradien oranye vibrant (#ff7e5f ke #feb47b)',
    'nature-green': 'gradien hijau alami (#56ab2f ke #a8e6cf)',
    'luxury-purple': 'gradien ungu mewah (#8360c3 ke #2ebf91)',
    'classic-black': 'gradien hitam klasik (#434343 ke #000000)',
    'warm-red': 'gradien merah hangat (#fc466b ke #3f5efb)'
};
```

### 6. PROMPT OUTPUT TEMPLATE

Prompt yang dihasilkan harus mengikuti format berikut:

```markdown
Buatkan landing page premium yang sangat menarik dan profesional untuk produk "[PRODUCT_NAME]" dengan spesifikasi berikut:

🎯 INFORMASI PRODUK:
- Nama Produk: [Dynamic dari form]
- Kategori: [Dynamic dari dropdown]
- Harga Modal: [Dynamic dari input]
- Diskon: [Dynamic jika ada]
- Deskripsi: [Dynamic dari textarea]
- Target Audience: [Dynamic atau default]
- Unique Selling Point: [Dynamic atau default]

🎨 DESAIN & VISUAL:
- Color Scheme: [Dynamic color scheme]
- Style Template: [Dynamic style template]
- Tampilan harus premium, modern, dan professional
- Responsive design untuk mobile dan desktop
- Smooth animations dan micro-interactions
- Typography yang elegant dan readable
[Conditional: GIF Gallery integration jika ada]
[Conditional: Testimonial images jika ada]

📱 STRUKTUR LANDING PAGE:
1. HEADER & HERO SECTION:
   - Navigation bar yang sticky dan elegant
   - Hero section dengan headline yang powerful
   - Subheadline yang menjelaskan value proposition
   - Call-to-action button yang prominent menuju: [DYNAMIC ORDER LINK]
   - Hero image/video yang berkualitas tinggi

2. PRODUCT SHOWCASE:
   - Product gallery dengan zoom functionality
   - 360° view jika memungkinkan
   - Multiple product angles dan detail shots
   [Conditional: Integrasi GIF model gallery jika ada]

3. FEATURES & BENEFITS:
[Dynamic berdasarkan checkbox selection]

4. CALL-TO-ACTION SECTIONS:
   - Primary CTA: Link Order ke [DYNAMIC ORDER LINK]
   - Secondary CTA: [DYNAMIC CONTACT INFO]
   [Conditional: Link Mentahan jika ada]
   - Multiple CTA placement strategis di seluruh page
   - Urgent messaging dan scarcity elements

5. TESTIMONI & SOCIAL PROOF:
   [Conditional: Gunakan gambar testimoni real jika ada]
   - Rating bintang dan review pelanggan
   - Social proof counters
   - Trust badges dan security seals

6. FOOTER:
   - Contact information lengkap: [DYNAMIC CONTACT]
   - Link order utama: [DYNAMIC ORDER LINK]
   [Conditional: Link resource tambahan jika ada]
   - Social media links
   - Legal information dan policies

🔧 FITUR TEKNIS:
- Optimized loading speed dengan lazy loading
- SEO-friendly structure dan meta tags
- Analytics tracking (Google Analytics ready)
- Social sharing functionality
- Mobile-first responsive design
- Cross-browser compatibility
- Accessibility standards compliant
- Interactive elements dengan smooth transitions
- WhatsApp integration untuk contact
- Popup modal untuk detail produk

💡 COPYWRITING GUIDELINES:
- Headline yang attention-grabbing dan benefit-focused
- Bullet points yang mudah di-scan
- Social proof dan credibility markers
- Urgency dan scarcity messaging ("Stok Terbatas", "Promo Hari Ini")
- Emotional triggers yang sesuai target audience
- Clear value proposition di setiap section
- Call-to-action yang persuasif dan action-oriented

📊 CONVERSION OPTIMIZATION:
- Above-the-fold CTA yang visible menuju [DYNAMIC ORDER LINK]
- Trust signals di area penting
- Risk reversal elements (garansi, money-back guarantee)
- Social proof positioning yang strategis
- Mobile conversion optimization dengan touch-friendly buttons
- Fast loading dan smooth UX
- Exit-intent popup untuk special offer
- Sticky order button yang mengikuti scroll

📱 MOBILE OPTIMIZATION:
- Mobile-first approach dengan touch optimization
- Swipe gestures untuk gallery
- Thumb-friendly button placement
- Optimized forms untuk mobile keyboard
- Fast loading dengan compressed images
- Progressive Web App features

🔗 LINK INTEGRATION:
- Semua CTA button mengarah ke: [DYNAMIC ORDER LINK]
- Contact section dengan: [DYNAMIC CONTACT INFO]
[Conditional: Download mentahan jika ada]
[Conditional: Model gallery jika ada]
- WhatsApp floating button untuk instant contact
- Social sharing dengan pre-filled message

[Conditional: CATATAN KHUSUS jika ada additional notes]

IMPORTANT: Buatkan dalam format HTML, CSS, dan JavaScript yang complete dan functional. Semua link harus functional dan mengarah ke URL yang benar. Pastikan semua elemen interactive berfungsi dengan baik. Fokus pada user experience yang exceptional dan conversion rate yang tinggi.

Gunakan teknik psikologi marketing seperti:
- Scarcity (stok terbatas)
- Urgency (promo terbatas waktu)  
- Social proof (testimoni real)
- Authority (badge dan sertifikasi)
- Reciprocity (bonus dan gift)

Generate full landing page code yang siap deploy, professional, dan conversion-focused!
```

### 7. RESULT DISPLAY

#### Output Container
```html
<div id="resultContainer" class="result-container" style="display: none;">
    <div class="result-header">
        <h3>🚀 Prompt Generated Successfully!</h3>
        <button id="copyBtn" class="copy-btn">📋 Copy Prompt</button>
    </div>
    <div id="promptOutput" class="prompt-output"></div>
    
    <div class="tips">
        <h4>📝 Cara Menggunakan Prompt:</h4>
        <ul>
            <li>Copy prompt di atas</li>
            <li>Paste ke Claude, ChatGPT, atau AI builder lainnya</li>
            <li>AI akan membuat landing page sesuai spesifikasi Anda</li>
            <li>Jika perlu penyesuaian, tambahkan instruksi spesifik</li>
        </ul>
    </div>
</div>
```

### 8. ADDITIONAL FEATURES

#### Tips Section
```html
<div class="tips">
    <h4>💡 Tips untuk Hasil Optimal:</h4>
    <ul>
        <li>Isi semua field dengan informasi yang detail dan akurat</li>
        <li>Gunakan deskripsi produk yang menarik dan persuasif</li>
        <li>Pastikan link order sudah benar dan aktif</li>
        <li>Pilih skema warna yang sesuai dengan brand Anda</li>
        <li>Tambahkan unique selling point yang kuat</li>
    </ul>
</div>
```

#### Floating Elements
```css
.floating-elements {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: -1;
}

.floating-circle {
    position: absolute;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.1);
    animation: float 6s ease-in-out infinite;
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
}
```

### 9. TECHNICAL REQUIREMENTS

- **Single HTML file** dengan embedded CSS dan JavaScript
- **No external dependencies** kecuali CDN yang diperlukan
- **Mobile responsive** dengan breakpoints yang proper
- **Cross-browser compatibility** (Chrome, Firefox, Safari, Edge)
- **Performance optimized** dengan loading time < 3 detik
- **Accessibility compliant** dengan proper ARIA labels
- **SEO-friendly** dengan meta tags yang tepat

### 10. QUALITY ASSURANCE

#### Validation Requirements
- Form validation dengan error messages yang clear
- Required field indicators yang visible
- Input format validation (URL, text, etc.)
- Real-time feedback untuk user actions

#### Error Handling
- Graceful error handling untuk network issues
- Fallback untuk unsupported browsers
- User-friendly error messages
- Recovery mechanisms untuk failed operations

### 11. SUCCESS CRITERIA

Aplikasi dianggap berhasil jika:
- ✅ Semua form input berfungsi dengan baik
- ✅ Prompt generation menghasilkan output yang detailed dan actionable
- ✅ Copy to clipboard berfungsi di semua browser
- ✅ Design terlihat premium dan professional
- ✅ Responsive design perfect di mobile dan desktop
- ✅ No console errors atau bugs
- ✅ Loading time optimal
- ✅ Accessibility score tinggi

## INSTRUKSI FINAL

Buatkan aplikasi web ini sebagai **single HTML file** yang complete, functional, dan siap deploy. Pastikan semua feature berfungsi dengan baik dan design terlihat premium seperti contoh yang diberikan. Generator ini harus bisa menghasilkan prompt yang sangat detail untuk membuat landing page conversion-focused yang professional.

**Output harus berupa kode HTML lengkap yang bisa langsung dibuka di browser dan digunakan tanpa setup tambahan.**# Generator-Prompt

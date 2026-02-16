# 🖼️ Image Display Guide

## Current Status

✅ **All 13 images are already correctly configured in the website HTML**

The images are using authenticated URLs with security tokens from the GenSpark file system. Each image URL includes a token parameter that authenticates the request.

## Image Locations in Website

### 1. Hero/About Section
- **Image**: Presenting in office
- **Purpose**: Professional profile photo

### 2. Professional Engagements - Workshops & Conferences
- **National Health & Family Welfare**: Clinician training session
- **Panel Discussion**: Mental health and rehabilitation panel
- **Large Conference**: Professional audience engagement

### 3. Professional Engagements - Training & Community
- **Classroom Training**: Educational training for students and professionals
- **Group Training**: Workshop for parents, educators, and leaders
- **Presenting to Audience**: Public speaking engagement

### 4. Certifications & Recognition
- **ANCSAP 2023**: Speaker at national conference
- **Receiving Certificate**: Professional recognition award
- **Ayush Rehabilitation Centre**: Certificate presentation ceremony

### 5. Community Impact
- **Law Enforcement Training**: Group photo with law enforcement team
- **Outdoor Event**: Community engagement activity
- **Team Photo**: Collaborative team work

---

## Why Images Might Not Display

If images are not showing on your website, here are the possible reasons and solutions:

### 🔴 **Problem 1: Token Expiration**

**Issue**: The authentication tokens in the image URLs may have expired.

**Why**: The tokens in the URLs (the long `?token=Z0FBQUF...` part) are time-limited security tokens that expire after a certain period.

**Solution Options**:

#### **Option A: Download Images Locally (RECOMMENDED)**

1. **Download all 13 images** from the original presentation:
   - Visit each image URL in your browser
   - Right-click → "Save image as..."
   - Name them: `hero.jpg`, `national_health.jpg`, etc.

2. **Create an `images` folder** in your website directory:
   ```
   archana_website_final/
   ├── images/
   │   ├── hero.jpg
   │   ├── national_health.jpg
   │   ├── panel_discussion.jpg
   │   ├── large_conference.jpg
   │   ├── classroom_training.jpg
   │   ├── group_training.jpg
   │   ├── presenting_audience.jpg
   │   ├── ancsap_2023.jpg
   │   ├── receiving_certificate.jpg
   │   ├── ayush_certificate.jpg
   │   ├── law_enforcement.jpg
   │   ├── outdoor_event.jpg
   │   └── team_photo.jpg
   ├── index.html
   ├── styles.css
   └── ...
   ```

3. **Update image URLs in index.html**:
   - Replace: `src="https://www.genspark.ai/api/files/s/CJdICX4J?token=..."`
   - With: `src="images/hero.jpg"`

#### **Option B: Use Image Hosting Service**

1. **Upload images to a free hosting service**:
   - **Cloudinary** (free tier: https://cloudinary.com)
   - **ImgBB** (https://imgbb.com)
   - **Imgur** (https://imgur.com)

2. **Get permanent URLs** from the hosting service

3. **Update HTML** with new URLs

#### **Option C: Host Images on Netlify**

When you deploy to Netlify with the images folder:
1. Netlify automatically serves the images
2. Images load from your domain (faster)
3. No external dependencies
4. No token expiration issues

---

### 🔴 **Problem 2: CORS (Cross-Origin Resource Sharing) Issues**

**Issue**: Browsers block images from external domains due to security policies.

**Solution**: Use Option A (local images) to avoid CORS issues entirely.

---

### 🔴 **Problem 3: Viewing HTML File Locally**

**Issue**: Opening `index.html` directly from your computer (file://) may not load external images properly.

**Solution**: 
1. Deploy to Netlify (images will work once deployed)
2. OR use a local server:
   ```bash
   # If you have Python installed:
   python -m http.server 8000
   # Then visit: http://localhost:8000
   ```

---

## ✅ Recommended Fix (Step-by-Step)

### **Step 1: Download All Images**

Visit these URLs and save each image:

1. **Hero/About**: [Download](https://www.genspark.ai/api/files/s/CJdICX4J)
2. **National Health**: [Download](https://www.genspark.ai/api/files/s/B4ekygLY)
3. **Panel Discussion**: [Download](https://www.genspark.ai/api/files/s/jexamS8f)
4. **Large Conference**: [Download](https://www.genspark.ai/api/files/s/uL6oHktf)
5. **Classroom Training**: [Download](https://www.genspark.ai/api/files/s/Dgl1hBPS)
6. **Group Training**: [Download](https://www.genspark.ai/api/files/s/AoQKNAcq)
7. **Presenting to Audience**: [Download](https://www.genspark.ai/api/files/s/mkv8k1b2)
8. **ANCSAP 2023**: [Download](https://www.genspark.ai/api/files/s/kPewe2FE)
9. **Receiving Certificate**: [Download](https://www.genspark.ai/api/files/s/bzB94q1o)
10. **Ayush Certificate**: [Download](https://www.genspark.ai/api/files/s/kgSrSxmZ)
11. **Law Enforcement**: [Download](https://www.genspark.ai/api/files/s/fFs4q07S)
12. **Outdoor Event**: [Download](https://www.genspark.ai/api/files/s/J4UMAcFE)
13. **Team Photo**: [Download](https://www.genspark.ai/api/files/s/p0VBh9xw)

### **Step 2: Create Images Folder**

Create a folder named `images` next to your `index.html` file.

### **Step 3: Rename Downloaded Images**

Rename your downloaded images to match these names:
- `hero.jpg`
- `national_health.jpg`
- `panel_discussion.jpg`
- `large_conference.jpg`
- `classroom_training.jpg`
- `group_training.jpg`
- `presenting_audience.jpg`
- `ancsap_2023.jpg`
- `receiving_certificate.jpg`
- `ayush_certificate.jpg`
- `law_enforcement.jpg`
- `outdoor_event.jpg`
- `team_photo.jpg`

### **Step 4: Update HTML File**

**I can create an updated version of index.html with local image paths for you!**

Let me know if you'd like me to generate that file.

---

## Quick Test

Once you've downloaded images and updated the HTML:

1. Open `index.html` in your browser
2. Right-click on a missing image → "Inspect"
3. Check the Console tab for error messages
4. Common errors:
   - **404 Not Found**: Image file missing or wrong path
   - **CORS error**: External image blocked
   - **Failed to load**: Network issue

---

## Need Help?

If images still don't show:

1. ✅ Verify images are in the `images/` folder
2. ✅ Check file names match exactly (case-sensitive)
3. ✅ Make sure image files are `.jpg` or `.png` format
4. ✅ Test on Netlify (not just local file)
5. ✅ Check browser console for errors (F12 → Console tab)

---

## Alternative: Placeholder Images

If you can't access the original images, you can temporarily use placeholder images:

```html
<img src="https://via.placeholder.com/800x600/4A90E2/FFFFFF?text=Professional+Photo" 
     alt="Professional Photo">
```

This will show a blue placeholder until you get the real images.

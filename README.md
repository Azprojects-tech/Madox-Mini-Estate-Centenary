# 🏡 Madox Mini Estate - Interactive Parcel Mapping System

## 📋 Project Overview
- **Estate Name**: Madox Mini Estate
- **Price**: ₦15,000,000 per parcel
- **Contact**: +2348039921371
- **Email**: ifeanyiali@gmail.com
- **WhatsApp**: +2348039921371

## 📁 Files in This Project

### 1. `madox-config.json`
Configuration file with all estate settings including:
- Site title and branding
- Contact information
- Price display
- Color scheme

### 2. `madox-mini-estate.html`
Complete interactive mapping website with:
- ✅ Mobile-responsive design
- ✅ Search functionality
- ✅ Status color coding (Available/Reserved/Sold)
- ✅ WhatsApp integration
- ✅ Email contact system
- ✅ Professional styling

### 3. `geojson-processor.html`
Tool to process your Parcels.geojson file:
- Adds price column (₦15,000,000)
- Adds status column (available)
- Ensures parcel_id exists
- Downloads processed file

## 🚀 Setup Instructions

### Step 1: Process Your GeoJSON File
1. Open `geojson-processor.html` in your browser
2. Copy content from `C:\Users\Admin\Madox-Pocket-Layout\Parcels.geojson`
3. Paste into the processor
4. Click "Process GeoJSON"
5. Download the processed file

### Step 2: Update the Map File
1. Open `madox-mini-estate.html` in a text editor
2. Find the `sampleParcels` variable (around line 300)
3. Replace the sample data with your processed GeoJSON
4. Save the file

### Step 3: Test the System
1. Open `madox-mini-estate.html` in your browser
2. Verify all parcels display correctly
3. Test search functionality
4. Test contact buttons

### Step 4: Deploy
1. Copy all files to `C:\Users\Admin\Madox-Pocket-Layout\`
2. Upload to your web hosting
3. Share the URL with clients

## 🎨 Customization Options

### Colors (in CSS variables):
- Primary: `#1e40af` (Blue)
- Secondary: `#1e3a8a` (Dark Blue)
- Available: `#28a745` (Green)
- Sold: `#dc3545` (Red)
- Reserved: `#ffc107` (Yellow)

### Contact Information:
Update in the JavaScript CONFIG object:
```javascript
const CONFIG = {
    contactInfo: {
        phone: '+2348039921371',
        email: 'ifeanyiali@gmail.com',
        whatsapp: '+2348039921371'
    }
};
```

## 🔧 Features Included

### Core Mapping:
- ✅ Interactive parcel visualization
- ✅ OpenStreetMap and Satellite views
- ✅ Zoom and pan controls
- ✅ Mobile-optimized interface

### Business Features:
- ✅ Parcel status management
- ✅ Price display per parcel
- ✅ Search by parcel ID
- ✅ Contact integration
- ✅ WhatsApp direct messaging

### Professional Design:
- ✅ Modern responsive layout
- ✅ Professional color scheme
- ✅ Hover effects and animations
- ✅ Mobile landscape support

## 📱 Mobile Optimization
- Responsive design for all screen sizes
- Touch-friendly controls
- Optimized for landscape viewing
- Fast loading on mobile networks

## 🌐 Integration Ready
This system can be:
- Embedded in other websites (iframe)
- Integrated into mobile apps
- Used as standalone website
- White-labeled for clients

## 📞 Support
For technical support or customizations:
- **Email**: ifeanyiali@gmail.com
- **Phone**: +2348039921371

---
*Created by A&Z Projects Ltd - Your GIS and Mapping Specialists*

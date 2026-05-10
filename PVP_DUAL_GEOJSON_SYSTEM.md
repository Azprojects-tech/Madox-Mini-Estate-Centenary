# PVP DUAL GEOJSON SYSTEM & COLUMN REQUIREMENTS
*Enhanced Template System with Parcels + Landmarks*

## 🗺️ DUAL GEOJSON STRUCTURE

### Two-File System
1. **`[estate-name]-parcels.geojson`** - Property boundaries and parcel data
2. **`[estate-name]-landmarks.geojson`** - Infrastructure, amenities, and features

### Template Updates Required
```javascript
const CLIENT_CONFIG = {
    estateName: '{{ESTATE_NAME}}',
    clientName: '{{CLIENT_NAME}}',
    clientEmail: '{{CLIENT_EMAIL}}',
    clientPhone: '{{CLIENT_PHONE}}',
    estateLocation: '{{ESTATE_LOCATION}}',
    googleSheetsId: '{{SHEET_ID}}',
    parcelsGeojson: '{{PARCELS_GEOJSON}}',    // NEW: Separate parcel file
    landmarksGeojson: '{{LANDMARKS_GEOJSON}}'  // NEW: Separate landmarks file
};
```

---

## 📋 GEOJSON COLUMN REQUIREMENTS

### PARCELS GEOJSON - Required Properties
```json
{
  "type": "Feature",
  "properties": {
    "PARCEL_ID": "001",           // REQUIRED - Must match Google Sheets
    "PARCEL_AREA": "500",         // REQUIRED - Square meters or specified unit
    "STATUS": "Available",        // OPTIONAL - Default status if not in sheets
    "PRICE": "15000000",         // OPTIONAL - Can come from Google Sheets
    "SIZE_UNIT": "sqm"           // OPTIONAL - Default: sqm
  },
  "geometry": { ... }
}
```

### LANDMARKS GEOJSON - Required Properties
```json
{
  "type": "Feature", 
  "properties": {
    "NAME": "Main Gate",          // REQUIRED - Landmark name
    "TYPE": "Infrastructure",     // REQUIRED - Category type
    "DESCRIPTION": "Estate entrance", // OPTIONAL - Details
    "STATUS": "Completed"         // OPTIONAL - Construction status
  },
  "geometry": { ... }
}
```

---

## 🏷️ COLUMN LABEL STANDARDS

### Parcel Properties (Case-Sensitive)
| Required | Property Name | Description | Example |
|----------|--------------|-------------|---------|
| ✅ YES | `PARCEL_ID` | Unique identifier | "001", "P-001", "PLOT-001" |
| ✅ YES | `PARCEL_AREA` | Plot size (numeric) | "500", "750.5", "1200" |
| ❌ Optional | `STATUS` | Current status | "Available", "Sold", "Reserved" |
| ❌ Optional | `PRICE` | Price in Naira | "15000000", "25000000" |
| ❌ Optional | `SIZE_UNIT` | Area measurement | "sqm", "sqft", "acres" |

### Landmark Properties (Case-Sensitive)
| Required | Property Name | Description | Example |
|----------|--------------|-------------|---------|
| ✅ YES | `NAME` | Feature name | "Swimming Pool", "Main Road" |
| ✅ YES | `TYPE` | Category | "Amenity", "Infrastructure", "Utility" |
| ❌ Optional | `DESCRIPTION` | Details | "Olympic size pool", "Tarred road" |
| ❌ Optional | `STATUS` | Construction status | "Completed", "Planned", "Under Construction" |

---

## 🔧 ENHANCED TEMPLATE SYSTEM

### Updated Client Input Format
```json
{
  "estate_name": "Paradise Gardens Estate",
  "client_name": "Ahmed Bello", 
  "client_email": "ahmed@paradise-gardens.ng",
  "client_phone": "+234 807 123 4567",
  "estate_location": "Abuja, FCT",
  "parcels_geojson": "paradise-parcels.geojson",     // NEW
  "landmarks_geojson": "paradise-landmarks.geojson"  // NEW
}
```

### Template Placeholders (Updated)
```
{{ESTATE_NAME}} → "Paradise Gardens Estate"
{{CLIENT_NAME}} → "Ahmed Bello"
{{CLIENT_EMAIL}} → "ahmed@paradise-gardens.ng"
{{CLIENT_PHONE}} → "+234 807 123 4567"
{{ESTATE_LOCATION}} → "Abuja, FCT"
{{SHEET_ID}} → [Generated Google Sheets ID]
{{PARCELS_GEOJSON}} → "paradise-parcels.geojson"
{{LANDMARKS_GEOJSON}} → "paradise-landmarks.geojson"
```

---

## 🗂️ PROJECT FOLDER STRUCTURE

### Recommended Client Project Organization
```
Client_Estate_Name/
├── 📄 estate-portal.html (Generated portal)
├── 📄 estate-parcels.geojson (Property boundaries)
├── 📄 estate-landmarks.geojson (Infrastructure/amenities)
├── 📊 estate-database.csv (Google Sheets template)
├── 📦 estate-deploy.zip (Netlify package)
├── 📚 Documentation/
│   ├── client-guide.md
│   ├── iframe-integration.md
│   └── admin-access.md
└── 📋 project-config.json (Client configuration)
```

---

## 🎯 LANDMARK CATEGORIES & TYPES

### Standard Landmark Types
```javascript
const LANDMARK_TYPES = {
    "Infrastructure": {
        color: "#34495e",
        icon: "🏗️",
        examples: ["Roads", "Bridges", "Gates", "Drainage"]
    },
    "Amenities": {
        color: "#3498db", 
        icon: "🏊",
        examples: ["Swimming Pool", "Clubhouse", "Playground", "Gardens"]
    },
    "Utilities": {
        color: "#e74c3c",
        icon: "⚡",
        examples: ["Power Station", "Water Treatment", "Internet Hub"]
    },
    "Commercial": {
        color: "#f39c12",
        icon: "🏪", 
        examples: ["Shopping Center", "Restaurant", "Bank", "Pharmacy"]
    },
    "Educational": {
        color: "#2ecc71",
        icon: "🎓",
        examples: ["School", "Library", "Training Center"]
    },
    "Healthcare": {
        color: "#e67e22",
        icon: "🏥",
        examples: ["Clinic", "Hospital", "Emergency Center"]
    }
};
```

---

## 📊 GOOGLE SHEETS INTEGRATION

### Parcel Database Structure (Updated)
```csv
Parcel ID,Status,Price,Area,Unit,Buyer,Contact,Notes,Date Updated,Agent
001,Available,₦15000000,500,sqm,,,Prime corner plot,2025-09-07,
002,Sold,₦18000000,600,sqm,John Smith,+234-801-234-5678,Transaction complete,2025-09-07,Sales Team
003,Reserved,₦16500000,550,sqm,Mary Johnson,+234-802-345-6789,30% deposit paid,2025-09-07,Sales Team
```

### Key Requirements
- **Parcel ID** must match exactly with GeoJSON `PARCEL_ID` property
- **Area** should match GeoJSON `PARCEL_AREA` for validation
- **Unit** specifies measurement (sqm, sqft, acres)

---

## ✅ COLUMN VALIDATION CHECKLIST

### Before Processing Client Data
- [ ] **PARCEL_ID** exists and unique in parcels GeoJSON
- [ ] **PARCEL_AREA** is numeric in parcels GeoJSON  
- [ ] **NAME** exists in landmarks GeoJSON
- [ ] **TYPE** specified for all landmarks
- [ ] Google Sheets **Parcel ID** column matches GeoJSON exactly
- [ ] No duplicate parcel IDs in either system
- [ ] Area values are consistent between GeoJSON and Google Sheets

---

## 🚀 UPDATED WORKFLOW

### Client Provides (Enhanced)
1. Estate contact information
2. **Parcels GeoJSON** with `PARCEL_ID` and `PARCEL_AREA`
3. **Landmarks GeoJSON** with `NAME` and `TYPE`
4. Project folder structure (recommended)

### AI Agent Processes
1. Validates both GeoJSON files for required properties
2. Creates enhanced template with dual-file system
3. Generates Google Sheets with parcel validation
4. Creates project folder structure
5. Delivers complete package with landmarks integration

### Client Receives
- Portal with parcels AND landmarks visualization
- Enhanced map showing infrastructure and amenities
- Complete project folder with all files organized
- Documentation covering both parcel and landmark management

---

**ENHANCED TEMPLATE SYSTEM STATUS: READY FOR DUAL GEOJSON PROCESSING** ✅

*Your template system now handles both parcels and landmarks with proper column validation!* 🚀

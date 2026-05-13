# LINE LIFF Quotation Verification System

ระบบตรวจสอบและอนุมัติใบเสนอราคาผ่าน LINE LIFF

## 🚀 Features

- ✅ Dynamic quotation loading from URL parameters
- ✅ Detailed quotation display with items table
- ✅ Automatic tax calculation (7% VAT)
- ✅ Expiry date validation
- ✅ Approve/Reject actions
- ✅ LINE message integration
- ✅ Mobile responsive design
- ✅ Mock data fallback for testing

## 📋 Requirements

- LINE LIFF ID (configured in `index.html`)
- Backend API endpoints (optional - uses mock data if not available)
- Web server to serve the files

## 🔧 Configuration

### Edit `index.html` Line 303

```javascript
const config = {
    liffId: "YOUR_LIFF_ID",
    apiBaseUrl: "https://your-api-domain.com/api"
};
```

Replace with your actual:
- `YOUR_LIFF_ID`: Your LINE LIFF ID
- `https://your-api-domain.com/api`: Your backend API URL

## 📡 API Endpoints Required

### GET `/api/quotation/:id`
Returns quotation details

```json
{
  "id": 1,
  "quotation_no": "QU-2026-001",
  "customer_name": "Company Name",
  "quote_date": "2026-05-10",
  "expiry_date": "2026-06-10",
  "items": [
    {
      "description": "Product A",
      "quantity": 10,
      "unit_price": 500
    }
  ],
  "notes": "Optional notes"
}
```

### POST `/api/quotation/:id/action`
Save approval/rejection decision

```json
{
  "action": "อนุมัติ" or "ปฏิเสธ",
  "approved_by": "User Name",
  "user_id": "LINE_USER_ID",
  "timestamp": "2026-05-13T10:30:00Z"
}
```

## 🌐 Deployment

### Deploy to Vercel

1. Connect GitHub repository
2. Link repository to Vercel
3. Deploy automatically on push

```bash
# Or manually deploy
npm i -g vercel
vercel
```

### Local Testing

```bash
# Python
python -m http.server 8000

# Node.js
npx http-server

# Access at http://localhost:8000
```

## 📝 Usage

```
https://your-domain.com/index.html?id=QU-2026-001
https://your-domain.com/index.html?id=QU-2026-002
```

## 📧 Support

For issues or questions, please contact the development team.

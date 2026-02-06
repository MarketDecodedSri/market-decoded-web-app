# UPI Payment Setup Instructions

## Quick Setup Guide

To complete the UPI payment integration, you need to add your actual UPI QR code and UPI ID to the checkout page.

### Step 1: Add Your UPI QR Code Image

1. Generate your UPI QR code from your payment app (Google Pay, PhonePe, Paytm, etc.)
2. Save the QR code image in the project folder (e.g., `upi-qr-code.png`)
3. Open `checkout.html` and find this section (around line 350):

```html
<!-- Placeholder for QR Code - Replace with actual QR code image -->
<div class="w-64 h-64 bg-gray-200 flex items-center justify-center rounded-lg">
    <div class="text-center">
        <div class="text-4xl mb-2">📱</div>
        <p class="text-sm text-gray-600">QR Code Placeholder</p>
        <p class="text-xs text-gray-500 mt-1">Add your UPI QR code image here</p>
    </div>
</div>
```

4. Replace it with:

```html
<!-- Your UPI QR Code -->
<img src="upi-qr-code.png" alt="UPI QR Code" class="w-64 h-64 rounded-lg">
```

### Step 2: Update Your UPI ID

1. Open `checkout.html` and find this line (around line 370):

```html
<p class="text-center font-mono font-bold text-navy text-lg" id="upiId">yourname@upi</p>
```

2. Replace `yourname@upi` with your actual UPI ID, for example:

```html
<p class="text-center font-mono font-bold text-navy text-lg" id="upiId">merchant@paytm</p>
```

### Step 3: Test the Payment Flow

1. Open `checkout.html` in your browser
2. Click the "Pay Now" button
3. Verify that:
   - The modal popup appears
   - Your QR code is displayed correctly
   - Your UPI ID is shown correctly
   - The WhatsApp link works (opens WhatsApp with the number 8248280295)
   - The "Copy UPI ID" button works

## Features Implemented

✅ **UPI Payment Notice** - Blue banner showing "Currently accepting UPI payments only"  
✅ **Device Detection** - Automatically detects if user is on mobile or desktop  
✅ **Desktop/Tablet Behavior** - Shows modal popup with QR code and UPI ID  
✅ **Mobile Behavior** - Directly opens UPI app with pre-filled payment details  
✅ **Mobile Instructions** - Shows payment confirmation instructions on the page after UPI app opens  
✅ **QR Code Display** - Section for your UPI QR code (desktop/tablet only)  
✅ **UPI ID Display** - Shows your UPI ID with copy functionality  
✅ **Amount Display** - Shows ₹3,999 prominently  
✅ **Payment Instructions** - Clear step-by-step instructions  
✅ **WhatsApp Integration** - Direct link to send payment screenshot to +91 8248280295  
✅ **Close Functionality** - Multiple ways to close the modal (X button, Close button, click outside)  

## Payment Flow

### On Desktop/Tablet:
1. User clicks "Pay Now" button
2. Modal popup appears with QR code and UPI ID
3. User scans QR code or copies UPI ID
4. User makes payment via their UPI app
5. User takes screenshot of payment confirmation
6. User clicks WhatsApp link in modal to send screenshot to 8248280295

### On Mobile:
1. User clicks "Pay Now" button
2. UPI app opens automatically with pre-filled payment details
3. User completes payment in their UPI app
4. Payment instructions appear on the page
5. User takes screenshot of payment confirmation
6. User clicks "Open WhatsApp" button to send screenshot to 8248280295
7. You verify payment and grant course access within 24 hours

## Notes

- The modal prevents background scrolling when open
- The UPI ID copy button shows a success message when clicked
- The WhatsApp link opens in a new tab
- All styling matches the main landing page theme

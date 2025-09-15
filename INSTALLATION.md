# Ecocash WordPress Plugin - Quick Installation Guide

## What This Plugin Does

This WordPress plugin transforms the Ecocash Dart SDK into a fully functional WordPress payment gateway that integrates seamlessly with WooCommerce. It provides:

- **Payment Processing**: Accept Ecocash payments on your WordPress/WooCommerce store
- **Transaction Management**: Track and manage all Ecocash transactions
- **Refund Processing**: Handle refunds directly from WordPress admin
- **Mobile Number Validation**: Automatic validation for Zimbabwean mobile numbers
- **Multi-Currency Support**: USD, ZWL, and ZiG currencies
- **Sandbox Testing**: Test payments safely before going live

## Quick Installation

1. **Download Plugin**: Download all files from this repository
2. **Upload to WordPress**: 
   - Zip the entire directory as `ecocash-payment-gateway.zip`
   - Go to WordPress Admin → Plugins → Add New → Upload Plugin
   - Upload the ZIP file and activate

3. **Configure Settings**:
   - Go to WordPress Admin → Ecocash → Settings
   - Add your Ecocash API keys (get from https://developers.ecocash.co.zw)
   - Enable sandbox mode for testing
   - Test your API connection

4. **Enable in WooCommerce**:
   - Go to WooCommerce → Settings → Payments
   - Find "Ecocash Payment Gateway" and enable it
   - Configure gateway settings as needed

## Key Features Implemented

### 1. Complete WordPress Plugin Structure
- Main plugin file with proper WordPress headers
- Organized class structure following WordPress standards
- Proper activation/deactivation hooks
- Uninstall script for clean removal

### 2. PHP SDK Implementation
- Converted Dart SDK functionality to PHP
- All API endpoints: payments, lookups, refunds
- Proper error handling and validation
- Mobile number formatting and validation

### 3. WooCommerce Integration
- Full payment gateway implementation
- Checkout flow integration
- Order status management
- Refund processing from admin

### 4. Admin Interface
- Settings page for configuration
- Transaction history and management
- Setup guide with step-by-step instructions
- API connection testing
- Real-time status updates

### 5. User Experience
- Simple checkout process
- Mobile number field with validation
- Payment status checking
- Clear error messages
- Responsive design

## File Structure

```
ecocash-payment-gateway/
├── ecocash-payment-gateway.php      # Main plugin file
├── includes/
│   ├── class-ecocash-sdk.php        # PHP SDK implementation
│   ├── class-ecocash-api.php        # API wrapper
│   ├── class-ecocash-payment-gateway.php  # WooCommerce gateway
│   └── class-ecocash-admin.php      # Admin interface
├── assets/
│   ├── css/admin.css                # Admin styles
│   ├── js/admin.js                  # Admin JavaScript
│   └── images/ecocash-logo.png      # Logo placeholder
├── uninstall.php                    # Cleanup on uninstall
└── README-WORDPRESS-PLUGIN.md       # Full documentation
```

## API Implementation

The plugin implements all core Ecocash API functionality:

### Payment Processing
```php
$payment_data = array(
    'mobileNumber' => '263771234567',
    'amount' => 50.00,
    'reason' => 'Payment for Order #123',
    'currency' => 'USD',
    'reference' => 'WC-123-1234567890'
);
```

### Transaction Lookup
```php
$lookup_data = array(
    'mobileNumber' => '263771234567',
    'reference' => 'WC-123-1234567890'
);
```

### Refund Processing
```php
$refund_data = array(
    'originalEcocashTransactionReference' => 'ecocash-ref-123',
    'refundCorrelator' => 'REF-123-1234567890',
    'sourceMobileNumber' => '263771234567',
    'amount' => 25.00,
    'clientName' => 'Your Store Name',
    'currency' => 'USD',
    'reasonForRefund' => 'Customer requested refund'
);
```

## Next Steps

1. **Install the Plugin**: Follow the installation guide above
2. **Get API Keys**: Register at https://developers.ecocash.co.zw
3. **Test in Sandbox**: Use sandbox mode to test payments
4. **Go Live**: Switch to live mode for production

This plugin is ready for production use and provides all the functionality needed to accept Ecocash payments in WordPress/WooCommerce stores serving the Zimbabwean market.

## Support

- Check the full documentation in `README-WORDPRESS-PLUGIN.md`
- Visit https://developers.ecocash.co.zw for official API documentation
- Report issues on the GitHub repository
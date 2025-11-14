# WebbyCrown RapNet for Bagisto

## 1. Introduction:

"RapNet for Bagisto" seamlessly integrates with the RapNet Diamond Trading Network, empowering jewelry store admins to display and sell certified diamonds from RapNet's extensive global inventory. This extension enables Bagisto store owners to access thousands of diamonds, manage pricing with custom commissions, and provide customers with a professional diamond shopping experience.

### Features:

- 🔌 Direct RapNet API integration for real-time diamond inventory
- 💎 Access to thousands of certified diamonds from global suppliers
- 💰 Flexible commission system (percentage or fixed discount)
- 🎨 Customizable product display with multiple column layouts (1-4 columns)
- 📊 Configurable diamond attribute fields with drag-and-drop reordering
- 🖼️ Custom placeholder images for different diamond shapes (Round, Princess, Marquise, etc.)
- 🔍 Advanced filtering by shape, color, clarity, cut, and more
- ⚙️ Admin panel configuration interface for API credentials and settings
- 🛒 Optional Add to Cart and Quick View functionality
- 📄 Pagination with custom posts per page
- 🎯 Easy integration with existing Bagisto stores
- 📱 Responsive design support

## 2. Requirements:

* **PHP**: 8.1 or higher
* **Bagisto**: v2.0.*
* **Composer**: 1.6.5 or higher
* **RapNet Account**: Active RapNet API subscription required

## 3. Installation:

### Step 1: Install the Package

```bash
composer require webbycrown/rapnet-for-bagisto
```

### Step 2: Publish Assets (if needed)

```bash
php artisan vendor:publish --provider="Webbycrown\RapnetBagisto\Providers\RapnetServiceProvider"
```

### Step 3: Clear Cache

```bash
composer dump-autoload
php artisan optimize:clear
```

## 4. Configuration:

### Admin Panel Settings

Navigate to: **Admin Panel → Configuration → APIs → RapNet**

The RapNet extension provides four main configuration sections:

### 4.1 API Settings

Configure your RapNet API credentials:

| Field | Description | Required |
|-------|-------------|----------|
| **API Key** | Your RapNet API Key | ✅ Yes |
| **API Secret** | Your RapNet API Secret Key | ✅ Yes |

> **Note:** Get your API credentials from your [RapNet Account Dashboard](https://www.rapnet.com/)

### 4.2 Template Settings

Customize how diamonds are displayed in your store:

| Field | Description | Options |
|-------|-------------|---------|
| **Commission Type** | How to apply commission on diamond prices | `percent` or `fixed` |
| **Commission Percentage** | Commission amount/percentage | Numeric value |
| **Add to Cart Button** | Show Add to Cart button on product listings | ✅ Enable/Disable |
| **Quick View** | Enable Quick View modal for diamonds | ✅ Enable/Disable |
| **Posts Per Page** | Number of diamonds to display per page | Numeric (e.g., 20, 50) |
| **Load More Data With** | Method for loading more products | `pagination` or `infinite scroll` |
| **Shop Page Loader** | Custom loading image | Upload image file |
| **Product Column** | Grid layout for product display | 1, 2, 3, or 4 columns |
| **Reorder Fields** | Drag-and-drop field ordering | Sortable list |

### 4.3 Placeholder Settings

Upload custom placeholder images for each diamond shape when actual images aren't available:

- **Default Image** - Fallback for any shape
- **Round Image** - For round diamonds
- **Princess Image** - For princess cut diamonds
- **Marquise Image** - For marquise cut diamonds
- **Oval Image** - For oval diamonds
- **Radiant Image** - For radiant cut diamonds
- **Emerald Image** - For emerald cut diamonds
- **Heart Image** - For heart-shaped diamonds
- **Cushion Image** - For cushion cut diamonds
- **Asscher Image** - For asscher cut diamonds

> **Supported formats:** JPG, PNG, BMP, WebP

### 4.4 Shape Settings

Upload shape icons for filter/navigation display:

Upload icons/images for each diamond shape to display in shape filters and navigation menus.

## 5. Available Diamond Attributes:

The extension provides access to the following RapNet diamond attributes:

### Basic Attributes
- **Diamond ID** - Unique identifier
- **Shape** - Diamond shape (Round, Princess, etc.)
- **Size** - Carat weight
- **Color** - Color grade (D-Z scale)
- **Clarity** - Clarity grade (FL-I3 scale)
- **Cut** - Cut grade
- **Polish** - Polish grade
- **Symmetry** - Symmetry grade

### Fancy Color Attributes
- **Fancy Color Intensity** - Color intensity
- **Fancy Color Overtone** - Secondary color
- **Fancy Color Dominant Color** - Primary color

### Measurements
- **Depth Percent** - Depth percentage
- **Table Percent** - Table percentage
- **Measurement** - Dimensions (LxWxD)
- **Meas Length** - Length in mm
- **Meas Width** - Width in mm
- **Meas Depth** - Depth in mm

### Grading Details
- **Girdle Min** - Minimum girdle thickness
- **Girdle Max** - Maximum girdle thickness
- **Girdle Condition** - Girdle finish
- **Culet Size** - Culet size
- **Culet Condition** - Culet condition
- **Fluor Intensity** - Fluorescence intensity
- **Fluor Color** - Fluorescence color

### Certification
- **Lab** - Grading laboratory (GIA, IGI, HRD, etc.)
- **Cert Num** - Certificate number
- **Has Cert File** - Certificate PDF available
- **Eye Clean** - Eye clean designation

### Pricing
- **Price Per Carat** - Per carat price
- **Total Sales Price** - Final price
- **Discount** - Discount percentage
- **Currency Code** - Currency (USD, EUR, etc.)
- **Currency Symbol** - $ £ € etc.

### Media
- **Has Image File** - Product image available
- **Image File URL** - Image URL
- **Video URL** - Video URL
- **Has Sarineloupe** - Sarine loupe available

### Supplier Information
- **Company** - Supplier company name
- **Stock Num** - Supplier stock number
- **Country** - Supplier country
- **Account ID** - RapNet account ID

## 6. Field Reordering:

The extension includes a powerful drag-and-drop field reordering system:

### How to Reorder Fields:

1. Navigate to **Configuration → APIs → RapNet → Template Settings**
2. Find the **Reorder Fields** section
3. **Active Column**: Fields currently displayed
4. **Inactive Column**: Hidden fields

### Reorder Process:

- **Drag fields** between Active/Inactive columns
- **Reorder fields** within the Active column to change display order
- **Edit labels** by clicking the edit icon next to any field
- **Custom labels** will be saved and displayed instead of default labels

### Example Configuration:

**Active Fields (Displayed):**
1. Checkbox
2. Shape
3. Size
4. Color
5. Clarity
6. Cut
7. Lab
8. Price/CT
9. Total Price
10. Action

**Inactive Fields (Hidden):**
- Fancy Color Intensity
- Fancy Color Overtone
- Fluor Intensity
- Polish
- Symmetry
- etc.

## 7. Pricing & Commission:

### Commission Types:

#### Percentage Discount
```
Final Price = (RapNet Price) × (1 + Commission%)
Example: $5,000 × (1 + 0.15) = $5,750
```

#### Fixed Discount
```
Final Price = RapNet Price + Fixed Amount
Example: $5,000 + $500 = $5,500
```

### Setting Commission:

1. Go to **Configuration → APIs → RapNet → Template Settings**
2. Select **Commission Type** (percent or fixed)
3. Enter **Commission Percentage** (e.g., 15 for 15% or 500 for $500)
4. Save configuration

## 8. Frontend Integration:

### Display Options:

#### Product Grid Columns
- **4 Column Layout** - Compact grid, more products visible
- **3 Column Layout** - Balanced view
- **2 Column Layout** - Larger product cards
- **1 Column Layout** - Detailed list view

#### Additional Features
- **Add to Cart Button** - Enable instant cart addition
- **Quick View** - Modal popup with diamond details
- **Pagination** - Standard page navigation
- **Infinite Scroll** - Auto-load more products on scroll

## 9. API Integration:

### How It Works:

1. **API Connection**: Extension connects to RapNet API using your credentials
2. **Data Sync**: Diamond inventory is fetched in real-time
3. **Price Calculation**: Commission is applied based on your settings
4. **Display**: Diamonds are displayed according to your template settings
5. **Filtering**: Customers can filter by shape, size, color, clarity, etc.
6. **Ordering**: Customers can add diamonds to cart and complete purchase

### Data Flow:

```
RapNet API → Extension → Price Calculation → Display → Customer Purchase
```

## 10. FAQ:

**Q: Do I need a RapNet account?**  
A: Yes, you need an active RapNet API subscription to use this extension.

**Q: Are diamond prices updated in real-time?**  
A: Yes, prices are fetched from RapNet API based on your sync settings.

**Q: Can I customize the commission per diamond?**  
A: The extension applies a global commission rate. Custom per-diamond pricing requires additional customization.

**Q: What diamond shapes are supported?**  
A: All standard shapes: Round, Princess, Marquise, Oval, Radiant, Emerald, Heart, Cushion, Asscher, Pear, and more.

**Q: Can I hide certain diamond attributes?**  
A: Yes, use the Field Reordering feature to move unwanted fields to the Inactive column.

**Q: Are diamond images included?**  
A: Yes, if available from RapNet. You can also upload custom placeholder images for each shape.

**Q: Can customers filter diamonds?**  
A: Yes, the extension supports filtering by all major attributes (shape, color, clarity, cut, price range, etc.).

**Q: Is the extension compatible with Bagisto themes?**  
A: Yes, it integrates with standard Bagisto themes. Custom themes may require minor adjustments.

## 11. Troubleshooting:

**API connection fails:**
- Verify API Key and API Secret are correct
- Check RapNet account is active and has API access
- Ensure your server can make outbound HTTPS requests
- Check firewall/security settings

**Diamonds not displaying:**
- Confirm API credentials are configured
- Check if fields are in the Active column (Field Reordering)
- Verify your RapNet account has inventory access
- Clear cache: `php artisan cache:clear`

**Images not showing:**
- Upload placeholder images for each shape
- Check image file formats (JPG, PNG, WebP)
- Verify storage permissions
- Ensure AWS_FILE_PATH is set if using S3

**Commission not applying:**
- Check Commission Type is selected (percent or fixed)
- Verify Commission Percentage field has a value
- Clear configuration cache: `php artisan config:clear`

**Field reordering not working:**
- Clear browser cache
- Check JavaScript console for errors
- Ensure jQuery and jQuery UI are loaded
- Try re-saving the configuration

## 12. Support:

- 🐛 [Report Issues](https://github.com/webbycrown/rapnet-for-bagisto/issues)
- 📧 Email: info@webbycrown.com
- 🌐 Website: [webbycrown.com](https://webbycrown.com)
- 📖 RapNet API Docs: [rapnet.com/api](https://www.rapnet.com/)

## 13. Changelog:

### v1.0.1 - 2025-11-14

#### 📚 Documentation Release

- 📖 Complete comprehensive README with detailed documentation
- 🔧 Added detailed API configuration guide with credential setup
- 💡 Added template customization guide with all options
- 🎨 Added placeholder and shape image upload instructions
- 📊 Documented all 40+ diamond attributes with descriptions
- 🔄 Added field reordering system documentation with examples
- 💰 Added pricing and commission calculation examples
- ❓ Added comprehensive FAQ section (8 questions)
- 🛠️ Added troubleshooting guide for common issues
- 🌐 Added frontend integration options documentation
- 🐛 Fixed namespace in RapnetServiceProvider.php
- 📋 Added CHANGELOG.md for version tracking
- 🚀 Added RELEASE_NOTES.md for GitHub releases
- 🔑 Enhanced composer.json with SEO keywords
- 📦 Set package to stable release ready for production

---

### v1.0.0 - 2024-01-01

#### ✨ Initial Release

- 🎉 Initial release of **RapNet for Bagisto**
- 🔌 Full RapNet API integration for diamond inventory management
- 💎 Real-time access to global diamond inventory
- 💰 Flexible commission system with percentage and fixed options
- 🎨 Customizable product display with 1-4 column layouts
- 📊 Advanced drag-and-drop field reordering system
- 🖼️ Custom placeholder images for all diamond shapes
- 🔍 Comprehensive diamond attribute filtering
- ⚙️ Admin panel configuration interface
- 🛒 Optional Add to Cart and Quick View features
- 📄 Configurable pagination and infinite scroll
- 🌍 Multi-currency support

#### 📚 Documentation

- 📖 Comprehensive README with detailed setup guide
- 🔧 API configuration instructions
- 💡 Template customization examples
- 🎨 Placeholder and shape image upload guide
- ❓ FAQ section answering common questions
- 🛠️ Troubleshooting guide for common issues
- 📋 Complete diamond attributes reference
- 📚 Field reordering instructions

#### 🔄 Package

- 📦 Stable package version for production use
- ✨ Simple installation: `composer require webbycrown/rapnet-for-bagisto`
- 🏷️ Properly tagged and versioned for Packagist
- 📦 Published to Packagist: [webbycrown/rapnet-for-bagisto](https://packagist.org/packages/webbycrown/rapnet-for-bagisto)
- 🐙 Open source on GitHub: [webbycrown/rapnet-for-bagisto](https://github.com/webbycrown/rapnet-for-bagisto)

---

<div align="center">
  <strong>Made with ❤️ by <a href="https://webbycrown.com">WebbyCrown</a></strong>
</div>

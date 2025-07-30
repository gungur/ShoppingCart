# Shopping Cart System

## Overview
This Java program implements a shopping cart system for a grocery market. It provides functionality to manage market items, add/remove items from a cart, calculate totals, and generate summaries. The system includes two main classes: `ShoppingCart` (core functionality) and `ShoppingCartTester` (unit tests).

## Features

### Core ShoppingCart Class
- **Product Lookup**: Search for products by name or ID
- **Cart Management**: 
  - Add items to cart
  - Remove items from cart
  - Empty cart completely
  - Check for item presence
  - Count item occurrences
- **Price Calculations**: 
  - Get individual product prices
  - Calculate total with tax
- **Reporting**:
  - Generate cart summary
  - Create deep copies of market items

### Testing Class (ShoppingCartTester)
Comprehensive unit tests for all major functionality:
- Product lookup tests
- Price calculation tests
- Cart operation tests (add/remove/empty)
- Summary generation tests
- Integrated test runner

## How to Use

### Running the Program
1. Compile both Java files:
   ```
   javac ShoppingCart.java ShoppingCartTester.java
   ```
2. Run the tester:
   ```
   java ShoppingCartTester
   ```

### Key Methods

**Product Information:**
- `lookupProductByName(String name)`: Find product details by name
- `lookupProductById(int id)`: Find product details by ID
- `getProductPrice(String name)`: Get price of an item
- `getCopyOfMarketItems()`: Get a deep copy of all market items

**Cart Operations:**
- `addItemToCart(String item, String[] cart, int size)`: Add item to cart
- `removeItem(String[] cart, String item, int size)`: Remove item from cart
- `emptyCart(String[] cart, int size)`: Empty the cart completely
- `contains(String item, String[] cart, int size)`: Check if item is in cart
- `nbOccurrences(String item, String[] cart, int size)`: Count item occurrences

**Checkout:**
- `checkout(String[] cart, int size)`: Calculate total with tax
- `getCartSummary(String[] cart, int size)`: Generate formatted cart summary

## Testing
The `ShoppingCartTester` class includes comprehensive unit tests for all functionality. Run all tests with:
```java
ShoppingCartTester.runAllTests();
```

Individual test methods are also available:
- `testLookupMethods()`
- `testGetProductPrice()`
- `testAddItemToCartContainsNbOccurrences()`
- `testRemoveItem()`
- `testCheckoutGetCartSummary()`

## Data Structure
The market items are stored in a 2D String array with the format:
```
marketItems[i][0] = item ID
marketItems[i][1] = item name
marketItems[i][2] = item price (with $ prefix)
```

## Example Usage
```java
// Create a cart
String[] cart = new String[10];
int cartSize = 0;

// Add items
cartSize = ShoppingCart.addItemToCart("Apple", cart, cartSize);
cartSize = ShoppingCart.addItemToCart("Banana", cart, cartSize);

// Get summary
String summary = ShoppingCart.getCartSummary(cart, cartSize);

// Checkout
double total = ShoppingCart.checkout(cart, cartSize);
```

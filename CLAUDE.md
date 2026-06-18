# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a React-based expense tracker application built with Vite. The project is a starter template for learning React development and intentionally includes areas for improvement (bugs, UI issues, code organization).

## Commands

```bash
# Start development server (Vite runs on http://localhost:5173)
npm run dev

# Build for production
npm build

# Run ESLint to check code quality
npm run lint

# Preview production build locally
npm run preview
```

## Architecture & Code Structure

### Project Layout

- **`src/App.jsx`** - Main application component containing all business logic and UI. This is the sole component and where all improvements should be made.
- **`src/main.jsx`** - Entry point that mounts the App component
- **`src/App.css`** - Styling for the application
- **`src/index.css`** - Global styles
- **`vite.config.js`** - Vite configuration with React plugin
- **`eslint.config.js`** - ESLint configuration with React hooks and refresh plugins

### Application Logic

The App component manages:

1. **Transaction State** - Array of transactions with properties: `id`, `description`, `amount`, `type` (income/expense), `category`, `date`
2. **Form State** - Input fields for adding new transactions (description, amount, type, category)
3. **Filter State** - Two filters for transactions (filterType, filterCategory)
4. **Calculations** - totalIncome, totalExpenses, and balance are derived from filtered transactions (note: amounts are strings, not numbers)
5. **Categories** - Hard-coded array: food, housing, utilities, transport, entertainment, salary, other

### Key Implementation Details

- **State Management**: Uses React hooks (useState) for all state
- **Form Handling**: onSubmit handler adds new transactions to the beginning of the array
- **Filtering**: Transactions are filtered sequentially by type and category
- **Date Format**: Uses ISO date format (YYYY-MM-DD)
- **Amount Handling**: Currently stored as strings (not numbers) - this may be a bug to address
- **Summary Calculations**: Income/expense totals treat string amounts as if they were numbers (implicit coercion)

## Development Notes

- The app includes sample seed data in the initial state for testing
- ESLint is configured to ignore unused variables starting with uppercase or underscore
- React Refresh is enabled for hot module replacement during development
- The project follows ES modules (type: "module" in package.json)

## Known Areas for Improvement

As a learning project, there are intentional issues:
- All logic in a single component (lacks component separation)
- Amount values are strings instead of numbers
- UI could be more polished
- Code organization could be improved
- No data persistence (resets on page reload)

# Dashboard Folder Structure Example

```bash
/src
  /assets
    /images
    /styles
      global.css
  /components
    /Header
      Header.js
      Header.css
    /Sidebar
      Sidebar.js
      Sidebar.css
    /Card
      Card.js
      Card.css
  /features
    /Analytics
      Analytics.js
      Analytics.css
    /UserManagement
      UserList.js
      UserDetails.js
      UserManagement.css
    /Settings
      Settings.js
      Settings.css
  /context
    ThemeContext.js
  /hooks
    useAuth.js
    useFetch.js
  /layout
    DashboardLayout.js
    DashboardLayout.css
  /services
    api.js
  /utils
    formatDate.js
    calculateStats.js
  App.js
  index.js
  index.css
```

## 1. assets/

- For static files like images, global styles, and fonts.
- Example: global.css for global styling like resets or utility classes.
- Images for logos, icons, etc.

## 2. components/

- Reusable, generic UI components shared across the dashboard.
- Header: Contains the top navigation bar.

Header.js
Sidebar.js
A Card component

## 3. features/

Feature-specific components grouped by functionality.

### Analytics

- Handles data visualization and stats.
- Example: Analytics.js shows graphs or tables.

### UserManagement

- Contains pages or components like UserList and UserDetails.

### Settings

- Manages user preferences, themes, etc.

## 4. context/

For managing global state with React Context API.

```jsx
import { createContext, useState } from "react";

const ThemeContext = createContext();

function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

export { ThemeContext, ThemeProvider };
```

## 5. hooks/

Custom hooks for reusable logic.

useFetch.js

```jsx
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);

  return data;
}

export default useFetch;
```

## 6. layout/

Defines the main layout of the dashboard.

```jsx
import React from "react";
import Header from "../components/Header";
import Sidebar from "../components/Sidebar";

function DashboardLayout({ children }) {
  return (
    <div className="dashboard-layout">
      <Header />
      <Sidebar />
      <main>{children}</main>
    </div>
  );
}

export default DashboardLayout;
```

## 7. services/

For API Integration

```jsx
export const getUsers = async () => {
  const response = await fetch("/api/users");
  return response.json();
};
```

## 8. utils/

Utility or Helper functions for common tasks.

```jsx
export const calculateAverage = (numbers) => {
  return numbers.reduce((a, b) => a + b, 0) / numbers.length;
};
```

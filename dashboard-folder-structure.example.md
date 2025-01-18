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

```Header.js:
import React from 'react';
import './Header.css';

function Header() {
  return <header className="header">Dashboard Header</header>;
}

export default Header;
```

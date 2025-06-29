# Flows Auth: Svelte Authentication Library with WebAuthn Support

![GitHub Release](https://img.shields.io/badge/Release-v1.0.0-brightgreen) [![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/Rudragiri-Gosai/flows-auth/actions)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Overview

Flows Auth is a robust authentication library designed for Svelte applications. It provides seamless integration of WebAuthn and passkey support specifically tailored for Thepia Flow applications. This library simplifies the process of implementing secure authentication mechanisms, allowing developers to focus on building their applications without worrying about the intricacies of authentication.

## Features

- **WebAuthn Support**: Leverage the latest standards for secure authentication.
- **Passkey Integration**: Simplify user logins with passkeys.
- **Svelte Compatibility**: Built to work seamlessly with Svelte applications.
- **TypeScript Support**: Enjoy type safety and enhanced development experience.
- **Whitelabeling**: Customize the authentication experience to fit your brand.
- **OAuth Integration**: Easily connect with various OAuth providers.

## Installation

To install Flows Auth, you can use npm or yarn. Run one of the following commands in your terminal:

```bash
npm install flows-auth
```

or

```bash
yarn add flows-auth
```

## Usage

To use Flows Auth in your Svelte application, import the library and initialize it. Here’s a simple example:

```javascript
import { Auth } from 'flows-auth';

const auth = new Auth({
  // Configuration options
  clientId: 'your-client-id',
  redirectUri: 'your-redirect-uri',
});

// Initiate login
auth.login();
```

### Configuration Options

| Option        | Type     | Description                          |
|---------------|----------|--------------------------------------|
| `clientId`   | string   | Your application's client ID.       |
| `redirectUri`| string   | The URI to redirect after login.    |
| `scopes`     | array    | The scopes you want to request.     |

## API Reference

### Auth Class

#### `constructor(options: AuthOptions)`

Creates a new instance of the Auth class.

- **Parameters**:
  - `options`: An object containing configuration options.

#### `login()`

Initiates the login process.

#### `logout()`

Logs the user out of the application.

#### `getUser()`

Returns the currently authenticated user.

## Examples

### Basic Login Flow

Here’s a simple example demonstrating the login flow:

```javascript
import { Auth } from 'flows-auth';

const auth = new Auth({
  clientId: 'your-client-id',
  redirectUri: 'your-redirect-uri',
});

async function handleLogin() {
  try {
    await auth.login();
    const user = auth.getUser();
    console.log('Logged in user:', user);
  } catch (error) {
    console.error('Login failed:', error);
  }
}

handleLogin();
```

### Logout Example

To log the user out, you can call the `logout` method:

```javascript
async function handleLogout() {
  try {
    await auth.logout();
    console.log('User logged out');
  } catch (error) {
    console.error('Logout failed:', error);
  }
}

handleLogout();
```

## Contributing

We welcome contributions to Flows Auth! If you want to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/YourFeature`).
6. Open a Pull Request.

Please ensure that your code adheres to our coding standards and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

For the latest releases, please visit the [Releases](https://github.com/Rudragiri-Gosai/flows-auth/releases) section. You can download the latest version and execute it in your application.

## Contact

For questions or feedback, feel free to open an issue in the repository or contact the maintainer directly.

---

Feel free to explore the repository and integrate Flows Auth into your Svelte applications. We hope this library helps you streamline your authentication processes effectively.
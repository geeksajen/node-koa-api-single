## Getting Started

### Requirements

* Mac OS X, Windows, or Linux
* [npm](https://www.npmjs.com/) package + [Node.js](https://nodejs.org/) v7.9.0 or
  newer

### Directory Layout

Before you start, take a moment to see how the project structure looks like:

```
.
├── /sample/                    # Sample Code
├── /node_modules/              # 3rd-party libraries and utilities
├── /src/                       # The source code of the application
│   ├── /config/                # Configuration
│   ├── /lib/                   # Our library
│   ├── /routes/                # API routes folder
│   ├── /system/                # System plugins / modules
│   ├── /app.js                 # Application layer component
│   ├── /server.js              # Server layer component
│   ├── /start.js               # Main entry point
│   └── ...                     # Others
├── /test/                      # Unit and end-to-end tests
├── Dockerfile                  # Commands for building a Docker image for production
├── docker-compose.yml          # Commands for building a Docker image for production
├── package.json                # The list of 3rd party libraries and utilities
```

### Quick Start

#### Run `npm install`

#### Run `docker-compose up` (Optional)

If you have redis/mysql on your dev machine already, skip this step.

#### Modify `src/config/db.js` (Optional)

```
module.exports = {
  'maindb': {
    'client': 'mysql',
    'connection': {
      'host': '127.0.0.1',
      'port': 3307,
      'user': 'user',
      'password': 'password',
      'database': 'sampledb',
      'multipleStatements': true
    },
    'pool': {
      'min': 0,
      'max': 10
    }
  }
};
```

#### Modify `src/system/redis/index.js` (Optional)

```node.js
  this.createClient('main', 'main', '127.0.0.1', 6379);
  this.createClient('sub-main', 'sub-main', '127.0.0.1', 6379);
```

#### Run `npm run start-dev`

> [http://localhost:1337/](http://localhost:1337/) — Node.js server

Now you can open your web app in a browser.

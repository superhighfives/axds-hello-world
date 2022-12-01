# AXDS Hello World

The **AXDS Hello World** example contains the minimum code needed to get a simple Single Page Application (SPA) on LWR running in Typescript, with [AXDS](https://github.com/OneAppExchange/appx-design-system).

## Project Setup

The directory structure looks like this:

```
scripts/
  └── start-server.mjs  // create and start server
src/
  ├── assets/           // static assets
  │   └── recipes-logo.png
  └── modules/          // lwc modules
      └── example/
          └── app/
              ├── app.css
              ├── app.html
              └── app.ts
lwr.config.json         // lwr configuration
package.json            // npm packaging configuration
.npmrc                  // npm setup information
```

## Configuration

The LWR server is configured in `lwr.config.json`, at the root of the project. The **LWC TS Boilerplate** example has one LWC module and one server-side route.

```json
// lwr.config.json
{
    "lwc": {
        "modules": [
            {
                "dir": "$rootDir/src/modules"
            },
            {
                "npm": "@oneappexchange/appx-design-system"
            }
        ]
    },
    "routes": [
        {
            "id": "home",
            "path": "/",
            "rootComponent": "home/app",
            "layoutTemplate": "$layoutsDir/main.html"
        }
    ]
}

```

## Running the Project

```bash
yarn install
yarn build
yarn start # prod mode and ESM format
```

Open the site at [http://localhost:3000](http://localhost:3000)

To start the project in a different mode:

-   dev: `yarn dev`
-   compat: `yarn start:compat`
-   prod-compat: `yarn start:prod-compat`

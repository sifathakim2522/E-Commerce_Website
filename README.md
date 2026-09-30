# E-commerce Website

A full-stack commerce project with a React storefront, a separate admin interface, and an Express API backed by MongoDB.

## Project structure

| Directory | Purpose |
| --- | --- |
| frontend/ | Customer storefront built with React and Vite |
| admin/ | React administration interface |
| backend/ | User, product, cart, and order APIs |

The backend includes Cloudinary image handling and payment-related integrations. Payment functionality requires provider configuration and testing; this repository is a development project, not a production-readiness claim.

## Local setup

Use Node.js 22.12+ and npm. You also need MongoDB and configuration for the services you intend to use.

1. Copy backend/.env.example to backend/.env and supply your own values.
2. Copy frontend/.env.example and admin/.env.example to .env in their respective directories.
3. Install and run each component in its own terminal:

```sh
cd backend
npm ci
npm run dev
```

```sh
cd frontend
npm ci
npm run dev
```

```sh
cd admin
npm ci
npm run dev
```

The API defaults to port 4000. Open the frontend and admin URLs printed by Vite. Both interfaces use VITE_BACKEND_URL to locate the API.

The database connection code appends /e-commerce to MONGODB_URI; use a compatible base URI such as mongodb://127.0.0.1:27017. Cloudinary credentials configure uploads. Use test credentials when developing payment flows.

## Checks

Run npm run build and npm run lint separately in frontend/ and admin/. There is no backend test script configured.

## Development notes

- Keep .env files and installed dependencies out of version control.
- Use environment templates as configuration guides, never as real credentials.
- Review authentication, payment verification, validation, and deployment configuration before accepting real customers or payments.
- Automated tests and a verified deployment walkthrough are useful next milestones.

## Attribution

Preserve any existing third-party license and asset notices. No new repository-wide license is granted by this README.

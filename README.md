{
  "name": "elevenlabs-docs",
  "private": true,
  "version": "1.0.0",
  "description": "ElevenLabs Documentation",
  "scripts": {
    "dev": "fern docs dev",
    "fmt": "prettier \"**/*.{css,js,ts,tsx,md,mdx,yml,yaml,json}\" --write && pnpm run fmt:openapi",
    "fmt:check": "prettier \"**/*.{css,js,ts,tsx,md,mdx,yml,yaml,json}\" --check",
    "fmt:openapi": "openapi-format ./fern/apis/api/openapi.json -o ./fern/apis/api/openapi.json",
    "fern:upgrade": "fern upgrade",
    "fern:check": "fern check",
    "fern:preview-merge": "fern write-definition --api api",
    "docs:preview": "fern generate --docs --preview",
    "sdk:preview": "fern generate --group python-sdk --preview --api api && fern generate --group typescript-sdk --preview --api api",
    "openapi:update": "curl -o ./fern/apis/api/openapi.json https://api.elevenlabs.io/openapi.json && pnpm run fmt:openapi",
    "openapi:lint": "pnpm lint-openapi ./fern/apis/api/openapi.json",
    "ci": "pnpm run fern:check && pnpm run fmt:check"
  },
  "keywords": [
    "elevenlabs",
    "documentation",
    "api",
    "docs"
  ],
  "author": "elevenlabs",
  "license": "MIT",
  "devDependencies": {
    "@trivago/prettier-plugin-sort-imports": "^5.2.0",
    "fern-api": "^0.53.15",
    "ibm-openapi-validator": "^1.33.2",
    "openapi-format": "^1.25.0",
    "prettier": "3.4.2",
    "prettier-plugin-tailwindcss": "^0.6.9"
  }
}
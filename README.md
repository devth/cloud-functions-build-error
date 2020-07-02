# Cloud Functions Build Error Repro

Demonstrates generic `Build failed: Build error details not available` error in
Cloud Functions, due to suspected build timeout because of the amount of
dependencies in `package.json`.

## Usage

Use `.env` to set Firebase credentials:

```
FIREBASE_API_KEY=
FIREBASE_AUTH_DOMAIN=
FIREBASE_DATABASE_URL=
FIREBASE_PROJECT_ID=
FIREBASE_STORAGE_BUCKET=
FIREBASE_APP_ID=
```

Install deps:

```bash
yarn
```

Then deploy functions with:

```bash
yarn deploy-fns
# or
yarn deploy-fns --debug
```

Sample output

```
i  deploying functions
i  functions: ensuring necessary APIs are enabled...
✔  functions: all necessary APIs are enabled
i  functions: preparing ./ directory for uploading...
i  functions: packaged ./ (577.38 KB) for uploading
✔  functions: ./ folder uploaded successfully
i  functions: creating Node.js 10 (Beta) function addMessage(us-central1)...

⚠  functions[addMessage(us-central1)]: Deployment error.
Build failed: Build error details not available.


Functions deploy had errors with the following functions:
        addMessage


To try redeploying those functions, run:
    firebase deploy --only functions:addMessage


To continue deploying other features (such as database), run:
    firebase deploy --except functions

Error: Functions did not deploy properly.
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```


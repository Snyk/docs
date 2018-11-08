---
title: "NodeJS Onboarding"
---

To start using Snyk Runtime Protection for your NodeJS applications, add the [@snyk/nodejs-runtime-agent](https://www.npmjs.com/package/@snyk/nodejs-runtime-agent) dependency to your project by running:

```
npm install @snyk/nodejs-runtime-agent
```

in your project folder, and configure it as soon as possible in your application’s start sequence. Here’s an example of such a flow:

```
require('@snyk/nodejs-runtime-agent')({
  projectId: '0462e42b-c92f-4b48-bac8-81eb3ff7f43e',
});

const express = require('express');
...
```

Make sure to have `require('@snyk/nodejs-runtime-agent')` prior to any other `require` statement.

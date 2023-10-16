# NestJS MongoDB testing

A package providing testing utilities for NestJS APIs using MongoDB.

# Table of contents

1. [Installation](#installation)
2. [Documentation](#documentation)

# Installation

You can install the package using the following commands:

```bash
# yarn
yarn add -D nestjs-mongo-testing

# npm
npm install -d nestjs-mongo-testing
```

# Documentation

Create a test MongoDB database by importing the `TestMongooseModule` in your test module.

```ts
import { TestMongooseModule } from 'nestjs-mongo-testing';

async function setup(): Promise<void> {
  const rootModule: TestingModule = await Test.createTestingModule({
    imports: [TestMongooseModule]
  }).compile();
}
```

Stop the memory server in your teardown function:

```ts
import { MemoryServer } from 'nestjs-mongo-testing';

// Execute this at the end of your test.
async function teardown(): Promise<void> {
  await MemoryServer.getInstance().stop();
}
```

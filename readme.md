# Next.js Plop Templates

[![npm version](https://badge.fury.io/js/nextjs14-plop-templates.svg)](https://badge.fury.io/js/nextjs14-plop-templates)

Plop templates for Next.js 14 , supporting both TypeScript and JavaScript.

## Features

- Templates for React components
- Templates for Next.js API routes
- Templates for Next.js pages
- Support for both TypeScript and JavaScript
- Dynamic route generation
- Customizable component structure (atoms, molecules, organisms)

## Installation

First, ensure you have Plop installed:

```bash
npm install --save-dev plop
```

Then, install this package in your project:

```bash
npm install --save-dev nextjs14-plop-templates
```

## Usage

1. Create a `plopfile.js` in your project root if you don't already have one.

2. Add the following to your `plopfile.js`:

```javascript
const nextjsGenerators = require("nextjs14-plop-templates");

module.exports = function (plop) {
  nextjsGenerators(plop);
};
```

3. Run Plop in your terminal:

```bash
npm run plop
```

4. Choose the generator you want to use:

   - Component
   - API
   - Page

5. Follow the prompts to generate your files.

## Compatibility

### This package is compatible with:

- Next.js 14
- Next.js 15

The templates and generators provided by this package are designed to work with Next.js 14 and 15. They should continue to function correctly unless there are significant structural changes in future Next.js releases.

## Generators

### Component Generator

Creates a new React component.

Options:

- Component name
- Component type (atom, molecule, organism, or none)
- TypeScript or JavaScript

Example output:

```typescript
import { ReactElement } from "react";

type ButtonProps = {};

const Button = ({}: ButtonProps): ReactElement => {
  return <div>Button</div>;
};

export default Button;
```

### API Route Generator

Creates a new Next.js API route.

Options:

- Route name
- HTTP methods (GET, POST, PUT, DELETE)
- Dynamic routes

Example output (with dynamic route "id"):

```typescript
import { NextRequest, NextResponse } from "next/server";

export async function GET(request: NextRequest, { params }: { params: { id: string } }) {
  const id = params.id;
  // Your GET logic here
  return NextResponse.json({ message: `GET request for id: ${id}` });
}

export async function POST(request: NextRequest, { params }: { params: { id: string } }) {
  const id = params.id;
  // Your POST logic here
  return NextResponse.json({ message: `POST request for id: ${id}` });
}

// Add other methods (PUT, DELETE) as needed
```

### Page Generator

Creates a new Next.js page.

Options:

- Page name
- Dynamic routes

Example output:

```typescript
import { ReactElement } from "react";

export default function Page(): ReactElement {
  return (
    <div>
      <h1>Hello World</h1>
    </div>
  );
}
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License.

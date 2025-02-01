# Next.js 15 App Router Bug: Unexpected Behavior with Default Exports

This repository demonstrates a subtle bug in Next.js 15's App Router when a page component uses a default export and lacks dynamic imports.  The issue manifests as unexpected behavior during development and potential runtime issues.

## Bug Description

When using a page component with a default export and no dynamic imports within Next.js 15 App Router, the application might show unexpected rendering issues, especially during development. The expected behavior is that the page renders correctly, and it will, when deployed to a production server. But it may show errors when running locally.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the unexpected behavior in the browser.

## Solution

The solution involves using named exports. Even if you're just returning one component, explicitly export it by name. This removes ambiguity and helps Next.js 15 correctly handle the page component.

## Additional Notes

This bug is specific to the way the Next.js App Router handles default exports in conjunction with how components are loaded during development. The impact is subtle but might cause confusion. 
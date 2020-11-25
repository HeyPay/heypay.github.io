# Code Standards

This documentation is a guide for your path as a developer 👩‍💻🧑‍💻. The following code standards must be applied for every feature or piece of code you touch, trying always to leave the code better than you found it. 

# Table of Contents
1. [General rules](#general-rules)

## General rules <a name="general-rules">

- Imports should follow these criteria regarding the order:
    - Imports from external packages should go before import from internal packages.
    - Imports should be in alphabetical order taking in consideration that `@` goes before other characters.
    - When importing multiple elements from a file, they should also be imported in alphabetical order.

- Collection and sub-collection entities should be added to `functions/src/collections` subfolder, use their plural wording and at least an interface representing it's data structure. For example for an entity of type `device`, create `functions/src/collections/devices/devices.model.ts` file, with an interface as `export interface Device { ... }`.  

- Global scope variables that will be used on functions should start with an underscore `_`. For example:
```typescript
let _accountCategoryConfig: AccountCategoryConfig;

export function coolLogicToDoStuff() {
...
```

- All dependency declared on `package.json` must have their version locked, for example: `moment": "2.24.0"`. 

- All functions must specify their return type, for example: `awesomeFunctionToDoStuff(): Promise<void>`.

- On Typescript files, use single-quotes `'` instead of double quotes `"`.

- Setup your IDE to use 2 spaces configuration for indentation.

- Use template literals over string concatenation, for example: 
```typescript
const fullName = firstName + ' ' + lastName; // Wrong
const fullName = `${firstName} ${lastName}`; // Nice!
```

# Code Standards

This documentation is a guide for your path as a developer 👩‍💻🧑‍💻. The following code standards must be applied for every feature or piece of code you touch, trying always to leave the code better than you found it. 

# Table of Contents
1. [General rules](#general-rules)

## General rules <a name="general-rules">

- Every `component`, `modal`, `page` and `tab` must comply the following naming:
    - `<view_name>.<component | modal | page | tab>.html`
    - `<view_name>.<component | modal | page | tab>.scss`
    - `<view_name>.<component | modal | page | tab>.spec.ts`
    - `<view_name>.<component | modal | page | tab>.ts`

For example, a new modal should be named as follows: `<view_name>.modal.html`, `<view_name>.modal.scss`, `<view_name>.modal.spec.ts` and `<view_name>.modal.ts`.

- Module imports should follow these criteria regarding the order:
    - Imports should be separated in groups as follows:
        - Angular packages
        - Ionic packages
        - Other external packages
        - App internal packages
    - Then each group must be ordered alphabetically, taking in consideration that `@` goes before other characters.
    - Imports should be in alphabetical order taking in consideration that `@` goes before other characters.
    - When importing multiple elements from a file, they should also be imported in alphabetical order.

- Elements within a class should be in the following order:
    1. Public variables in alphabetical order.
    2. Private variables in alphabetical order (should always start with an underscore `_`).
    3. Constructor
    4. Platform specific functions
    5. Public functions
    6. Private functions
    7. Getter and setters

- Functions within a class should be in the following order:
    1. Calls to platform specific events, such as `ngOnInit()`, in alphabetical order.
    2. Public functions in alphabetical order.
    3. Private functions in alphabetical order (should always start with an underscore `_`).

- Declarations inside a constructor should be in alphabetical order.

- All dependency declared on `package.json` must have their version locked, for example: `moment": "2.24.0"`. 

- All functions must specify their return type, for example: `awesomeFunctionToDoStuff(): Promise<void>`.

- On Typescript files, use single-quotes `'` instead of double quotes `"`.

- Setup your IDE to use 2 spaces configuration for indentation.

- Use template literals over string concatenation, for example: 
```typescript
const fullName = firstName + ' ' + lastName; // Wrong
const fullName = `${firstName} ${lastName}`; // Nice!
```

- Platform specific event functions, such as `ngOnInit()` should not have direct logic inside them, use a private function with a descriptive name and them call it, for example:
```typescript
ngOnInit(): void {
  this._setSubscriptions();
}

private _setSubscriptions(): void {
  this._usersSubscription = this.usersSvc.getAll().subscribe((users) => ...);
  ... 
}
```

- For each subscribe call it must have a subscription reference, which then must be handled in order to unsubscribe when is no longer needed. 

- Run `npm run lint` before submitting a pull request.

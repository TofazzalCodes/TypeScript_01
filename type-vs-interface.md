# Type vs Interface in TypeScript: What Is the Difference?

## Introduction

TypeScript provides two common ways to define the structure of data: `type` aliases and `interface`. Both help developers describe the shape of objects and make code safer. However, they have some important differences. Understanding these differences helps us choose the right one for a project.

## Detailed Explanation

An `interface` is mainly used to define the structure of an object.

```ts
interface User {
  name: string;
  age: number;
}

const user: User = {
  name: "Rakib",
  age: 22
};
```

A `type` alias can define the same object structure.

```ts
type User = {
  name: string;
  age: number;
};
```

Both examples work in the same way. They tell TypeScript that a user must have a string `name` and a number `age`.

One important difference is that interfaces support declaration merging. This means we can declare the same interface more than once, and TypeScript combines them. Type aliases do not support declaration merging.

Both can also be extended using different syntax.

```ts
interface Admin extends User {
  role: string;
}

type AdminUser = User & {
  role: string;
};
```

Another advantage of `type` is that it supports union types.

```ts
type Status = "loading" | "success" | "error";
```

## Conclusion

Use `interface` when describing object structures, especially when they may need to be extended. Use `type` when working with unions, intersections, tuples, or more complex types. Both are useful, so choose the one that makes your code easier to understand.
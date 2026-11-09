# Combining Union and Intersection Types in TypeScript

## Introduction

TypeScript provides powerful features to define flexible and reusable types. Two important features are Union (`|`) and Intersection (`&`) types. Union types allow a variable to accept multiple possible types, while Intersection types combine multiple types into one. We can use both together to create flexible object structures.

## Detailed Explanation

### 1. Union Types (`|`)

A Union type allows a variable to accept more than one type.

```ts
type Status = "active" | "inactive";

let userStatus: Status = "active";
```

Here, `userStatus` can only contain `"active"` or `"inactive"`. If we assign another value, TypeScript will show an error.

### 2. Intersection Types (`&`)

An Intersection type combines multiple types into one.

```ts
type User = {
  name: string;
  age: number;
};

type Employee = {
  employeeId: number;
  department: string;
};

type Staff = User & Employee;
```

Now, the `Staff` type contains all properties from both `User` and `Employee`.

### 3. Combining Union and Intersection

We can combine both concepts in a practical example.

```ts
type Admin = User & {
  role: "admin";
};

type Customer = User & {
  role: "customer";
};

type Account = Admin | Customer;

const account: Account = {
  name: "Rakib",
  age: 25,
  role: "admin"
};
```

Here, an account can be either an Admin or a Customer, but both must follow the User structure.

## Conclusion

Union types help us define multiple possible options, while Intersection types combine different structures. Using both together makes TypeScript code more flexible, reusable, and type-safe. These concepts are especially useful when building real-world applications.
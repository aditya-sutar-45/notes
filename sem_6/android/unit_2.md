# Core Concepts of JavaScript

## `async/await`

### Problems with Callback

1. can lead to callback hell
2. difficult to maintain
3. complex error handling
4. hard to manage multiple async tasks

### Advantages of Promises and async/await

1. cleaner and readable code
2. avoids callback nesting
3. better error handling using try catch
4. easier to manage multiple async tasks
5. makse sync code look like async

| Callbacks                             | Promises / async-await          |
| ------------------------------------- | ------------------------------- |
| callback functions                    | Promise objects                 |
| leads to callback hell                | Cleaner and flatter code        |
| trash error handling                  | Uses `try-catch`                |
| Harder to read, maintain              | Easier to read and maintain     |
| dont use for complex async operations | use for complex async workflows |

eg callback:

```js
getUser(id, (user) => {
  getPosts(user, (posts) => {
    console.log(posts);
  });
});
```

eg asnyc await

```js
try {
  const user = await getUser(id);
  const posts = await getPosts(user);
} catch (error) {
  console.log(error);
}
```

## Spread Operator and Destructuring

### Spread

- `...`
- used to copy / merge objects
- reduces code complexity
- helps update state without modifying original data

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // 1, 2, 3, 4, 5

const users = { name: "Aditya", age: 20 };
const updatedUser = {
  ...users,
  age: 21,
};
```

### Destructuring

- extracts values from arrays or objects into variables
- improves readabilty

```js
const users = { name: "Aditya", age: 20 };
const { name, age } = users;
```

### React Native examples

```jsx
const [user, setUser] = useState({
  name: "Aditya",
  age: 20,
});

setUser({
  ...user,
  age: 21,
});

const [todos, setTodos] = useState(["Study", "Gym"]);

setTodos([...todos, "Sleep"]);

function UserCard({ name, age }) {
  return (
    <Text>
      {name} - {age}
    </Text>
  );
}
```

## Interfaces and Inheritance in Typescript

### Interface

1. Defines structure of an object
2. specifies properties and methods
3. improves type safety

```ts
interface User {
  name: string;
  age: number;
}

const user: User = {
  name: "Aditya",
  age: 20,
};
```

### Inheritance

- allows one interface to inherit properties from another
- uses `extends` keyword

```ts
interface Person {
  name: string;
}

interface Student extends Person {
  rollNo: number;
}

const student: Student = {
  name: "Aditya",
  rollNo: 101,
};
```

### Interface vs Type

| Interface                           | Type Alias                        |
| ----------------------------------- | --------------------------------- |
| interface keyword                   | type keyword                      |
| Supports inheritance                | Uses intersection for composition |
| Mainly used for object              | represents objects, unions, etc   |
| Can be merged - declaration merging | Cannot be merged                  |

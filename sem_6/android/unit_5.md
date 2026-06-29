# Optimizing App Performance

## MMKV and Chaching Libraries improving network performance

- store frequently used data locally
- reduce number of API calls
- Data can be shown instantly
- fresh data loads from the background
- saves internet
- improves battery
- partially / full offline
- _MMKV_ → fast key value storage
- check cache → if not found → fetch from network → save to cache

## MMKV - Memory mapped key value

- high performance key value storage
- developed by Tencent
- stores data locally

### How MMKV improves performance

- stores API responses and app data locally
- data can be loaded from local storage
- uses memory mapping → file storage is directly mapped into RAM
- fetch previously fetched data without internet
- improves startup times and loading speed

## Unit Test vs Component Integration Test

| Unit Test                     | Component Integration Test           |
| ----------------------------- | ------------------------------------ |
| single function / module      | multiple components together         |
| checks logic in isolation     | checks interaction between comp      |
| fast and simple               | more complex and slower              |
| does not involve UI           | includes user actions                |
| finds errors in units of code | finds error in components            |
| eg: testing utility function  | eg: testing if clicking button works |

TLDR →
**Unit Test** : one small piece of code independantly
**Component Integration** : multiple connected components

## FlatList in React Native

- component used to efficiently render large lists of data
- uses virtualization → only items visible on screen are rendered
- off screen items removed
- reduces memory uses
- improves scroll performance

```jsx
import { FlatList, Text } from "react-native";

const data = [
  { id: "1", name: "Apple" },
  { id: "2", name: "Banana" },
  { id: "3", name: "Orange" },
];

<FlatList
  data={data}
  keyExtractor={(item) => item.id}
  renderItem={({ item }) => <Text>{item.name}</Text>}
/>;
```

### FlatList config options for performance

1. `initalNumToRender` → how many items are rendered initially
2. `maxToRenderPerBathch` → number of items rendered in on batch
3. `windowSize` → how many screens worth of items are kept in memory
4. `removeClippedSubviews` → removes items outside the visible screen
5. `getItemLayout` → provides item hieght/width in advanced
6. `keyExtractor` → provides unique keys for items

## useMemo and useCallback

### useMemo

- memoizes a computed value
- prevents expensive calculation from running again and again
- returns a value

```jsx
const result = useMemo(() => expensiveCalc(data), [data]);
```

### useCallback

- memoizes a function
- prevents function recreation on every render
- returns a function
- used for optimizing callbacks passed to child components

```jsx
const handleClick = useCallback(() => {
  console.log("Clicked");
}, []);
```

## Overusing useMemo and useCallback can reduce performance

- when computation being memoized is simple
- memoizing rarely used stuff
- each memoized value needs additional space / memory
- react compares dependency arrays on every render, adding overhead
- overuse adds complexity and makes code harder to maintain
- useCallback fo revery function can increase memory usage

## AsyncStorage vs MMKV

| AsyncStorage                   | MMKV                           |
| ------------------------------ | ------------------------------ |
| uses async storage operations  | uses sync storage operations   |
| slower for large data          | faster due to memory mapping   |
| serialized format              | mapped files for direct access |
| simple storage needs           | high performance caching       |
| delays in frequent reaad/write | near instant read/write        |
| community maintained           | developed by tencent           |

## Flipper and React Dev Tools

### Frame drops

- occur when app fails to maintain 60fps
- causes laggy animation

### Flipper

- monitors app performance in real time
- uses the performance plugin to track FPS
- helps identify slow renders and bottlenecks
- shows CPU and memory usage
- helps detect unnecessary re-renders

### React Dev Tools

- uses the profiler tab to analyze component rendering
- identifies components that re render too frequently
- measure render time
- helps find expensive components

### How they help isolate frame drops

1. use flipper → FPS drops
2. use dev tools profiler → components
3. optimize

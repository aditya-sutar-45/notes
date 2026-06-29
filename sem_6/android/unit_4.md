# Mobile UI/UX Design (React Native)

## Flexbox alignment properties

### justifyContent

- alignment along the main axis (vertical)
- positions items top, center, bottom, with spacing

Common values

1. `flex-start` → start of container
2. `center` → center
3. `flex-end` → end of contianer
4. `space-between` → equal space between
5. `space-aroudn` → equal space around

### alignItems

- alignment along the cross axis (horizontal)
- positions items left, center, right, stretch

Common values

1. `flex-start` → left
2. `center` → center
3. `flex-end` → right
4. `stretch` → fill available width

```jsx
<View
  style={{
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  }}
>
  <Text>Hello</Text>
</View>
```

## Cross Platform layouts

- resolving design conflicts between material design and human interface guidelines
- should follow
  - material design → android
  - human interface guidelines → IOS
- maintain consistent brand identity
- platform specific components when necessary
- conditional rendering using `Platform.OS`

## Material Design vs Human Interface Guidelines

| Material Design                      | Human Interface Guidelines    |
| ------------------------------------ | ----------------------------- |
| google                               | apple                         |
| android                              | ios                           |
| bold colors                          | simple clean minimal          |
| emphasizes cards, shadows, elevation | emphasizes clarity, depth     |
| uses Floating action buttons         | avoid Floating action buttons |

## Layout strategies for scalable React Native UI

- flexbox
- avoid fixed widths
- relative dimensions (percentage based)
- use `Dimensions` API → gives screen height, width
- use `useWindowDimensions()` to adapt layout
- responsive sizing and spacing
- support both landscape and portrait
- conditional layouts for phone, tablets, foldables
- FlatList instead of ScrollView
- Test UI and diff screens

## Native Driver in React Native

- runs animations on native UI thread instead of JS thread
- enabled using:

  ```jsx
  useNativeDriver: true;
  ```

### How does it optimize animations?

- moves animations: JS thread → native thread
- reduces communication over React Native Bridge
- animations continue even when JS thread is busy
- decreases lag and stuttering

### Why is it needed for 60FPS?

- smooth UI
- each frame has 16.67 ms to render
- JS thread is busy with API calls → can cause lags

| Native Driver             | JS Animations             |
| ------------------------- | ------------------------- |
| Runs on native UI thread  | Runs on JS thread         |
| Independent of JS thread  | Depends on JS thread      |
| Less bridge communication | More bridge communication |
| Smoother animations       | Can become laggy          |
| Better 60 FPS support     | More frame drops          |

## Accessibilty in React Native for TalkBack / VoiceOver

- TalkBack → Screen reader used for android
- VoiceOver → Screen reader for IOS
- gives audio feedback

### Accessibilty options

1. `accessible={true}` make component accessible
2. `accessibiltyLabel` provide description for screen readers
3. `accessbiltyHint` to explain what the action does
4. `accessibiltyRole` to specific the element type
5. `accessibilityState` to indicate states (disabled / selected)

eg:

```jsx
<Button
  title="Login"
  accessible={true}
  accessibilityLabel="Login Button"
  accessibilityHint="Logs into your account"
  accessibilityRole="button"
/>
```

## FlatList vs ScrollView

| ScrollView                     | FlatList                      |
| ------------------------------ | ----------------------------- |
| Renders all items at once.     | Renders only visible items.   |
| Higher memory usage.           | Lower memory usage.           |
| Slower for large datasets.     | Optimized for large datasets. |
| No virtualization support.     | Uses virtualization.          |
| Suitable for small lists.      | Suitable for large lists.     |
| Can cause lag with many items. | Provides smooth scrolling.    |

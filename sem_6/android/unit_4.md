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

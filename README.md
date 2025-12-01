# SwipeUp Lib React-Native

SwipeUp Lib is a React Native library that provides an easy and flexible solution for adding swipe-up gestures to your mobile applications. With this library, developers can quickly implement the swipe-up functionality to trigger actions, reveal menus, or display additional information, enhancing the user experience.

## Installation

```bash
# Using npm
npm install swipeup-lib-react-native

# Using Yarn
yarn add swipeup-lib-react-native
```

## Configuration

### 1. Tailwind CSS Setup

To apply the styles from this library, update your `tailwind.config.js` to include the library's path in the `content` array:

```js
module.exports = {
  content: [
    "./App.{js,jsx,ts,tsx}",
    "./src/**/*.{js,jsx,ts,tsx}",
    // Add this line to include the library files
    "./node_modules/swipeup-lib-react-native/lib/**/*.{js,jsx,ts,tsx}"
  ],
  // ...
}
```

### 2. Babel Configuration

Ensure your `babel.config.js` includes the necessary plugins for `nativewind` and `react-native-reanimated`. If you haven't configured them yet, update your `babel.config.js`:

```js
module.exports = function (api) {
  api.cache(true);
  return {
    presets: ["babel-preset-expo"],
    plugins: ["nativewind/babel", "react-native-reanimated/plugin"],
  };
};
```

### 3. Gesture Handler

Wrap your root component (e.g., inside `App.tsx` or `App.js`) with `GestureHandlerRootView` from `react-native-gesture-handler`:

```jsx
import { GestureHandlerRootView } from 'react-native-gesture-handler';

export default function App() {
  return (
    <GestureHandlerRootView style={{ flex: 1 }}>
      {/* Your app code */}
    </GestureHandlerRootView>
  );
}
```

## Features

- Customizable with Tailwind CSS

## Usage/Examples

```javascript
import { Text, TouchableOpacity, View } from "react-native";
import { SwipeUp } from "swipeup-lib-react-native";
import { Card } from "../card"; // Adjust import based on your project structure

export default function Example() {
    return (
        <View className="flex-1 p-4 bg-purple-500">
            <TouchableOpacity className="w-48 h-48 bg-emerald-500"/>
            {/* <!-- This is an example of a swipeable card component --> */}
            <SwipeUp
                borderColor="bg-white"
                backgroundColor="bg-black"
                touchIconColor="bg-black"
            >
                <Text className="text-white font-semibold text-center my-2 text-2xl">
                    example
                </Text>
                {/* Example children */}
                <View className="bg-red-500 p-4 m-2"><Text>Item 1</Text></View>
                <View className="bg-sky-500 p-4 m-2"><Text>Item 2</Text></View>
            </SwipeUp>
        </View>
    );
}
```


## Demo

![Texto Alternativo](./assets/example.gif)


## Improvements

If you have made any improvements to the code, such as refactoring, performance enhancements, accessibility improvements, etc., please create an issue to discuss them.


## Support

For support, please send an email to brunogomesdsilva7@gmail.com.

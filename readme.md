# React Native Animated Loader Typescript
 

## Prerequisites
### Using React Native CLI
This library uses [lottie-react-native](https://github.com/react-native-community/lottie-react-native) to render loader animations. Therefore this library need to be installed and linked to your project before installing this package.

Follow the official instruction and linking guide [here](https://github.com/react-native-community/lottie-react-native/blob/master/README.md#getting-started).

### Using Expo
No need to do anything specific, just install the package itself. Expo already has Lottie library API available and it will take care of the rest.

## Install

```
yarn add https://github.com/kayode001/react-native-animated-loader-typscript.git
```
or
```
npm install https://github.com/kayode001/react-native-animated-loader-typscript.git --save
```

## Usage

```jsx
import React from 'react';
import { StyleSheet } from 'react-native';
import AnimatedLoader from "react-native-animated-loader";

export default class Loader extends React.Component {
  constructor(props) {
    super(props);
    this.state = { visible: false };
  }

  componentDidMount() {
    setInterval(() => {
      this.setState({
        visible: !this.state.visible
      });
    }, 2000);
  }

  render() {
    const { visible } = this.state;
    return (
      <AnimatedLoader
        visible={visible}
        overlayColor="rgba(255,255,255,0.75)"
        source={require("./loader.json")}
        animationStyle={styles.lottie}
        speed={1}
      >
        <Text>Doing something...</Text>
      </AnimatedLoader>
    );
  }
}

const styles = StyleSheet.create({
  lottie: {
    width: 100,
    height: 100
  }
});
```

### Loader files

You can find free lottie files for your loaders [here](https://lottiefiles.com/search?q=loader).

## Props

| Prop | Description | Default |
|---|---|---|
|**`source`**| The source of animation. Can be referenced as a local asset by a string, or remotely with an object with a `uri` property, or it can be an actual JS object of an animation, obtained (for example) with something like `require('../path/to/animation.json')`. | [Lottie Object](https://lottiefiles.com/1531-loader) |
|**`visible`**| Controls the visibility of the loader. | `false` |
|**`overlayColor`**| Changes the color of the overlay. | `rgba(255,255,255,0.75)` |
|**`animationStyle`**| The style to be applied to the Lottie. | - |
|**`animationType`**| Changes animation on show and hide loader's view. | `none` |
|**`speed`**| The speed the animation will progress. | `1` |
|**`loop`**| A boolean flag indicating whether or not the animation should loop. | `true` |


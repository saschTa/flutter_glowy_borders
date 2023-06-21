This package provides a wrapper widget to animate borders around your widgets.
You can choose to provide current Animation Progress externally or use an indefinitely animation.

<img src="https://raw.githubusercontent.com/saschTa/flutter_glowy_borders/main/example/assets/animated_border.gif" width="200"/> | <img src="https://raw.githubusercontent.com/saschTa/flutter_glowy_borders/main/example/assets/animated_border_circle.gif" width="200"/> | <img src="https://raw.githubusercontent.com/saschTa/flutter_glowy_borders/main/example/assets/animated_border_percentage.gif" width="200"/>

## Features

### AnimatedGradientBorder Widget

- Wrapper to Animate widgets border with gradients and glow
- Set animation progress manually or loop indefinitely
- control size of glow, border and colors to achieve stunning effects

## Getting started

Create your flutter app, import this package and use AnimatedGradientBorder to wrap some element.

## Usage

In this example you only need to wrap the widget with a full size Column in your app to see the
results.
Also note the `currentProgress` variable which is used to set animation state.
If you remove it or set it to `null`, the animation will play indefinitely.

`Please Note that you will need to set the same border radius for the wrapper as well as the child to
make it look like a true border.`

```dart

const widget = AnimatedGradientBorder(
  borderSize: 1,
  glowSize: 60,
  gradientColors: [Colors.black, Colors.black, Colors.black, Colors.purple.shade50],
  animationProgress: currentProgress,
  borderRadius: BorderRadius.all(Radius.circular(2)),
  child: Container(
    width: 300,
    height: 300,
    decoration: BoxDecoration(
        borderRadius: BorderRadius.all(Radius.circular(2)),
        color: Theme
            .of(context)
            .colorScheme
            .secondaryContainer),
    child: Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text("current value: $currentProgress",
            style: TextStyle(color: Colors.white, fontSize: 30.0)),
      ],
    ),
  ),
);
```

## Additional information

This feature uses Backdrop Filter under the hood which can cause performance issues if used
extensively. Keep that in mind.

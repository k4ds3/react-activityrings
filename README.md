# react-activity-rings
**Apple-inspired Activity Rings for React.**  

[![npm bundle size (scoped)](https://img.shields.io/bundlephobia/minzip/@jonasdoesthings/react-activity-rings?color=%2384cc16&style=flat-square)](https://bundlephobia.com/package/@jonasdoesthings/react-activity-rings)
[![LICENSE](https://img.shields.io/npm/l/@jonasdoesthings/react-activity-rings?color=%2384cc16&style=flat-square)](./LICENSE)
[![npm version](https://img.shields.io/npm/v/@jonasdoesthings/react-activity-rings?color=84cc16&style=flat-square)](https://www.npmjs.com/package/@jonasdoesthings/react-activity-rings/)


![demo banner gif](.assets/activityrings_banner.gif)

Support my Open Source work:  
<a href="https://www.buymeacoffee.com/JonasDoesThings" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

## Installation
using npm:  
`npm install @jonasdoesthings/react-activity-rings`  
using yarn:  
`yarn add @jonasdoesthings/react-activity-rings`
## Examples
Storybook Demo: https://jonasdoesthings.github.io/react-activity-rings/

```tsx
import {ActivityRings} from "@jonasdoesthings/react-activity-rings";

// Basic example with no custom settings
<ActivityRings rings={[
  {filledPercentage: 0.5, color: '#fa0e5a'},
  {filledPercentage: 0.75, color: '#afff02'},
  {filledPercentage: 0.25, color: '#00fff8'},
]} />
```
```tsx
// Example with custom settings
<ActivityRings 
  rings={[
    {filledPercentage: 0.1, color: 'rgb(255, 0, 0)'},
    {filledPercentage: 1, color: '#FF0000'},
    {filledPercentage: 0.5, color: '#00fff8'},
  ]} 
  options={{
    initialRadius: 20,
    animationDurationMillis: 1500,
    containerHeight: '10vh',
  }} 
/>
```

More usage-examples can be found under [./src/components/ActivityRings.stories.tsx](./src/components/ActivityRings.stories.tsx).

## API
### ActivityRings
| Property | Type                         | Required | Description                                          |
|----------|------------------------------|----------|------------------------------------------------------|
| rings    | ActivityRing[]               | yes      | An array of ActivityRing objects containing the data |
| options  | ActivityRingContainerOptions | no       | An object containing general settings                |

### ActivityRing
| Property         | Type   | Required | Description                                                                                                                                                               |
|------------------|--------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| filledPercentage | number | yes      | A float between 0 and 1 representing the progress in percent                                                                                                              |
| color            | string | yes      | A [css-compatible color string](https://developer.mozilla.org/en-US/docs/Web/CSS/color) i.e. `#FF00FF` or `rgb(0, 255, 0)`                                                |
| backgroundColor  | string | no       | A [css-compatible color string](https://developer.mozilla.org/en-US/docs/Web/CSS/color) i.e. `#FF00FF` or `rgb(0, 255, 0)`. If not defined, the foreground color is used. |
| ringWidth        | number | no       | A number in svg viewport-relative pixels specifying the stroke-width of the ring, if not defined, defaults to 12                                                          |

### ActivityRingContainerOptions
| Property                | Type   | Default     | Description                                                                                                              |
|-------------------------|--------|-------------|--------------------------------------------------------------------------------------------------------------------------|
| containerHeight         | string | 100%        | A [css-compatible height value](https://developer.mozilla.org/en-US/docs/Web/CSS/height) of the container                |
| containerWidth          | string | 100%        | A [css-compatible width value](https://developer.mozilla.org/en-US/docs/Web/CSS/width) of the container                  |
| paddingBetweenRings     | number | 0.75        | The padding between each of the rings                                                                                    |
| initialRadius           | number | 30          | The radius of the innermost ring                                                                                         |
| animationDurationMillis | number | 1000        | The duration of the initial animation in milliseconds (0=no animation)                                                   |
| animationTimingFunction | string | ease-in-out | A [css-compatible animation timing function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function) |
| backgroundOpacity       | number | 0.4         | A float between 0 and 1 representing the opacity of the background-ring color in percent                                 |

(All fields are optional)

## Notes 

### React Native
This project currently does not work with react native when targeting other platforms than web, due to react native not supporting the used `<svg>` component and its descendents.
If you want to tackle this issue, feel free to fork this project and replace the web svg-component with a react-native supported one.  
More Details regarding RN support [can be found in this Issue](https://github.com/JonasDoesThings/react-activity-rings/issues/1)

## License
The project is licensed under the MIT license.    
Check the [LICENSE](./LICENSE) file, for the full legal-notice.

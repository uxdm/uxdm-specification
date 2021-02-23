# Design Editor

## Frame

Same as Art Board in Sketch or frame in Figma.

### Types

- Basic frame.
- Asset, includes illustrations and icons, etc.

## RTL & Dark mode & L10n

All the design elements have native support of these. Could provide variations of assets and overrides of components and frames.

## Layout & Platform

- Design is not targeting any specific platform but provides **component level platform variants**.
- Use **Flex** as the core layout concept.
- Provides List and Collection View, similar to what we see in Framer X. But also provide empty and error states for maximum flexibility.

## Text Rendering

Text blocks do not store actual string value; they keep a reference to the data field or localization term key. During the preview, it fills text blocks with localized strings and data values.

## Variations

All the frames, assets, colors, fonts, and components can have multiple variants. So we can support the right to left layout and dark mode.

### Colors

We can manage colors with multiple Palette Groups. So it was color ID stored in the design document, not the color value. During the preview, viewers can switch between Palette Groups to get a sense of different color combinations.

## Version Control

### Excluded

- Frame position and Frame size in most cases
- All text values. Use connected localization resources or API request results.
- All images. Use connect cloud assets, specialized **Asset Frame** or API results.

## Preview

We can toggle nodes map with a shortcut. When you press the key, a connection overlay will show up on top. Click on the connection or slot will show the related frame or state.

## Prototyping

We do not plan to provide any prototyping tools. The product manager should do this using Nodes Map Editor. What designers should do is mapping the necessary nodes and slots.

## Layout Unit

You can set a layout unit and apply it to view dimensions or margins/paddings (recommended).

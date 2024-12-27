<div align="center">

Link in bio to **widgets**,
your online **home screen**. ➫ [🔗 kee.so](https://kee.so/)

</div>

---

# sryd-img-crop

## Install

```sh
pnpm add sryd-img-crop
# or
yarn add sryd-img-crop
# or
npm i sryd-img-crop
```

## Usage

```jsx harmony
import { Upload } from 'sryd';
import ImgCrop from 'sryd-img-crop';

const Demo = () => (
  <ImgCrop>
    <Upload>+ Add image</Upload>
  </ImgCrop>
);
```

## Props

| Prop           | Type       | Default        | Description                                                                      |
| -------------- | ---------- | -------------- | -------------------------------------------------------------------------------- |
| quality        | `number`   | `0.4`          | Cropped image quality, `0` to `1`                                                |
| fillColor      | `string`   | `'white'`      | Fill color for cropped image                                                     |
| zoomSlider     | `boolean`  | `true`         | Enable zoom                                                                      |
| rotationSlider | `boolean`  | `false`        | Enable rotation                                                                  |
| aspectSlider   | `boolean`  | `false`        | Enable aspect                                                                    |
| showReset      | `boolean`  | `false`        | Show reset button to reset zoom & rotation & aspect                              |
| resetText      | `string`   | `Reset`        | Reset button text                                                                |
| aspect         | `number`   | `1 / 1`        | Aspect of crop area , `width / height`                                           |
| minZoom        | `number`   | `1`            | Minimum zoom                                                                     |
| maxZoom        | `number`   | `3`            | Maximum zoom                                                                     |
| minAspect      | `number`   | `0.5`          | Minimum aspect                                                                   |
| maxAspect      | `number`   | `2`            | Maximum aspect                                                                   |
| cropShape      | `string`   | `'rect'`       | Shape of crop area, `'rect'` or `'round'`                                        |
| showGrid       | `boolean`  | `false`        | Show grid of crop area (third-lines)                                             |
| cropperProps   | `object`   | -              | [react-easy-crop] props (\* existing props cannot be overridden)                 |
| modalClassName | `string`   | `''`           | Modal classname                                                                  |
| modalTitle     | `string`   | `'Edit image'` | Modal title                                                                      |
| modalWidth     | `number`   | `string`       | Modal width                                                                      |
| modalOk        | `string`   |                | Ok button text                                                                   |
| modalCancel    | `string`   |                | Cancel button text                                                               |
| onModalOk      | `function` | -              | Callback of click ok button                                                      |
| onModalCancel  | `function` | -              | Callback of click cancel button (or modal mask & top right "x")                  |
| modalProps     | `object`   |                | [Ant Design Modal] props (\* existing props cannot be overridden)                |
| beforeCrop     | `function` | -              | Callback before crop modal, if return `false` or `reject()`, modal will not open |

## FAQ

### `ConfigProvider` not work?

Try to set `libraryDirectory`(`'es'` or `'lib'`) to `babel-plugin-import` config, see which one will work.

```js
module.exports = {
  plugins: [
    ['import', { libraryName: 'sryd', libraryDirectory: 'es', style: true }],
  ],
};
```

### No style? (only `sryd<=v4`)

If you use `sryd<=v4` + `babel-plugin-import`, and no `Modal` or `Slider` were imported, please import these styles manually:

```js
import 'sryd/es/modal/style';
import 'sryd/es/slider/style';
```
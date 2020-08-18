# flutter_map_location_marker

A [flutter_map](https://pub.dev/packages/flutter_map) plugin for displaying device current location.
![Interface preview](https://github.com/tlserver/flutter_map_location_marker/raw/master/assets/interface.jpg)

## Features

* **Customization**: The location marker can be fully customized. The colors of accuracy circle and
header are also customizable.

* **Simple**: Not depend on other layer. No `MapController` or `MarkerLayer` are needed.

## Usage

Add flutter_map_location_marker to your pubspec.yaml:
 
```yaml
dependencies:
  flutter_map_location_marker: any // or latest verion
```

Add the plugin and the layer option into `FlutterMap`:

```dart
Widget build(BuildContext context) {
  return FlutterMap(
    options: MapOptions(
      plugins: [
        LocationMarkerPlugin(), // <-- add plugin here
      ],
    ),
    layers: [
      TileLayerOptions(
        urlTemplate: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
        subdomains: ['a', 'b', 'c'],
        maxZoom: 19,
      ),
      LocationMarkerLayerOptions(), // <-- add layer options here
    ],
  );
}
```

## Examples

1. [Marker Customization](./example/lib/page/customize_marker_example.dart)  
Change the marker to any widget you want.

2. [Floating Action Button for Centering Current Location](./example/lib/page/center_fab_example.dart)  
Use a floating action button to move and zoom the map to current location.

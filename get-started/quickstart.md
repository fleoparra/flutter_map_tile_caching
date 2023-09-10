# Quickstart

{% hint style="warning" %}
**FMTC is licensed under GPL-v3.**

If you're developing a proprietary (non open-source) application, this affects you and your application's legal right to distribution. For more information, please see [#proprietary-licensing](../#proprietary-licensing "mention").
{% endhint %}

This page guides you through a simple, fast setup of FMTC that just enables basic browse caching, without any of the bells and whistles that you can discover throughout the rest of this documentation.

## 1. [Install](installation.md)

Depend on the latest version of the package from pub.dev, then import it into the appropriate files of your project.

{% code title="Console/Terminal" %}
```sh
flutter pub add flutter_map_tile_caching
```
{% endcode %}

```dart
import 'package:flutter_map_tile_caching/flutter_map_tile_caching.dart';
```

## 2. [Initialise](../usage/initialisation.md)

Perform the startup procedure to allow usage of FMTC's APIs and connect to the underlying systems.

<pre class="language-dart" data-title="main.dart"><code class="lang-dart">import 'package:flutter/widgets.dart';
import 'package:flutter_map_tile_caching/flutter_map_tile_caching.dart';

Future&#x3C;void> main() async {
    WidgetsFlutterBinding.ensureInitialized();   
<strong>    await FlutterMapTileCaching.initialise();
</strong>    // ...
    // runApp(MyApp());
}
</code></pre>

## 3. [Create a store](../usage/roots-and-stores/#without-automatic-creation)

Create an isolated space to store tiles and other information to be accessed by the map and other methods.

<pre class="language-dart" data-title="main.dart"><code class="lang-dart">Future&#x3C;void> main() async {
    WidgetsFlutterBinding.ensureInitialized();   
    await FlutterMapTileCaching.initialise();
<strong>    await FMTC.instance('mapStore').manage.createAsync();
</strong>    // ...
    // runApp(MyApp());
}
</code></pre>

## 4. [Connect to 'flutter\_map'](../usage/integration.md)

Enable your `FlutterMap` widget to use the caching and underlying systems of FMTC.

<pre class="language-dart"><code class="lang-dart">import 'package:flutter_map/flutter_map.dart';

TileLayer(
    urlTemplate: 'https://tile.openstreetmap.org/{z}/{x}/{y}.png',
    userAgentPackageName: 'com.example.app',
<strong>    tileProvider: FMTC.instance('mapStore').getTileProvider(),
</strong>    // Other parameters as normal
),
</code></pre>

## 5. Wow! Look at that caching...

{% hint style="success" %}
You should now have a basic working implementation of FMTC that caches tiles for you as you browse the map!

There's a lot more to discover, from store management to bulk downloading, and from statistics to exporting/importing.
{% endhint %}

{% hint style="warning" %}
Before using FMTC, especially to bulk download, ensure you comply with the appropriate restrictions and terms of service set by your tile server. Failure to do so may lead to any punishment, at the tile server's discretion.

This library and/or the creator(s) are not responsible for any violations you make using this package.

***

Some common tile servers' ToS are listed below:

* [OpenStreetMap](https://operations.osmfoundation.org/policies/tiles)
* [Mapbox](https://www.mapbox.com/legal/tos)
* [Thunderforest](https://www.thunderforest.com/terms/)
* [Stadia Maps](https://stadiamaps.com/terms-of-service/)

For testing purposes, check out the testing tile server included in the FMTC project: [#testing-your-application](../bulk-downloading/introduction.md#testing-your-application "mention").
{% endhint %}
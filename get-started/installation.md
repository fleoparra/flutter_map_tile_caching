# Installation

{% hint style="warning" %}
**FMTC is licensed under GPL-v3.**

If you're developing a proprietary (non open-source) application, this affects you and your application's legal right to distribution. For more information, please see [#proprietary-licensing](../#proprietary-licensing "mention").
{% endhint %}

{% hint style="success" %}
Looking to start using FMTC in your project? Check out the [quickstart.md](quickstart.md "mention") guide!
{% endhint %}

## Depend On

### From [pub.dev](https://pub.dev/packages/flutter\_map\_tile\_caching)

This is the recommended method of installing this package as it ensures you only receive the latest stable versions, and you can be sure pub.dev is reliable.

Just import the package as you would normally, from the command line:

<pre class="language-shell"><code class="lang-shell"><strong>flutter pub add flutter_map_tile_caching
</strong>flutter pub add fmtc_plus_background_downloading # OPTIONAL
flutter pub add fmtc_plus_sharing # OPTIONAL
</code></pre>

### From [github.com](https://github.com/JaffaKetchup/flutter\_map\_tile\_caching)

If you urgently need the latest version, a specific branch, or a specific fork, you can use this method.

{% hint style="info" %}
Commits available from Git (GitHub) may not be stable. Only use this method if you have no other choice.
{% endhint %}

Add the following lines to your pubspec.yaml file under the 'dependencies\_override' section:

<pre class="language-yaml" data-title="pubspec.yaml"><code class="lang-yaml">dependency_overrides:
<strong>    flutter_map_tile_caching:
</strong><strong>        git:
</strong><strong>            url: https://github.com/JaffaKetchup/flutter_map_tile_caching.git
</strong>    fmtc_plus_background_downloading: # OPTIONAL
        git:
            url: https://github.com/JaffaKetchup/fmtc_plus_background_downloading.git
    fmtc_plus_sharing: # OPTIONAL
        git:
            url: https://github.com/JaffaKetchup/fmtc_plus_sharing.git
</code></pre>

## Import

After installing the package, import it into the necessary files in your project:

<pre class="language-dart"><code class="lang-dart"><strong>import 'package:flutter_map_tile_caching/flutter_map_tile_caching.dart';
</strong>import 'package:fmtc_plus_background_downloading/fmtc_plus_background_downloading.dart'; // OPTIONAL
import 'package:fmtc_plus_sharing/fmtc_plus_sharing.dart'; // OPTIONAL
</code></pre>
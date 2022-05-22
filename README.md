# natural-earth-tiles

Natural Earthのベクタータイル

# 作成手順

```sh
% git clone https://github.com/mapbox/mbutil.git
% cd mbutil
% wget https://github.com/lukasmartinelli/naturalearthtiles/releases/download/v1.0/natural_earth.vector.mbtiles
% ./mb-util --image_format pbf ./natural_earth.vector.mbtiles tiles
% mkdir /tmp/sandbox
% mv -i tiles /tmp/sandbox/tiles
% cd /tmp/sandbox
% gzip -d -r -S .pbf *
% find . -type f -exec mv '{}' '{}'.pbf \;
% mv tiles/metadata.json.pbf tiles/metadata.json
  // これでtilesがunzipなベクタータイル
```

# 参考

- https://github.com/klokantech/naturalearthtiles
- https://github.com/lukasmartinelli/naturalearthtiles/releases/tag/v1.0
- http://naturalearthtiles.lukasmartinelli.ch/maps/natural_earth.vector.html
- https://github.com/lukasmartinelli/naturalearthtiles/blob/gh-pages/maps/natural_earth.vector.json
- https://gis.stackexchange.com/questions/210188/unzipping-osm2vectortiles-after-extracing-with-mbutil

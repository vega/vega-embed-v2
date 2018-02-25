# Vega-Embed v2

[Vega-Embed](https://github.com/vega/vega-embed) for Vega 2 and Vega-Lite 1

## Usage
If in HTML.
```html
<div id="vis"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.js" charset="utf-8"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/vega/2.6.5/vega.js" charset="utf-8"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/vega-lite/1.3.1/vega-lite.js" charset="utf-8"></script>
<!-- Import the vega-lite -->
<script src="vega-embed-v2.js" charset="utf-8"></script>

<script type="text/javascript">
  var spec = {...}, // vega 2 or vega-lite 1 spec
  embedSpec = {
    mode: "vega-lite",
    spec: spec
    }
    vegaEmbed("#vis", embedSpec, function(error, result) {
        console.log(result);
  }).catch(console.error);
</script>
</body>
</html>
```

## Development
```sh
git clone https://github.com/vega/vega-embed-v2
cd vega-embed-v2
npm run dep
npm run build
```
This will generate `vega-embed-v2.js`. Run a local webserver (e.g., `python -m SimpleHTTPServer 8000`) in the Vega-Embed folder and then point your web browser at the test page (e.g., http://localhost:8000/test-vl.html).

Note that since `vega-embed-v2` depends on `vega-embed`, to correctly `browserify`, it seems we need to have devdep for `vega-embed` installed, hence `npm install` cannot work. The current work around is `npm run dep`. See `scripts` in `package.json` for details.
```js
import * as d3 from "npm:d3";
```

```js
const geojson = await FileAttachment("data/output.geojson").json();
console.log(geojson);

const projection = d3.geoConicConformal()
               .parallels([12.472944, 35.172806]);
               /*
               .rotate([-80, 0])
               .scale(1000);
               .translate([width / 2, height / 2]);*/

Plot.plot({
    projection: projection,
    marks : [
        Plot.geo(geojson, {
            title: (d) => `${d.STATE} ${d.District}`,
            tip: true
        })
    ]
});
```

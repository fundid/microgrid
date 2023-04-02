<script>
    import "@carbon/styles/css/styles.css";
    import "@carbon/charts/styles.css";
    import { BarChartSimple, BarChartGrouped, ComboChart, DonutChart, PieChart } from "@carbon/charts-svelte";
  </script>
  
  <BarChartSimple
    data={[
      { group: "Qty", value: 65000 },
      { group: "More", value: 29123 },
      { group: "Sold", value: 35213 },
      { group: "Restocking", value: 51213 },
      { group: "Misc", value: 16932 },
    ]}
    options={{
      title: "Simple bar (discrete)",
      height: "400px",
      axes: {
        left: { mapsTo: "value" },
        bottom: { mapsTo: "group", scaleType: "labels" },
      },
    }}
  />

  <p></p>
 <p></p>
  
 <BarChartSimple
	data={[
	{
		"group": "Qty",
		"value": 65000
	},
	{
		"group": "More",
		"value": 29123
	},
	{
		"group": "Sold",
		"value": 35213
	},
	{
		"group": "Restocking",
		"value": 51213
	},
	{
		"group": "Misc",
		"value": 16932
	}
]}
	options={{
	"title": "Horizontal simple bar (discrete)",
	"axes": {
		"left": {
			"mapsTo": "group",
			"scaleType": "labels"
		},
		"bottom": {
			"mapsTo": "value"
		}
	},
	"height": "400px"
}}
	/>

    <p>

    </p>
    <p>

    </p>

    <BarChartGrouped
	data={[
	{
		"group": "Dataset 1",
		"date": "2018-12-31T21:00:00.000Z",
		"value": 10000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-01T21:00:00.000Z",
		"value": 65000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-02T21:00:00.000Z",
		"value": 30000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-05T21:00:00.000Z",
		"value": 49213
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-06T21:00:00.000Z",
		"value": 51213
	},
	{
		"group": "Dataset 2",
		"date": "2018-12-31T21:00:00.000Z",
		"value": 8000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-01T21:00:00.000Z",
		"value": 67000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-02T21:00:00.000Z",
		"value": 15000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-05T21:00:00.000Z",
		"value": 51213
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-06T21:00:00.000Z",
		"value": 45213
	}
]}
	options={{
	"title": "Vertical grouped bar (time series)",
	"axes": {
		"left": {
			"mapsTo": "value"
		},
		"bottom": {
			"mapsTo": "date",
			"scaleType": "time"
		}
	},
	"height": "400px"
}}
	/>

    <p></p>
    <p></p>

    <BarChartGrouped
	data={[
	{
		"group": "Dataset 1",
		"date": "2018-12-31T21:00:00.000Z",
		"value": 10000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-01T21:00:00.000Z",
		"value": 65000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-02T21:00:00.000Z",
		"value": 30000
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-05T21:00:00.000Z",
		"value": 49213
	},
	{
		"group": "Dataset 1",
		"date": "2019-01-06T21:00:00.000Z",
		"value": 51213
	},
	{
		"group": "Dataset 2",
		"date": "2018-12-31T21:00:00.000Z",
		"value": 8000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-01T21:00:00.000Z",
		"value": 67000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-02T21:00:00.000Z",
		"value": 15000
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-05T21:00:00.000Z",
		"value": 51213
	},
	{
		"group": "Dataset 2",
		"date": "2019-01-06T21:00:00.000Z",
		"value": 45213
	}
]}
	options={{
	"title": "Horizontal grouped bar (time series)",
	"axes": {
		"left": {
			"mapsTo": "date",
			"scaleType": "time"
		},
		"bottom": {
			"mapsTo": "value"
		}
	},
	"height": "400px"
}}
	/>

    <p></p>
    <p></p>

    <ComboChart
	data={[
	{
		"group": "School A",
		"date": "Monday",
		"value": 10000
	},
	{
		"group": "School A",
		"date": "Tuesday",
		"value": 65000
	},
	{
		"group": "School A",
		"date": "Wednesday",
		"value": 30000
	},
	{
		"group": "School A",
		"date": "Thursday",
		"value": 49213
	},
	{
		"group": "School A",
		"date": "Friday",
		"value": 49213
	},
	{
		"group": "Temperature",
		"date": "Monday",
		"temp": 70
	},
	{
		"group": "Temperature",
		"date": "Tuesday",
		"temp": 75
	},
	{
		"group": "Temperature",
		"date": "Wednesday",
		"temp": 31
	},
	{
		"group": "Temperature",
		"date": "Thursday",
		"temp": 31
	},
	{
		"group": "Temperature",
		"date": "Friday",
		"temp": 43
	}
]}
	options={{
	"title": "Combo (Line + Simple bar) - custom configs",
	"axes": {
		"left": {
			"mapsTo": "value",
			"scaleType": "linear",
			"title": "USA Summer School Attendance"
		},
		"right": {
			"mapsTo": "temp",
			"scaleType": "linear",
			"title": "Temperature (°F)",
			"correspondingDatasets": [
				"Temperature"
			]
		},
		"bottom": {
			"title": "Day of the Week",
			"mapsTo": "date",
			"scaleType": "labels"
		}
	},
	"comboChartTypes": [
		{
			"type": "simple-bar",
			"correspondingDatasets": [
				"School A"
			]
		},
		{
			"type": "line",
			"options": {
				"points": {
					"radius": 5
				}
			},
			"correspondingDatasets": [
				"Temperature"
			]
		}
	],
	"height": "400px"
}}
	/>

    <p></p>
    <p></p>

    <DonutChart
	data={[
	{
		"group": "2V2N 9KYPM version 1",
		"value": 20000
	},
	{
		"group": "L22I P66EP L22I P66EP L22I P66EP",
		"value": 65000
	},
	{
		"group": "JQAI 2M4L1",
		"value": 75000
	},
	{
		"group": "J9DZ F37AP",
		"value": 1200
	},
	{
		"group": "YEL48 Q6XK YEL48",
		"value": 10000
	},
	{
		"group": "Misc",
		"value": 25000
	}
]}
	options={{
	"title": "Donut (centered)",
	"resizable": true,
	"legend": {
		"alignment": "center"
	},
	"donut": {
		"center": {
			"label": "Browsers"
		},
		"alignment": "center"
	},
	"height": "400px"
}}
	/>
<p></p>
<p></p>

<PieChart
	data={[
	{
		"group": "2V2N 9KYPM version 1",
		"value": 20000
	},
	{
		"group": "L22I P66EP L22I P66EP L22I P66EP",
		"value": 65000
	},
	{
		"group": "JQAI 2M4L1",
		"value": 75000
	},
	{
		"group": "J9DZ F37AP",
		"value": 1200
	},
	{
		"group": "YEL48 Q6XK YEL48",
		"value": 10000
	},
	{
		"group": "Misc",
		"value": 25000
	}
]}
	options={{
	"title": "Pie (centered)",
	"resizable": true,
	"legend": {
		"alignment": "center"
	},
	"pie": {
		"alignment": "center"
	},
	"height": "400px"
}}
	/>

    <p></p>
    <p></p>

    <PieChart
	data={[]}
	options={{
	"title": "Pie (skeleton)",
	"resizable": true,
	"data": {
		"loading": true
	},
	"height": "400px"
}}
	/>
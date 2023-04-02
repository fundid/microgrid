<script>
    import { Accordion, AccordionItem, DataTable } from "carbon-components-svelte";
    import { ComboChart } from "@carbon/charts-svelte";
        
            import "@carbon/styles/css/styles.css";
            import "@carbon/charts/styles.css";
  </script>
  
  <Accordion size="xl">
    <AccordionItem title="Weekly Overview">
      <p>        
        <ComboChart
            data={[
            {
                "group": "2023",
                "day": "Monday",
                "value": 53
            },
            {
                "group": "2023",
                "day": "Tuesday",
                "value": 238
            },
            {
                "group": "2023",
                "day": "Wednesday",
                "value": 391
            },
            {
                "group": "Last Years Average",
                "day": "Monday",
                "watt": 106
            },
            {
                "group": "Last Years Average",
                "day": "Tuesday",
                "watt": 160
            },
            {
                "group": "Last Years Average",
                "day": "Wednesday",
                "watt": 524
            },
            {
                "group": "Last Years Average",
                "day": "Thursday",
                "watt": 683
            },
            {
                "group": "Last Years Average",
                "day": "Friday",
                "watt": 728
            },
            {
                "group": "Last Years Average",
                "day": "Saturday",
                "watt": 829
            },
            {
                "group": "Last Years Average",
                "day": "Sunday",
                "watt": 804
            }
        ]}
            options={{
            "title": "Weekly Overview",
            "axes": {
                "left": {
                    "mapsTo": "value",
                    "scaleType": "linear",
                    "title": "Week Power Production"
                },
                "right": {
                    "mapsTo": "watt",
                    "scaleType": "linear",
                    "title": "Last Years Average",
                    "correspondingDatasets": [
                        "Last Years Average"
                    ]
                },
                "bottom": {
                    "title": "Day",
                    "mapsTo": "day",
                    "scaleType": "labels"
                }
            },
            "comboChartTypes": [
                {
                    "type": "simple-bar",
                    "correspondingDatasets": [
                        "2023"
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
                        "Last Years Average"
                    ]
                }
            ],
            "height": "400px"
        }}
            />
        
      </p>
    </AccordionItem>
    <AccordionItem title="Status">
      <p>
          
          <DataTable
            headers={[
              { key: "name", value: "Name" },
              { key: "voltage", value: "Voltage" },
              { key: "current", value: "Current" },
            ]}
            rows={[
              {
                id: "a",
                name: "L3",
                voltage: "297 A",
                current: 3.0,
                
              },
              {
                id: "b",
                name: "L1",
                voltage: "320 A",
                current: 4.43,
                
              },
            ]}
          />
          
      </p>
    </AccordionItem>
  </Accordion>
  
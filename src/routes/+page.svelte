<script>
  import { Accordion, AccordionItem, DataTable } from "carbon-components-svelte";
  import { ComboChart, MeterChart } from "@carbon/charts-svelte";
      
          import "@carbon/styles/css/styles.css";
          import "@carbon/charts/styles.css";
</script>

<Accordion size="xl">
  <AccordionItem title="Monthly Overview">
    <p>        
      <ComboChart
          data={[
          {
              "group": "2023",
              "month": "January",
              "value": 53
          },
          {
              "group": "2023",
              "month": "February",
              "value": 238
          },
          {
              "group": "2023",
              "month": "March",
              "value": 391
          },
          {
              "group": "2023",
              "month": "April",
              "value": 4
          },
          {
              "group": "Last Years Average",
              "month": "January",
              "watt": 106
          },
          {
              "group": "Last Years Average",
              "month": "February",
              "watt": 160
          },
          {
              "group": "Last Years Average",
              "month": "March",
              "watt": 524
          },
          {
              "group": "Last Years Average",
              "month": "April",
              "watt": 683
          },
          {
              "group": "Last Years Average",
              "month": "May",
              "watt": 728
          },
          {
              "group": "Last Years Average",
              "month": "June",
              "watt": 829
          },
          {
              "group": "Last Years Average",
              "month": "July",
              "watt": 804
          },
          {
              "group": "Last Years Average",
              "month": "August",
              "watt": 742
          },
          {
              "group": "Last Years Average",
              "month": "September",
              "watt": 542
          },
          {
              "group": "Last Years Average",
              "month": "October",
              "watt": 365
          },
          {
              "group": "Last Years Average",
              "month": "November",
              "watt": 139
          },
          {
              "group": "Last Years Average",
              "month": "December",
              "watt": 87
          }
      ]}
          options={{
          "title": "Monthly Overview",
          "axes": {
              "left": {
                  "mapsTo": "value",
                  "scaleType": "linear",
                  "title": "2023 Power Production"
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
                  "title": "Month",
                  "mapsTo": "month",
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
  <AccordionItem title="Monthly Progress">
      <p>
        
        <MeterChart
            data={[
            {
                "group": "Power Generated",
                "value": 5.9
            }
        ]}
            options={{
            "title": "Weekly output relative to Estimation:",
            "meter": {
                "peak": 80,
                "status": {
                    "ranges": [
                        {
                            "range": [
                                0,
                                50
                            ],
                            "status": "success"
                        },
                        {
                            "range": [
                                50,
                                60
                            ],
                            "status": "warning"
                        },
                        {
                            "range": [
                                60,
                                100
                            ],
                            "status": "danger"
                        }
                    ]
                }
            },
            "height": "100px"
        }}
            />
        
    </AccordionItem>
</Accordion>

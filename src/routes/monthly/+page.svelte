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
                "group": "Output",
                "date": "Apr 1",
                "value": 5.6
            },
            {
                "group": "Output",
                "date": "Apr 2",
                "value": 6.9
            },
            {
                "group": "Estimated Output",
                "date": "Apr 1",
                "watt": 6.2
            },
            {
                "group": "Estimated Output",
                "date": "Apr 2",
                "watt": 6.5
            }
        ]}
            options={{
            "title": "Monthly Energy Output",
            "axes": {
                "left": {
                    "mapsTo": "value",
                    "scaleType": "linear",
                    "title": "Power Production"
                },
                "right": {
                    "mapsTo": "watt",
                    "scaleType": "linear",
                    "title": "Estimated Output",
                    "correspondingDatasets": [
                        "Estimated Output"
                    ]
                },
                "bottom": {
                    "title": "Date",
                    "mapsTo": "date",
                    "scaleType": "labels"
                }
            },
            "comboChartTypes": [
                {
                    "type": "simple-bar",
                    "correspondingDatasets": [
                        "Output"
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
                        "Estimated Output"
                    ]
                }
            ],
            "height": "400px"
        }}
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
            "title": "Monthly output relative to Estimation:",
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
  
<script>
    import { Accordion, AccordionItem, DataTable } from "carbon-components-svelte";
    import { ComboChart, MeterChart } from "@carbon/charts-svelte";
        
            import "@carbon/styles/css/styles.css";
            import "@carbon/charts/styles.css";
  </script>
  
  <Accordion size="xl">
    <AccordionItem title="Yearly Overview">
      <p>        
        <ComboChart
            data={[
            {
                "group": "Output",
                "month": "2022",
                "value": 5067
            },
            {
                "group": "Output",
                "month": "2023",
                "value": 1289
            },
            {
                "group": "Estimated Output",
                "month": "2022",
                "watt": 5147
            },
            {
                "group": "Estimated Output",
                "month": "2023",
                "watt": 6543
            }
        ]}
            options={{
            "title": "Yearly Energy Output",
            "axes": {
                "left": {
                    "mapsTo": "value",
                    "scaleType": "linear",
                    "title": "2023 Power Production"
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
                    "title": "Month",
                    "mapsTo": "month",
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
    <AccordionItem title="Yearly Progress">
      <p>
          
        <script>
            import {  } from "@carbon/charts-svelte";
        
            import "@carbon/styles/css/styles.css";
            import "@carbon/charts/styles.css";
        </script>
        
        <MeterChart
            data={[
            {
                "group": "Power Generated",
                "value": 11.9
            }
        ]}
            options={{
            "title": "Yearly output relative to Estimation:",
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
  
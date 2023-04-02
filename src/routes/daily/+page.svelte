<script>
    import { Accordion, AccordionItem, DataTable } from "carbon-components-svelte";
    import { ComboChart, MeterChart } from "@carbon/charts-svelte";
        
            import "@carbon/styles/css/styles.css";
            import "@carbon/charts/styles.css";
  </script>
  
  <Accordion size="xl">
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
    <AccordionItem title="Daily Progress">
      <p>
        
        <MeterChart
            data={[
            {
                "group": "Power Generated",
                "value": 17.4
            }
        ]}
            options={{
            "title": "Daily output relative to Estimation:",
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
  
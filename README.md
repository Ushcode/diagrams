# diagrams
testing different diagram rendering diagrams in markdown


Here is a simple flow chart:

```mermaid
graph LR

subgraph Input
  In["User inputs a desired chemical to manufacture"]
end

subgraph Process
  style DCS fill:#ADD8E6, stroke:#000
  style KG1 fill:#ADD8E6, stroke:#000
  style Parts fill:#ADD8E6, stroke:#000
  style KG2 fill:#ADD8E6, stroke:#000
  style Met fill:#ADD8E6, stroke:#000
  style KG3 fill:#ADD8E6, stroke:#000

  DCS["Deep Chemical Space"]
  KG1["Possible Chemical Routes KG"]
  Parts["Manufacturing Partners"]
  KG2["Abstract Capabilities KG"]
  Met["Metrics for supply chain"]
  KG3["Possible Supply Chains KG"]

  DCS -->|CDI tools to identify routes| KG1
  KG1 -->|filter physically possible chemical routes (no explosive intermediaries etc.)| KG3
  Parts -->|Supplier capabilities added to KG.\\nShare data on molecular\\nstructures, manufacturing processes, etc.| KG2
  KG2 -->|Pair possible routes with routes\\navailable with capabilities / supply chains| KG3
  Met -->|add metrics on cost / \\nvulnerability etc. Asess and give weights| KG3
end

subgraph Output
  style Out fill:#ADD8E6, stroke:#000
  Out["User is presented with possible supply chains"]
end

In -->|User inputs| DCS
KG3 -->|Result| Out

```

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d
    Functionality added                 :milestone, 2014-01-25, 0d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```
<!--![Diagram Image Link](./onshore.puml)-->

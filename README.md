## 📊 Business Operations & Analytics

### Revenue Visibility

**Tech Stack:**

* Data Factory, Lakehouse, Warehouse, Power BI, DAX

**Highlights:**

- Built a revenue visibility platform using Microsoft Fabric
- Implemented Bronze, Silver, and Gold data layers
- Developed dimensional models for sales and customer analytics
- Delivered automated Power BI executive reporting

```mermaid
flowchart TB

    subgraph Sources["Business Systems"]
        CRM["CRM"]
        ERP["ERP"]
        Orders["Orders"]
        Invoices["Invoices"]
    end

    subgraph DF_Env["Data Factory"]
        DF["Data Factory<br>Pipelines"]
        
        subgraph Lakehouse["<br>Lakehouse"]
            A["Bronze<br>Raw Data"] --> B["Silver<br>Business Data"]
            B --> C["Gold<br>Revenue Metrics"]
        end

        WH["Warehouse"]
        SM["Semantic Model"]
    end

    subgraph Reporting["Reporting"]
        Revenue["Revenue"]
        Sales["Sales"]
        Customer["Customers"]
        Forecast["Forecast"]
    end

    %% Links
    CRM & ERP & Orders & Invoices --> DF
    DF --> A
    C --> WH
    WH --> SM
    SM --> Revenue & Sales & Customer & Forecast
```

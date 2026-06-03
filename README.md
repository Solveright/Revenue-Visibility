## 📊 Business Operations & Analytics

### Revenue Visibility

**Tech Stack:**

* Microsoft Fabric, Data Factory, Lakehouse, Warehouse, Power BI, DAX

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

    subgraph DF_Env["<br>Data Factory"]
        DF["Data Factory<br>Pipelines"]
        
    subgraph Lakehouse["<br>Lakehouse"]
            A["Bronze<br>Raw Data"] --> B["Silver<br>Business Data"]
            B --> C["Gold<br>Revenue Metrics"]
        end

    subgraph Analytics["<br>Analytics Layer"]
        WH[Warehouse]
        SM[Semantic Model]
    end

    subgraph Reporting["Reporting"]
        Revenue["Revenue"]
        Sales["Sales"]
        Customer["Customers"]
        Forecast["Forecast"]
    end

    %% Data Ingestion
    CRM --> DF
    ERP --> DF
    Orders --> DF
    Invoices --> DF

    %% Inside Data Factory Flow
    DF --> A
    C --> WH
    WH --> SM

    %% Reporting Layer Consumption
    SM --> Revenue
    SM --> Sales
    SM --> Customer
    SM --> Forecast
```

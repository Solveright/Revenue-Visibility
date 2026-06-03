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
    graph TD
    subgraph Data Factory["Data Factory"]
        DF["Pipelines"]
        subgraph Lakehouse
        A[Bronze<br>Raw Data] --> B[Silver<br>Business Data]
        B --> C[Gold<br>Revenue Metrics]
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

    CRM --> DF
    ERP --> DF
    Orders --> DF
    Invoices --> DF

    Gold --> WH
    WH --> SM

    SM --> Revenue
    SM --> Sales
    SM --> Customer
    SM --> Forecast
```

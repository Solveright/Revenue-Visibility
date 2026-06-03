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

    subgraph Data Factory
        DF["Pipelines"]

        subgraph Lakehouse["Lakehouse"]
            Bronze["Bronze<br/>Raw Data"]
            Silver["Silver<br/>Business Data"]
            Gold["Gold<br/>Revenue Metrics"]
        end

        WH["Warehouse"]
        SM["Semantic Model"]
    end

    subgraph Result["Result"]
        Revenue["Revenue Dashboard"]
        Sales["Sales Analysis"]
        Customer["Customer Insights"]
        Forecast["Revenue Forecast"]
    end

    CRM --> DF
    ERP --> DF
    Orders --> DF
    Invoices --> DF

    DF --> Bronze
    Bronze --> Silver
    Silver --> Gold

    Gold --> WH
    WH --> SM

    SM --> Revenue
    SM --> Sales
    SM --> Customer
    SM --> Forecast
```

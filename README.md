## 📊 Business Operations & Analytics

### Revenue Visibility

**Tech Stack:**

* Microsoft Fabric, Data Factory, Lakehouse, Warehouse, Power BI, DAX

**Highlights:**

* Built an end-to-end revenue analytics solution using Microsoft Fabric
* Implemented Medallion Architecture (Bronze, Silver, Gold) for business data
* Developed a dimensional model for revenue, customer, product, and sales analysis
* Created Power BI dashboards for executive reporting and revenue visibility
* Automated data ingestion and transformation using Fabric Data Factory

```mermaid
flowchart TB

    subgraph Sources["Business Systems"]
        CRM["CRM"]
        ERP["ERP"]
        Orders["Orders"]
        Invoices["Invoices"]
    end

    subgraph
        DF["Data Factory"]

        subgraph Lakehouse["Lakehouse"]
            Bronze["Bronze<br/>Raw Data"]
            Silver["Silver<br/>Business Data"]
            Gold["Gold<br/>Revenue Metrics"]
        end

        WH["Warehouse"]
        SM["Semantic Model"]
    end

    subgraph BI["Power BI"]
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

# graphql



# What is GraphQL?

**GraphQL** is a query language for APIs and a runtime for executing those queries with your existing data. It was developed by Facebook in 2012 and released as an open-source project in 2015.

## 🔍 Key Features

- **Declarative Data Fetching**: Clients specify exactly what data they need.
- **Single Endpoint**: Unlike REST, GraphQL APIs typically use a single endpoint.
- **Strongly Typed Schema**: The API is defined by a schema that specifies types and relationships.
- **Real-time Data**: Supports subscriptions for real-time updates.

## 🧱 Core Concepts

- **Schema**: Defines the structure of the API.
- **Types**: Describe the shape of data (e.g., `User`, `Post`).
- **Queries**: Read operations to fetch data.
- **Mutations**: Write operations to modify data.
- **Resolvers**: Functions that resolve a value for a type or field.
- **Subscriptions**: Enable real-time communication via WebSockets.

## 📦 Example Query

```graphql
query {
  user(id: "1") {
    name
    email
  }
}
```

```mermaid

graph TD
    A[GraphQL] --> B[Schema]
    B --> C[Queries]
    B --> D[Mutations]
    B --> E[Subscriptions]
    B --> F[Resolvers]
    A --> G[Benefits over REST]
    G --> H[Efficient Data Fetching]
    G --> I[Strongly Typed Schema]
    G --> J[Real-time Data]
    G --> K[Reduced Overfetching]

    %% Styling for benefit nodes
    classDef benefit fill:#d4f7dc,stroke:#2e7d32,stroke-width:1px;
    class G,H,I,J,K benefit;


%% Define a custom style for benefits
    classDef title fill:#ffff00,stroke:#2e7d32,stroke-width:4px;

    %% Apply the style to benefit nodes
    class A title;
```



```mermaid

graph TD
    subgraph Benefits_over_REST [Benefits over REST]
        G1[✅ Efficient Data Fetching]
        G2[✅ Strongly Typed Schema]
        G3[✅ Real-time Data]
        G4[✅ Reduced Overfetching]
    end
```

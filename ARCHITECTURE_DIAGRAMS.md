# Architecture Diagrams

This document contains architecture diagrams illustrating the microfrontend architecture and monorepo structure of this project.

## Microfrontend Architecture

The following diagram illustrates how the microfrontends are composed and interact within the single-spa framework:

```mermaid
graph TD
    subgraph "Browser"
        A[User Browser]
    end
    
    subgraph "Single-SPA Root Config"
        B[Root Config - Port 9000]
        C[Layout Engine]
        D[Router]
    end
    
    subgraph "Microfrontends"
        E[Navigation MFE - Port 8080]
        F[Future MFE 1]
        G[Future MFE 2]
    end
    
    A -->|"/localhost:9000"| B
    B --> C
    C --> D
    D -->|"Route: /"| E
    D -->|"Route: /future1"| F
    D -->|"Route: /future2"| G
    
    classDef rootConfig fill:#f9f,stroke:#333,stroke-width:2px;
    classDef microfrontend fill:#bbf,stroke:#333,stroke-width:1px;
    classDef browser fill:#dfd,stroke:#333,stroke-width:1px;
    
    class B,C,D rootConfig;
    class E,F,G microfrontend;
    class A browser;
```

## Runtime Flow

This diagram shows the runtime flow of how the application loads and renders microfrontends:

```mermaid
sequenceDiagram
    participant Browser
    participant RootConfig as Root Config (Port 9000)
    participant ImportMap as Import Map
    participant LayoutEngine as Layout Engine
    participant NavigationMFE as Navigation MFE (Port 8080)
    
    Browser->>RootConfig: Navigate to http://localhost:9000
    RootConfig->>ImportMap: Load import map
    ImportMap-->>RootConfig: Return module URLs
    RootConfig->>LayoutEngine: Initialize layout
    LayoutEngine->>RootConfig: Return layout definition
    RootConfig->>NavigationMFE: Load @titanco/titanco-navigation
    NavigationMFE-->>RootConfig: Return lifecycle functions
    RootConfig->>NavigationMFE: bootstrap()
    NavigationMFE-->>RootConfig: Bootstrapped
    RootConfig->>NavigationMFE: mount()
    NavigationMFE-->>RootConfig: Mounted
    NavigationMFE-->>Browser: Render navigation UI
```

## Monorepo Structure

This diagram illustrates the monorepo structure and how the packages are organised:

```mermaid
graph TD
    A[single-spa-demo]
    
    subgraph "Root Package"
        B[package.json]
        C[README.md]
        D[ARCHITECTURE.md]
        E[DEVELOPMENT.md]
    end
    
    subgraph "Shell Package"
        F[titanco-root-app]
        F1[package.json]
        F2[src/]
        F3[src/index.ejs]
        F4[src/microfrontend-layout.html]
        F5[src/titanco-root-config.ts]
    end
    
    subgraph "Microfrontend Packages"
        G[titanco-navigation]
        G1[package.json]
        G2[src/]
        G3[public/]
    end
    
    A --> B
    A --> C
    A --> D
    A --> E
    
    A -->|packages/shell/| F
    F --> F1
    F --> F2
    F2 --> F3
    F2 --> F4
    F2 --> F5
    
    A -->|packages/microfrontends/| G
    G --> G1
    G --> G2
    G --> G3
    
    classDef root fill:#f9f,stroke:#333,stroke-width:1px;
    classDef shell fill:#bbf,stroke:#333,stroke-width:1px;
    classDef microfrontend fill:#dfd,stroke:#333,stroke-width:1px;
    
    class A,B,C,D,E root;
    class F,F1,F2,F3,F4,F5 shell;
    class G,G1,G2,G3 microfrontend;
```

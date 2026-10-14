## Question 2: Directed Graph and Search Tree

**Abstraction:** A state is the town the trailer is in, and an action is driving along a highway to the next connected town. Minor towns and junctions between two listed towns, traffic, road works and weather are left out. Dead-end towns (Makindu, Kajiado, Migori) are kept because the agent cannot know in advance that they do not lead to Kisumu.

### Directed graph

```mermaid
graph LR
    Nairobi((Nairobi)) --> Ruiru((Ruiru))
    Nairobi --> AthiRiver((Athi River))
    Nairobi --> Naivasha((Naivasha))
    Nairobi --> Narok((Narok))
    Ruiru --> Thika((Thika))
    Thika --> Karatina((Karatina))
    Karatina --> Nyeri((Nyeri))
    Nyeri --> Nyahururu((Nyahururu))
    Nyahururu --> Nakuru((Nakuru))
    AthiRiver --> Makindu((Makindu))
    AthiRiver --> Kajiado((Kajiado))
    Naivasha --> Gilgil((Gilgil))
    Gilgil --> Nakuru
    Nakuru --> Kericho((Kericho))
    Kericho --> Kisumu((Kisumu))
    Narok --> Bomet((Bomet))
    Bomet --> Kisii((Kisii))
    Kisii --> Kisumu
    Kisii --> Migori((Migori))
    Kisii --> HomaBay((Homa Bay))
    HomaBay --> Kisumu
    style Nairobi fill:#cfe8ff,stroke:#1f6feb
    style Kisumu fill:#d4f8d4,stroke:#1a7f37
```

### Search tree

```mermaid
graph TD
    R((Nairobi))
    R --> A1((Ruiru))
    R --> B1((Athi River))
    R --> C1((Naivasha))
    R --> D1((Narok))

    A1 --> A2((Thika))
    A2 --> A3((Karatina))
    A3 --> A4((Nyeri))
    A4 --> A5((Nyahururu))
    A5 --> A6((Nakuru))
    A6 --> A7((Kericho))
    A7 --> A8((Kisumu))

    B1 --> B2((Makindu))
    B1 --> B3((Kajiado))

    C1 --> C2((Gilgil))
    C2 --> C3((Nakuru))
    C3 --> C4((Kericho))
    C4 --> C5((Kisumu))

    D1 --> D2((Bomet))
    D2 --> D3((Kisii))
    D3 --> D4((Kisumu))
    D3 --> D5((Migori))
    D3 --> D6((Homa Bay))
    D6 --> D7((Kisumu))

    style R fill:#cfe8ff,stroke:#1f6feb
    style A8 fill:#d4f8d4,stroke:#1a7f37
    style C5 fill:#d4f8d4,stroke:#1a7f37
    style D4 fill:#d4f8d4,stroke:#1a7f37
    style D7 fill:#d4f8d4,stroke:#1a7f37
```

In the tree, a town reached by a different route appears again as a separate node (Nakuru, Kericho and Kisumu repeat), because each node represents one path from Nairobi.
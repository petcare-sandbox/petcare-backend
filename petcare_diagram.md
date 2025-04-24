```mermaid
flowchart TD
    A["Client"] -- REST API --> B["API Gateway"]
    B -- gRPC --> C["Auth Service"] & D["Owner Service"] & E["Doctor Service"] & F["Procedure Service"] & G["Appointment Service"] & H["Payment Service"] & P["Pet Service"]
    F -- gRPC --> P
    H -- Payment Gateway --> K["External Payment Provider"]
    G -- gRPC --> D & E & F & H
    D -- gRPC --> P
    E -- gRPC --> P
    G -- Kafka --> n1["Notification Service"]
    H -- Kafka --> n1


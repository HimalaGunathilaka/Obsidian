
- **Session Layer Protocol**  
    CoAP operates over the **session layer**, suitable for constrained devices in IoT environments.
    
- **Web Transfer Protocol (like HTTP)**  
    It works similarly to **HTTP**, using a request/response model.
    
- **Lightweight Protocol**
    
    - Designed for **low power**, **low memory**, and **low bandwidth** devices.
        
    - Ideal for constrained nodes and networks (e.g., in IoT).
        
- **REST-based Architecture**
    
    - Follows **REST principles**, enabling CRUD operations (GET, POST, PUT, DELETE).
        
- **Uses UDP (User Datagram Protocol)**
    
    - Unlike HTTP (which uses TCP), CoAP uses **UDP** to reduce overhead and improve performance in constrained environments.
        
- **Supports Proxying and Caching**
    
    - Includes mechanisms for **caching** responses and **proxying** messages to improve efficiency and scalability.
        

---

## **Packet Structure**

- **Header**: Contains message type, code, message ID, etc.
- **Token**: Used to match requests and responses.
- **Options**: Similar to HTTP headers (e.g., URI path, content format).
- **Payload**: The actual message content.

---

## **Communication Model**

- Follows **Request-Response** pattern (like HTTP
- Can be **configured to include ACKs** (Confirmable messages) or not (Non-confirmable messages).
    - **Confirmable**: Requires acknowledgment (reliable transmission).
    - **Non-confirmable**: No acknowledgment needed (faster, less reliable).

---

## **Security**

- Uses **DTLS (Datagram Transport Layer Security)** for security over UDP.
    - DTLS is TLS adapted for datagram-based communication.
    - Provides encryption, authentication, and integrity.
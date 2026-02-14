🚀 Cipher - No-Internet Messenger
Cipher is a high-performance Android messaging application designed for off-grid communication. It enables users to exchange text messages and images without needing a cellular network, Wi-Fi router, or internet connection by leveraging Wi-Fi Direct (P2P) technology.

✨ Features
True Offline Chat: No internet? No problem. Chat device-to-device via local Wi-Fi.
Media Sharing: Send and receive images seamlessly without data costs.
Low Latency: Uses raw TCP Sockets for near-instant message delivery.
Background Stability: Implements Android Foreground Services to keep the connection alive even when the app is minimized.
Modern UI: Clean, responsive chat interface with local message history.

🛠️ Technical Stack
Language: Kotlin
Architecture: Model-View-ViewModel (MVVM) approach.
Networking: Java/Kotlin TCP Sockets (ServerSocket & Socket).
Protocol: Custom Header-Length-Data byte stream protocol for reliable packet delivery.
Discovery: Wi-Fi P2P (Wi-Fi Direct) for hardware-level device pairing.
UI: RecyclerView with multiple ViewTypes for dynamic Text/Image bubbles.

⚙️ How it Works
Discovery: The app uses the WifiP2pManager to scan for nearby devices running Cipher.
Handshake: Once a peer is selected, one device acts as the Group Owner (Server) and the other as the Client.
The Stream: A dedicated ChatManager opens a DataOutputStream. It sends a "Header" (stating if the data is text or an image), followed by the "Length" of the data, and finally the "Payload."
Security: Runs as a Foreground Service with connectedDevice type to ensure the OS doesn't kill the connection during a chat.

📲 Installation
Clone this repository.
Open in Android Studio (Ladybug or newer recommended).
Ensure both devices have Location and Nearby Devices permissions enabled.
Build and Run!

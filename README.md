# research_webrtc_and_sip
Research webrtc and sip to call P2P


## WebRTC

### Build Server

1. Directory to webrtc server

```bash
cd webrtc/flutter-webrtc-server
```

2. Use `mkcert` to create a self-signed certificate.

```bash
brew update
brew install mkcert
mkcert -key-file configs/certs/key.pem -cert-file configs/certs/cert.pem  localhost 127.0.0.1 ::1 0.0.0.0
```

3. Run

```bash
brew install golang
go run cmd/server/main.go
```

- Open https://0.0.0.0:8086 to use flutter web demo.
- If you need to test mobile app, please check the [webrtc-flutter-demo](https://github.com/cloudwebrtc/flutter-webrtc-demo). 

### Build Client

#### Mobile

1. `cd webrtc/flutter-webrtc-demo`
2. `flutter packages get`
3. `flutter run`
4. Use `P2P Call Example` and enter your server address into the example app

#### Web
- if you already run `flutter-webrtc-server` then open https://0.0.0.0:8086

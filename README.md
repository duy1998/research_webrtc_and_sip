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

## screenshots
# iOS
<img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/flutter-webrtc-ios-example.png"/> <img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/ios-01.jpeg"/> <img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/ios-02.jpeg"/>
# Android
<img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/flutter-webrtc-android-example.png"/> <img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/android-01.png"/> <img width="180" height="320" src="https://raw.githubusercontent.com/cloudwebrtc/flutter-webrtc-demo/master/screenshots/android-02.png"/>

## SIP

### Build Server

Note: You must install and run Docker

1. Directory to Asterisk server

```bash
cd sip/docker/asterisk
```

2. Run `make`

### Build Client

#### Mobile

1. `cd sip/dart-sip-ua`
2. `flutter packages get`
3. `flutter run`
4. Register with server

- server_ip=your docker host ip

- Weobsocket: wss://server_ip:8089/ws
- SIP URI: 500@server_ip
- Authorizathion User: 500
- Password: 500
- Display Name: Bob

Note: We need to register in two devices to testing

### Screenshot

<img width="180" height="400" src="https://github.com/flutter-webrtc/dockers/raw/main/screenshots/asterisk/01.jpg"/> <img width="180" height="400" src="https://github.com/flutter-webrtc/dockers/raw/main/screenshots/asterisk/02.jpg"/>

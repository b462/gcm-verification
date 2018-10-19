# GCM verification for Jodel

This application provides two HTTP endpoints to create an Android account and to receive verification messages from GCM.
The server is written in Rust and needs nightly for async/await support.

Endpoints:
- GET http://127.0.0.1:8080/account
  response: `{"android_account":{"android_id":"XXX","security_token":"XXX"},"gcm_token":"XXX"}`
- POST http://127.0.0.1:8080/verification
  body: `{"android_id":"XXX","security_token":"XXX"}`
  response: `{"verification":{"server_time":0,"type":"silent_verification","verification_code":"XXX"}}`

Run server locally:

    cargo run

## License

Copyright: AsamK 2018

Licensed under the GPLv3: http://www.gnu.org/licenses/gpl-3.0.html

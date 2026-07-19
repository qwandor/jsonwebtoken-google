# Parse and validate Google JWT tokens

This is a fork of https://github.com/avkviring/jsonwebtoken-google, which seems to be unmaintained.
It just updates some dependencies.

```rust
#[derive(Debug, Serialize, Deserialize)]
pub struct TokenClaims {
    pub email: String,
    pub aud: String,
    pub iss: String,
    pub exp: u64,
}

async fn main() {
    let parser = Parser::new("some-google-web-client-id");
    let claims = parser.parse::<TokenClaims>("some-token").await.unwrap();
}
```

##  InterPlanetary File System (IPFS) Rust Interface

**Effortless IPFS Integration for Rust Projects**

This library streamlines interaction with the IPFS HTTP API, eliminating the need for complex manual wrappers or external dependencies.

**Example:**

```rust
mod utils;
mod ipfs;

use ipfs::IpfsClient;
use utils::DataHandler;


fn main() {
    let mut client = IpfsClient::new();
    client.set_host("http://localhost:5001");

    let add_result = client.add_file("./data.txt");
    let hash = DataHandler::extract_hash(&add_result);
    assert_eq!(hash, "Qm..."); // Replace with expected hash

    let file_content = client.get_file(&hash);
    let decoded_content = DataHandler::decode_string(&file_content);
    assert_eq!(decoded_content, "Your file content");
}
```

Simplify your IPFS integration today!

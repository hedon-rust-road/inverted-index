# Rust Inverted Index

This Rust project implements an Inverted Index for efficient document retrieval with support for query term highlighting. It uses a combination of custom tokenization and regex-based highlighting to provide an intuitive interface for searching text documents stored in memory.

## Features

- **Document Indexing**: Efficiently indexes documents by tokenizing text into words and mapping them to their respective document IDs.
- **Query Search**: Allows searching for documents that contain a given word or phrase, with case-insensitivity.
- **Highlighting**: Highlights all occurrences of the search term in the returned document text in purple for easy identification.
- **Custom Tokenization**: Splits text into words based on alphanumeric boundaries, improving on traditional whitespace-based methods.

## Usage

### Adding Documents

To add documents to the index, use the `add` method with a unique document ID and the text content of the document:

```rust
let mut index = InvertedIndex::new();
index.add(1, "Rust is safe and fast.");
index.add(2, "Rust is a systems programming language.");
index.add(3, "Programming in Rust is fun.");
```

### Querying

To query the index for documents containing a specific term and get the highlighted results:

```rust
let results = index.query("Rust");
for result in results {
    println!("{}", result);
}
```

### Highlights

Query results will highlight the search term in purple:

```plaintext
Rust is safe and fast.
Rust is a systems programming language.
Programming in Rust is fun.
```

## Installation

Ensure you have Rust installed on your machine. [Install Rust](https://www.rust-lang.org/tools/install).

Clone this repository and move into the project directory:

```bash
git clone https://github.com/hedon954/rust-action-by-hedon
cd rust-action-by-hedon/inverted_index
```

Run the project using Cargo:

```bash
cargo run
```

## Tests

Run tests to ensure that the tokenization and highlighting functions are working as expected:

```bash
cargo test
```

This will execute predefined unit tests for the tokenization of text and the highlighting of query terms within text content.

## Dependencies

This project uses the `regex` and `colored` crates from crates.io:

```toml
[dependencies]
colored = "2.1.0"
regex = "1.10.4"
```

Make sure to include them in your `Cargo.toml` file to utilize the functionality they provide.

## Contributing

Contributions to this project are welcome! Please fork the repository and submit a pull request with your feature or fix.

## License

This project is licensed under the Apache License - see the [LICENSE.md](https://github.com/hedon954/rust-action-by-hedon/blob/main/LICENSE) file for details.

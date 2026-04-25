# Nostream Competency Test

This project demonstrates a TypeScript-based implementation of a Web of Trust (WoT) builder and NIP-13 Proof of Work verifier for the Nostr protocol. It showcases proficiency with the Nostream relay infrastructure, Nostr protocol NIPs, and TypeScript development.

## Features

1. **Web of Trust Graph Builder**: Recursively traverses social graphs from a Nostr relay and generates an interactive visualization.
2. **NIP-13 Proof of Work Validator**: Validates Nostr events against Proof of Work difficulty targets.
3. **Interactive CLI**: Provides an easy-to-use interface for building the Web of Trust or verifying events.

## Project Structure

```
competency-test/
├── index.ts          # Core WoT builder and PoW verifier logic
├── cli.ts            # Interactive CLI interface
├── graphBuilder.ts   # HTML graph visualization export
├── unit.test.ts      # Unit tests for core functions
├── wot-graph.html    # Generated graph visualization (output)
├── README.md         # Project documentation
└── package.json      # Project dependencies and scripts
```

## Setup & Installation

### Prerequisites
- **Node.js** (v18 or higher)
- **npm** (or yarn)
- **Git**

### Installation Steps

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd competency-test
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Build the TypeScript files:
   ```bash
   npm run build
   ```

## Usage

### Run the CLI

Start the interactive CLI:
```bash
npm run cli
```

#### Option 1: Build Web of Trust
- Select **Option 1** in the CLI.
- The script will:
  - Connect to the configured Nostr relay.
  - Traverse the social graph up to the specified depth.
  - Generate an interactive graph visualization (`wot-graph.html`).
- Open the `wot-graph.html` file in a browser to explore the graph.

#### Option 2: Verify Event PoW
- Select **Option 2** in the CLI.
- Paste a Nostr event JSON (single-line format) when prompted.
- The script will validate the event and display the result.

Example event JSON:
```json
{
  "id": "0000000000000000000000000000000000000000000000000000000000000000","pubkey": "3bf0c63fcb93463407af97a5e5ee64fa883d107ef9e558472c4eb9aaaefa459d","kind": 1,"tags": [["nonce", "1000000", "20"]],"content": "Hello, Nostr!","created_at": 1672531200,"sig": "6b3144707a52dc5fbc6e0f0f6c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c8c"}
```

## Testing

Run unit tests to verify core functionality:
```bash
npm run test
```

## Technical Details

### Technologies Used
- **TypeScript**: Type-safe implementation.
- **Nostr Protocol**: Implements NIP-01, NIP-13, and NIP-19.
- **WebSocket**: Real-time communication with Nostr relays.
- **vis-network**: Library for graph visualization.
- **Commander.js**: CLI argument parsing.
- **nostr-tools**: Utilities for Nostr encoding/decoding.

### Key Algorithms
- **Graph Traversal**: BFS-like approach with batching and cycle prevention.
- **Proof of Work Validation**: Counts leading zero bits in event IDs and compares against difficulty targets.

### Performance
- Typical execution time for a 2-hop graph: ~12 seconds.
- Memory usage: <50MB for graphs with 2,000+ nodes.

## Author
Saniddhya Dubey

For questions or feedback, feel free to reach out!

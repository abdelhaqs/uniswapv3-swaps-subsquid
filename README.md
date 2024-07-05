# UniswapV3 Swaps Indexing Lab

This is a lab to test indexing UniswapV3 swaps data using Subsquid. This project serves as a starter template of a squid indexer for EVM networks (Ethereum, Polygon, BSC, etc.). See [Squid SDK docs](https://docs.subsquid.io/) for a complete reference.

For a step-by-step migration guide from TheGraph, see [the dedicated docs page](https://docs.subsquid.io/migrate/migrate-subgraph/).

Prerequisites: Node.js, Docker.

## Quickstart

### Prerequisites

1. Install Node.js from the [official website](https://nodejs.org/en).

2. On Windows, resolve script execution policy issues by running the following PowerShell commands:

    ```powershell
    Get-ExecutionPolicy
    Set-ExecutionPolicy RemoteSigned
    Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```

### Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/subsquid-labs/uniswapv3-swaps-example.git
    cd uniswapv3-swaps-example
    ```

2. Install @subsquid/cli globally:

    ```bash
    npm i -g @subsquid/cli
    ```

3. Install dependencies:

    ```bash
    npm ci
    ```

4. Start a Postgres database container and detach:

    ```bash
    sqd up
    ```

5. Build and start the processor:

    ```bash
    sqd process
    ```

6. The command above will block the terminal, being busy with fetching the chain data, transforming and storing it in the target database.

7. To start the GraphQL server, open a separate terminal and run:

    ```bash
    sqd serve
    ```

A GraphiQL playground will be available at [localhost:4350/graphql](http://localhost:4350/graphql) to query the indexed data.

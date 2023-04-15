## Small PoC setting up a subgraph node for the ShimmerEVM Testnet

### Setup

1. Run graph-compiler

```bash
npx graph-compiler --config configs/config.json --include node_modules/@openzeppelin/subgraphs/src/datasources --export-schema --export-subgraph
```

1. Create subgraph

```bash
graph create generated/test --node http://127.0.0.1:8020
```

3. Deploy subgraph to local graph node 
   
```bash
graph deploy --ipfs http://localhost:5001 --node http://localhost:8020 generated/test ./generated/test.subgraph.yaml
```
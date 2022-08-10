# NextJS NFT Marketplace with TheGraph

## 1. Git clone the contracts repo

In it's own terminal / command line, run:

```
git clone https://github.com/CheckThisIn/hardhat-nft-marketplace-fcc
cd hardhat-nextjs-nft-marketplace-fcc
yarn
```

## 2. Deploy to rinkeby

After installing dependencies, deploy your contracts to rinkeby:

```
yarn hardhat deploy --network rinkeby
```

## 3. Deploy your subgraph

```
cd ..
git clone https://github.com/CheckThisIn/graph-nft-marketplace-fcc
cd graph-nft-marketplace-fcc
yarn
```

Follow the instructions of the [README](https://github.com/CheckThisIn/graph-nft-marketplace-fcc/blob/main/README.md) of that repo.

Then, make a `.env` file and place your temporary query URL into it as `NEXT_PUBLIC_SUBGRAPH_URL`.

## 4. Start your UI

Make sure that:

- In your `networkMapping.json` you have an entry for `NftMarketplace` on the rinkeby network.
- You have a `NEXT_PUBLIC_SUBGRAPH_URL` in your `.env` file.

```
yarn dev
```

# Graph NFT Marketplace FCC

# Quickstart

1. Install Subgraph CLI

```
yarn global add @graphprotocol/graph-cli
```

2. Log into [the graph UI](https://thegraph.com/studio/subgraph) and create a new Subgraph.

Use Rinkeby as the network.

3. Initialize Subgraph

```
graph init --studio nft-marketplace
```

4. Authenticate CLI

```
graph auth  --studio YOUR_DEPLOY_KEY_HERE
```

5. Update your `subgraph.yaml`

- Update the `address` with your NftMarketplace Address
- Update the `startBlock` with the block right before your contract was deployed

6. Build graph locally

```
graph codegen && graph build
```

- `graph codegen`: Generates code in the `generated` folder based on your `schema.graphql`
- `graph build`: Generates the build that will be uploaded to the graph

7. Deploy subgraph

Replace `VERSION_NUMBER_HERE` with a version number like `0.0.1`.

```
graph deploy --studio nft-marketplace -l VERSION_NUMBER_HERE
```

8. View your UI

Back in your hardhat project, mint and list an NFT with:

```
yarn hardhat run scripts/mint-and-list-item.js --network rinkeby
```

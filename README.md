## 📌 To use this code:

- Clone this repo or download the latest release zip file.
- Unzip, if needed, and open the folder in VS Code.
- From the terminal type:
    `npm install`
- Copy your image layers into the `layers` folder.
- Use the `src/config.js` file to set up your layers and NFT information.
<br>

## 🔗 Links:

1. **NFT Forge Website Repo: https://github.com/himanshu-03/NFT-Forge-Website** 

2. **NFT Forge Live Website: https://himanshu-03.github.io/NFT-Forge-Website/**

3. **OpenSea: https://opensea.io/collection/oye-paaji**

4. **NFT Product Contracts: https://polygonscan.com/address/0x33cfce113d154f1920ea0b48053ad801636f8293**

<br />

## 📝 Steps to Generate, Upload and Mint your NFTs on OpenSea:

## Step 1 - Generating NFT

1. Head over to `src/config.js` in the project directory

    ```js
        const namePrefix = "OyePaaji";
        const description = "OyePaaji is a collection of 999 NFTs living on the Polygon blockchain. With over 50+ hand-drawn traits.";
        const baseUri = "ipfs://NewUriToReplace";

        const solanaMetadata = {
        symbol: "OP",
        seller_fee_basis_points: 1000, 
        external_url: "https://himanshu-03.github.io/NFT-Forge-Website/",
            creators: [
                {
                    address: "",  // Update your own wallet address
                    share: 100,
                },
            ],
        };
    ```

2. Add your **NFT Name**, **Description**, **Symbol**, and **External URL** for your NFT project.

3. The `seller_fee_basis_points` is royalty fees which is measured in **basis per points (bps)** where **100bps = 1%**

4. Add your **wallet address** in the `address` section.

    ```js
        const layerConfigurations = 
        [
            {
                growEditionSizeTo:100,
                layersOrder: [
                    { name: "SHIRT" },
                    { name: "HEAD" },
                    { name: "FACE" },
                    { name: "BEARD" },
                    { name: "MASK" },
                    { name: "SPECS" },
                        ]
            },
        ];
    ```

5. Update the **layers** in `layersOrder` as per your designs and assign the `growEditionSizeTo` with a number of NFTs you wish to generate.

6. Run the below command for generating NFTs with unique DNA.

    ```bash
    npm run generate
    ```
<br />


## Step 2 - Uploading the arts to IPFS Decentralized Storage

1. Head over to `utils/nftport/uploadFiles.js` in the project directory.

    ```js
    const AUTH = '';   // Add your own NFTPort API Key
    const TIMEOUT = 1000;
    ```

2. Mention your own NFTPort API Key in the `AUTH`. *You can generate your NFTPort API Key [here](https://www.nftport.xyz/)*

3. Run the below command for uploading your NFT Arts on IPFS Cloud Storage and getting a unique **metadata_uri** for each of them.

    ```bash
    node utils/nftport/uploadFiles.js
    ```

<br />

## Step 3 - Updating the Metadata of the files with the unique `metadata_uri` generated by uploading on IPFS

1.  Head over to `utils/nftport/updateMetas.js` in the project directory.

    ```js
    const AUTH = '';   // Add your own NFTPort API Key
    const TIMEOUT = 1000;
    ```

2. Mention your own NFTPort API Key in the `AUTH`. *You can generate your NFTPort API Key [here](https://www.nftport.xyz/)*

3. Run the below command for updating your **metadata file** with the unique **metadata_uri** generated by uploading on IPFS

    ```bash
    node utils/nftport/uploadMetas.js
    ```

<br />

## Step 4 - Minting the NFT Arts on OpenSea Platform via Polygon PoS Chain

1. Head over to `utils/nftport/mint.js` in the project directory.

    ```js
    const AUTH = '';  // Add your NFTPort API Key
    const CONTRACT_ADDRESS = '';  // Add your contract address
    const MINT_TO_ADDRESS = ''; // Add your wallet address
    const CHAIN = 'polygon';
    const TIMEOUT = 2000;
    ```

2. Update the `AUTH`, `CONTRACT_ADDRESS`, `MINT_TO_ADDRESS` with your **NFTPort API Key**, **Contract Address** and **Wallet Address** respectively.

    > *Note: You can find your `CONTRACT_ADDRESS` by logging into your NFTPort account and hovering [here](https://dashboard.nftport.xyz/contracts)*.

3. Run the below command for successfully minting the NFT's on OpenSea

    ```bash
    node utils/nftport/mint.js
    ```

<br />

**Do star the Repo ✨ if you found it usefull..!!**
 

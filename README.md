# MongoDB API for ERC-721 Tokens

This project implements a basic Node.js API for managing ERC-721 token metadata with MongoDB. It provides functionality to create and retrieve token metadata through RESTful endpoints.

## Prerequisites

Before you start, ensure you have the following installed on your system:

- **Node.js and npm** (Node.js 18.x or later is recommended)

## Installation

### Clone the Repository

Start by cloning this repository to your local machine:

```bash
git clone https://your-repository-url.git
cd mongodb-api
```

### Install Dependencies

Run the following command in your project directory to install the necessary packages:

```bash
npm install
```

### Run Server

To start the server, run:

```bash
node api-server.js
```

## Usage

### Create Token Metadata

To add new token metadata, use the following query command:

```bash
curl -X POST http://localhost:3000/api/token \
-H "Content-Type: application/json" \
-d '{
    "name": "Example Token",
    "symbol": "EXT",
    "baseURI": "http://example.com/token",
    "description": "This is an example token.",
    "contractRedemptionVoucher": {
        "voucherId": "voucher123",
        "validUntil": "2024-12-31T23:59:59Z"
    },
    "thumbnail": "http://example.com/image.jpg",
    "externalURL": "http://example.com",
    "assetURL": "http://example.com/asset.jpg"
}'
```

Example Response:

{"name":"MyNFT","symbol":"MNFT","baseURI":"http://example.com/nft","description":"This is a description of my NFT.","contractRedemptionVoucher":{"voucherId":"123456","validUntil":"2023-12-31T23:59:59.000Z"},"thumbnail":"http://example.com/nft/thumbnail.jpg","externalURL":"http://example.com","assetURL":"http://example.com/nft/asset.jpg","_id":"66419766c9797b8a7e0b2a7e","__v":0}%  

Token ID = "_id"

### Retrieve Token Metadata

To retrieve token metadata by ID, use the following curl command:

```bash
curl -X GET http://localhost:3000/api/token/<TokenID>
```
Replace <TokenID> with the actual ID of the token you wish to retrieve.
## Tech stack

- Contracts: Supra Framework: Move, Typescript
- Frontend: [Next.js](https://nextjs.org/), [tailwindcss](https://tailwindcss.com), [daisyui](https://daisyui.com)
- Backend: [Supabase](https://supabase.com), [Prisma](https://prisma.io), [Rxjs](https://rxjs.dev/)

## Development

### Frontend

- Installation

  ```
  yarn workspace market-frontend install
  ```

- Config `.env.development.local`

  In order to expose a variable to the browser you have to prefix the variable with `NEXT_PUBLIC_`

  ```
  NEXT_PUBLIC_NFT_STORAGE_KEY=
  NEXT_PUBLIC_WALLET_PRIVATE_KEY=
  NEXT_PUBLIC_MARKET_ADDRESS=0x64f236ab7ba803a8921c16fa2b9995da51033e3ed2e284e358f0d5431a39c0d0
  NEXT_PUBLIC_MARKET_NAME=_1200_dollars_per_hour
  NEXT_PUBLIC_MARKET_FEE_NUMERATOR=10
  NEXT_PUBLIC_MARKET_INITIAL_FUND=10000
  NEXT_PUBLIC_MARKET_COIN_TYPE=0x1::aptos_coin::AptosCoin
  NEXT_PUBLIC_APTOS_NODE_URL=https://fullnode.devnet.aptoslabs.com/v1/
  NEXT_PUBLIC_APTOS_FAUCET_URL=https://faucet.devnet.aptoslabs.com/v1/
  NEXT_PUBLIC_SUPABASE_KEY=
  NEXT_PUBLIC_SUPABASE_URL=
  ```

  Read more on [https://nextjs.org/docs/basic-features/environment-variables](https://nextjs.org/docs/basic-features/environment-variables)

- Run script for create market

  ```
  NODE_ENV=development yarn workspace market-frontend aptos:create-market
  ```

- Run dev

  ```
  yarn workspace market-frontend dev
  ```

### Backend

- Setup

  ```
  // install all the dependencies listed within package.json
  yarn workspace market-backend install

  // set up a new Prisma project
  yarn workspace market-backend prisma init
  ```

- Config `.env`

  ```
  DATABASE_URL=<YOUR SUPABASE DB URL>
  APTOS_NODE_URL=https://fullnode.devnet.aptoslabs.com/v1/
  APTOS_FAUCET_URL=https://faucet.devnet.aptoslabs.com/
  MARKET_ADDRESS=<YOUR MARKET ACCOUNT>
  ```

- DB Migration

  ```
  // create migrations from your Prisma schema, apply them to the database
  yarn workspace market-backend prisma migrate dev --name <new-file-suffix>
  ```

- Run
  ```
  yarn workspace market-backend start
  ```

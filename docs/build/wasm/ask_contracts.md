# Ask! Smart Contracts

This guide will help you set up your local environment and deploy a simple Ask! contract on our testnet, Shibuya.

---

## What is Ask!

Ask! is a framework for AssemblyScript developers to write Wasm smart contracts for `pallet-contracts`, otherwise known as the Wasm Virtual Machine. Its syntax is similar to TypeScript. The [current project](https://polkadot.polkassembly.io/post/949) is funded by Polkadot treasury, and still under active development. 

## Ask! Environment Setup

Start with executing the following command: 

```bash
git clone https://github.com/ask-lang/ask-template.git
cd ask-template
```

The command above will download a simple Ask! contract, shown below in `flipper.ts`.

```ts
/* eslint-disable @typescript-eslint/no-inferrable-types */
import { env, Pack } from "ask-lang";

@event({ id: 1 })
export class FlipEvent {
    flag: bool;

    constructor(flag: bool) {
        this.flag = flag;
    }
}

@spreadLayout
@packedLayout
export class Flipper {
    flag: bool;
    constructor(flag: bool = false) {
        this.flag = flag;
    }
}

@contract
export class Contract {
    _data: Pack<Flipper>;

    constructor() {
        this._data = instantiate<Pack<Flipper>>(new Flipper(false));
    }

    get data(): Flipper {
        return this._data.unwrap();
    }

    set data(data: Flipper) {
        this._data = new Pack(data);
    }

    @constructor()
    default(flag: bool): void {
        this.data.flag = flag;
    }

    @message({ mutates: true })
    flip(): void {
        this.data.flag = !this.data.flag;
        let event = new FlipEvent(this.data.flag);
        // @ts-ignore
        env().emitEvent(event);
    }

    @message()
    get(): bool {
        return this.data.flag;
    }
}
```

Run the command below, which will build the template contract.

```bash
# Install dependencies and Build the template contract
yarn && yarn build flipper.ts
```

The above command will generate the Wasm code and metadata file for the contract in `flipper.optimized.wasm`, and `metadata.json`, respectively.

![08](img/08a.png)

Now we will deploy this smart contract on our testnet.

Visit the [Polkadot.js apps portal](https://polkadot.js.org/apps/) and deploy the smart contract. Select Shibuya testnet and choose `metadata.json` for “json for either ABI or .contract bundle” section, or `flipper.optimized.wasm` for the “compiled contract Wasm” section.

![09](img/09a.png)

![10](img/10.png)

![11](img/11.png)

![12](img/12.png)

After following the steps above. We can confirm that the contract is deployed on Shibuya testnet.

![12](img/12.png)

That’s a wrap!
If you have any questions, please feel free to ask us in our [official discord channel](https://discord.gg/GhTvWxsF6S).

---

## Reference

- [Official documentation for ask!](https://github.com/ask-lang/ask)
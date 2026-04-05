# Context

> Execution context abstraction for meta-transaction support

## Overview

This is a verbatim port of OpenZeppelin's Context contract (v5.0.1), with only the Solidity pragma updated to `^0.8.30`. Part of the Uniteum library collection alongside [erc20](https://github.com/uniteum/erc20), [ownable](https://github.com/uniteum/ownable), and [clones](https://github.com/uniteum/clones).

## Features

- **Meta-transaction support**: Override `_msgSender()` for EIP-2771 relayer patterns
- **Minimal footprint**: Three virtual functions, no state
- **Solidity 0.8.30**: Modern Solidity compiler

## Installation

### Foundry

```bash
forge install uniteum/context
```

### Git Submodule

```bash
git submodule add https://github.com/uniteum/context lib/context
```

## Usage

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

import {Context} from "context/Context.sol";

contract MyContract is Context {
    function doSomething() external {
        address sender = _msgSender();
        // ...
    }
}
```

## What's Included

### Context.sol

- `_msgSender()` — Returns `msg.sender` (override for meta-transactions)
- `_msgData()` — Returns `msg.data`
- `_contextSuffixLength()` — Returns 0 (override for trusted forwarder suffix)

## License

MIT License — Copyright (c) 2026 Uniteum

Based on OpenZeppelin Contracts (MIT License)

## Related Libraries

- [ownable](https://github.com/uniteum/ownable) — Access control via single owner
- [erc20](https://github.com/uniteum/erc20) — ERC20 token implementation
- [clones](https://github.com/uniteum/clones) — Minimal proxy deployment (EIP-1167)

## Version

Ported from OpenZeppelin Contracts v5.0.1

Solidity: ^0.8.30

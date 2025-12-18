# Slither Audit Report: `ArtacleIndexRegistry`

**Generated:** 2025-12-18 07:16:01
**Analysis Tool:** Slither (Static Analysis)
**Scope:** Single contract analysis without external dependencies

## Executive Summary

**Contract:** `ArtacleIndexRegistry`

**Total Issues:** 12

### Issue Distribution:

- 🟡 **MEDIUM:** 3 issue(s)
- 🔵 **LOW:** 4 issue(s)
- ⚪ **INFORMATIONAL:** 5 issue(s)

## Detailed Findings

### 🟡 MEDIUM Severity (3)

#### 1. ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by IERC20(token).approve(address(permit2),tokenAmount) (contracts/hooks/ArtacleIndexRegistry.sol#362)

- **[ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by IERC20(token).approve(address(permit2),tokenAmount) (contracts/hooks/ArtacleIndexRegistry.sol#362)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

#### 2. ArtacleIndexRegistry.registerToken(address,address) (contracts/hooks/ArtacleIndexRegistry.sol#302-328) ignores return value by IArtacleIndex(token).midSwap() (contracts/hooks/ArtacleIndexRegistry.sol#311-315)

- **[ArtacleIndexRegistry.registerToken(address,address) (contracts/hooks/ArtacleIndexRegistry.sol#302-328) ignores return value by IArtacleIndex(token).midSwap() (contracts/hooks/ArtacleIndexRegistry.sol#311-315)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L302-L328`

#### 3. ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by posm.multicall{value: ethAmount}(multicallParams) (contracts/hooks/ArtacleIndexRegistry.sol#401)

- **[ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by posm.multicall{value: ethAmount}(multicallParams) (contracts/hooks/ArtacleIndexRegistry.sol#401)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

### 🔵 LOW Severity (4)

#### 1. ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._poolManager (contracts/hooks/ArtacleIndexRegistry.sol#122) lacks a zero-check on :

- **[ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._poolManager (contracts/hooks/ArtacleIndexRegistry.sol#122) lacks a zero-check on :](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `missing-zero-check`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L122`

#### 2. ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._adminFund (contracts/hooks/ArtacleIndexRegistry.sol#125) lacks a zero-check on :

- **[ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._adminFund (contracts/hooks/ArtacleIndexRegistry.sol#125) lacks a zero-check on :](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `missing-zero-check`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L125`

#### 3. ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) lacks a zero-check on :

- **[ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) lacks a zero-check on :](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `missing-zero-check`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L163`

#### 4. Reentrancy in ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406):

- **[Reentrancy in ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406):](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `reentrancy-benign`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

### ⚪ INFORMATIONAL Severity (5)

#### 1. 6 different versions of Solidity are used:

- **[6 different versions of Solidity are used:](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `pragma`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L2`

#### 2. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase

- **[Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

#### 3. Parameter ArtacleIndexRegistry.addRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#180) is not in mixedCase

- **[Parameter ArtacleIndexRegistry.addRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#180) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L180`

#### 4. Parameter ArtacleIndexRegistry.removeRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#190) is not in mixedCase

- **[Parameter ArtacleIndexRegistry.removeRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#190) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L190`

#### 5. Parameter ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) is not in mixedCase

- **[Parameter ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L163`

## Recommendations

### 🟡 Medium Priority Improvements

1. **Address MEDIUM severity issues in the next development cycle**
2. **Evaluate risk vs effort for each issue**

### ℹ️ Best Practices

1. **Regular Security Audits:** Run Slither regularly during development
2. **Code Review:** Have security-focused code reviews
3. **Testing:** Implement comprehensive unit and integration tests
4. **Documentation:** Keep security considerations documented


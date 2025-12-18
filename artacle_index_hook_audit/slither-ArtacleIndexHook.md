# Slither Audit Report: `ArtacleIndexHook`

**Generated:** 2025-12-18 07:16:01
**Analysis Tool:** Slither (Static Analysis)
**Scope:** Single contract analysis without external dependencies

## Executive Summary

**Contract:** `ArtacleIndexHook`

**Total Issues:** 13

### Issue Distribution:

- 🟠 **HIGH:** 2 issue(s)
- 🟡 **MEDIUM:** 4 issue(s)
- 🔵 **LOW:** 3 issue(s)
- ⚪ **INFORMATIONAL:** 4 issue(s)

## Detailed Findings

### 🟠 HIGH Severity (2)

#### 1. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) uses arbitrary from in transferFrom: token.safeTransferFrom(payer,address(manager),amount) (contracts/hooks/CurrencySettler.sol#38)

- **[CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) uses arbitrary from in transferFrom: token.safeTransferFrom(payer,address(manager),amount) (contracts/hooks/CurrencySettler.sol#38)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ HIGH
  - **Confidence:** High
  - **Check:** `arbitrary-send-erc20`
  - **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

#### 2. ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) sends eth to arbitrary user

- **[ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) sends eth to arbitrary user](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ HIGH
  - **Confidence:** Medium
  - **Check:** `arbitrary-send-eth`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L340-L353`

### 🟡 MEDIUM Severity (4)

#### 1. ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) uses a dangerous strict equality:

- **[ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) uses a dangerous strict equality:](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** High
  - **Check:** `incorrect-equality`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L340-L353`

#### 2. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle{value: amount}() (contracts/hooks/CurrencySettler.sol#29)

- **[CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle{value: amount}() (contracts/hooks/CurrencySettler.sol#29)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

#### 3. ArtacleIndexHook._getCurrentPrice(PoolKey) (contracts/hooks/ArtacleIndexHook.sol#359-362) ignores return value by (sqrtPriceX96,None,None,None) = poolManager.getSlot0(key.toId()) (contracts/hooks/ArtacleIndexHook.sol#360)

- **[ArtacleIndexHook._getCurrentPrice(PoolKey) (contracts/hooks/ArtacleIndexHook.sol#359-362) ignores return value by (sqrtPriceX96,None,None,None) = poolManager.getSlot0(key.toId()) (contracts/hooks/ArtacleIndexHook.sol#360)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L359-L362`

#### 4. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle() (contracts/hooks/CurrencySettler.sol#44)

- **[CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle() (contracts/hooks/CurrencySettler.sol#44)](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ⚠️ MEDIUM
  - **Confidence:** Medium
  - **Check:** `unused-return`
  - **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

### 🔵 LOW Severity (3)

#### 1. Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):

- **[Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `reentrancy-events`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L242-L288`

#### 2. Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):

- **[Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `reentrancy-events`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L242-L288`

#### 3. ArtacleIndexHook._getCurrentBuyFee(address) (contracts/hooks/ArtacleIndexHook.sol#149-173) uses timestamp for comparisons

- **[ArtacleIndexHook._getCurrentBuyFee(address) (contracts/hooks/ArtacleIndexHook.sol#149-173) uses timestamp for comparisons](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ LOW
  - **Confidence:** Medium
  - **Check:** `timestamp`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L149-L173`

### ⚪ INFORMATIONAL Severity (4)

#### 1. 7 different versions of Solidity are used:

- **[7 different versions of Solidity are used:](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `pragma`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L2`

#### 2. Variable ArtacleIndexHook.FEE_SCHEDULE (contracts/hooks/ArtacleIndexHook.sol#57-65) is not in mixedCase

- **[Variable ArtacleIndexHook.FEE_SCHEDULE (contracts/hooks/ArtacleIndexHook.sol#57-65) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L57-L65`

#### 3. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase

- **[Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `naming-convention`
  - **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

#### 4. ArtacleIndexHook (contracts/hooks/ArtacleIndexHook.sol#31-366) does not implement functions:

- **[ArtacleIndexHook (contracts/hooks/ArtacleIndexHook.sol#31-366) does not implement functions:](https://github.com/crytic/slither/wiki/Detector-Documentation)**
  - **Severity:** ℹ️ INFORMATIONAL
  - **Confidence:** High
  - **Check:** `unimplemented-functions`
  - **Location:** `contracts/hooks/ArtacleIndexHook.sol#L31-L366`

## Recommendations

### 🔴 Critical/High Priority Actions Required

1. **Address all CRITICAL and HIGH severity issues immediately**
2. **Re-run Slither analysis after fixes**
3. **Consider code review for complex fixes**

### 🟡 Medium Priority Improvements

1. **Address MEDIUM severity issues in the next development cycle**
2. **Evaluate risk vs effort for each issue**

### ℹ️ Best Practices

1. **Regular Security Audits:** Run Slither regularly during development
2. **Code Review:** Have security-focused code reviews
3. **Testing:** Implement comprehensive unit and integration tests
4. **Documentation:** Keep security considerations documented


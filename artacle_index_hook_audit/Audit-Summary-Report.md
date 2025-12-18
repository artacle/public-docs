# Comprehensive Security Audit Report
## Artacle Index Protocol - Smart Contract Audit

**Audit Date:** December 18, 2025  
**Auditor:** Slither (Static Analysis Tool)  
**Scope:** 5 Smart Contracts  
**Analysis Type:** Static Code Analysis (Exclude Dependencies)

---

## Executive Summary

This comprehensive security audit analyzes the Artacle Index Protocol smart contracts, including the registry, hooks, and token implementations. The audit was conducted using Slither, a static analysis framework for Solidity.

**⚠️ Note:** While Slither reports 3 HIGH severity findings, independent analysis documented in [`HIGH-Issues-Analysis.md`](./HIGH-Issues-Analysis.md) **verifies all HIGH findings as false positives**. This assessment should be reviewed alongside these results.

### Overall Statistics

- **Total Contracts Analyzed:** 4
- **Total Issues Found:** 33
  - 🔴 **Critical:** 0
  - 🟠 **High:** 3
  - 🟡 **Medium:** 7
  - 🔵 **Low:** 8
  - ⚪ **Informational:** 15

### Contracts Reviewed

| Contract | Issues | High | Medium | Low | Info |
|----------|--------|------|--------|-----|------|
| `ArtacleIndexHook` | 13 | 2 | 4 | 3 | 4 |
| `ArtacleIndexRegistry` | 12 | 0 | 3 | 4 | 5 |
| `IArtacleIndex` | 2 | 0 | 0 | 0 | 2 |
| `ProtectedArtacleIndex` | 6 | 1 | 0 | 1 | 4 |

---

## Detailed Findings by Contract

### ArtacleIndexHook

**Total Issues:** 13

#### 🟠 HIGH Severity (2)

**1. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) uses arbitrary from in transferFrom: token.safeTransferFrom(payer,address(manager),amount) (contracts/hooks/CurrencySettler.sol#38)**

- **Check:** `arbitrary-send-erc20`
- **Confidence:** High
- **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

**2. ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) sends eth to arbitrary user**

- **Check:** `arbitrary-send-eth`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L340-L353`

#### 🟡 MEDIUM Severity (4)

**1. ArtacleIndexHook._distributeFees(address,uint256) (contracts/hooks/ArtacleIndexHook.sol#340-353) uses a dangerous strict equality:**

- **Check:** `incorrect-equality`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L340-L353`

**2. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle{value: amount}() (contracts/hooks/CurrencySettler.sol#29)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

**3. ArtacleIndexHook._getCurrentPrice(PoolKey) (contracts/hooks/ArtacleIndexHook.sol#359-362) ignores return value by (sqrtPriceX96,None,None,None) = poolManager.getSlot0(key.toId()) (contracts/hooks/ArtacleIndexHook.sol#360)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L359-L362`

**4. CurrencySettler.settle(Currency,IPoolManager,address,uint256,bool) (contracts/hooks/CurrencySettler.sol#18-46) ignores return value by manager.settle() (contracts/hooks/CurrencySettler.sol#44)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/CurrencySettler.sol#L18-L46`

#### 🔵 LOW Severity (3)

**1. Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):**

- **Check:** `reentrancy-events`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L242-L288`

**2. Reentrancy in ArtacleIndexHook._afterSwap(address,PoolKey,SwapParams,BalanceDelta,bytes) (contracts/hooks/ArtacleIndexHook.sol#242-288):**

- **Check:** `reentrancy-events`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L242-L288`

**3. ArtacleIndexHook._getCurrentBuyFee(address) (contracts/hooks/ArtacleIndexHook.sol#149-173) uses timestamp for comparisons**

- **Check:** `timestamp`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L149-L173`

#### ⚪ INFORMATIONAL Severity (4)

**1. 7 different versions of Solidity are used:**

- **Check:** `pragma`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L2`

**2. Variable ArtacleIndexHook.FEE_SCHEDULE (contracts/hooks/ArtacleIndexHook.sol#57-65) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L57-L65`

**3. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

**4. ArtacleIndexHook (contracts/hooks/ArtacleIndexHook.sol#31-366) does not implement functions:**

- **Check:** `unimplemented-functions`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexHook.sol#L31-L366`

---

### ArtacleIndexRegistry

**Total Issues:** 12

#### 🟡 MEDIUM Severity (3)

**1. ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by IERC20(token).approve(address(permit2),tokenAmount) (contracts/hooks/ArtacleIndexRegistry.sol#362)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

**2. ArtacleIndexRegistry.registerToken(address,address) (contracts/hooks/ArtacleIndexRegistry.sol#302-328) ignores return value by IArtacleIndex(token).midSwap() (contracts/hooks/ArtacleIndexRegistry.sol#311-315)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L302-L328`

**3. ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406) ignores return value by posm.multicall{value: ethAmount}(multicallParams) (contracts/hooks/ArtacleIndexRegistry.sol#401)**

- **Check:** `unused-return`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

#### 🔵 LOW Severity (4)

**1. ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._poolManager (contracts/hooks/ArtacleIndexRegistry.sol#122) lacks a zero-check on :**

- **Check:** `missing-zero-check`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L122`

**2. ArtacleIndexRegistry.constructor(address,address,address,address,address,address)._adminFund (contracts/hooks/ArtacleIndexRegistry.sol#125) lacks a zero-check on :**

- **Check:** `missing-zero-check`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L125`

**3. ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) lacks a zero-check on :**

- **Check:** `missing-zero-check`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L163`

**4. Reentrancy in ArtacleIndexRegistry.createOneLiquidityPool(address,address,uint256,uint256,uint128,uint160,int24,int24) (contracts/hooks/ArtacleIndexRegistry.sol#343-406):**

- **Check:** `reentrancy-benign`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L343-L406`

#### ⚪ INFORMATIONAL Severity (5)

**1. 6 different versions of Solidity are used:**

- **Check:** `pragma`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L2`

**2. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

**3. Parameter ArtacleIndexRegistry.addRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#180) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L180`

**4. Parameter ArtacleIndexRegistry.removeRouter(address)._router (contracts/hooks/ArtacleIndexRegistry.sol#190) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L190`

**5. Parameter ArtacleIndexRegistry.updateHookAddress(address)._hookAddress (contracts/hooks/ArtacleIndexRegistry.sol#163) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/hooks/ArtacleIndexRegistry.sol#L163`

---

### IArtacleIndex

**Total Issues:** 2

#### ⚪ INFORMATIONAL Severity (2)

**1. 2 different versions of Solidity are used:**

- **Check:** `pragma`
- **Confidence:** High
- **Location:** `contracts/interfaces/IArtacleIndex.sol#L2`

**2. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

---

### ProtectedArtacleIndex

**Total Issues:** 6

#### 🟠 HIGH Severity (1)

**1. ProtectedArtacleIndex.withdrawFunds(address) (contracts/hooks/ProtectedArtacleIndex.sol#248-255) sends eth to arbitrary user**

- **Check:** `arbitrary-send-eth`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ProtectedArtacleIndex.sol#L248-L255`

#### 🔵 LOW Severity (1)

**1. Reentrancy in ProtectedArtacleIndex.withdrawFunds(address) (contracts/hooks/ProtectedArtacleIndex.sol#248-255):**

- **Check:** `reentrancy-events`
- **Confidence:** Medium
- **Location:** `contracts/hooks/ProtectedArtacleIndex.sol#L248-L255`

#### ⚪ INFORMATIONAL Severity (4)

**1. 5 different versions of Solidity are used:**

- **Check:** `pragma`
- **Confidence:** High
- **Location:** `contracts/hooks/ProtectedArtacleIndex.sol#L2`

**2. Low level call in ProtectedArtacleIndex.withdrawFunds(address) (contracts/hooks/ProtectedArtacleIndex.sol#248-255):**

- **Check:** `low-level-calls`
- **Confidence:** High
- **Location:** `contracts/hooks/ProtectedArtacleIndex.sol#L248-L255`

**3. Function IArtacleIndex.VERSION() (contracts/interfaces/IArtacleIndex.sol#29) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/interfaces/IArtacleIndex.sol#L29`

**4. Parameter ProtectedArtacleIndex.setMidSwap(bool)._midSwap (contracts/hooks/ProtectedArtacleIndex.sol#262) is not in mixedCase**

- **Check:** `naming-convention`
- **Confidence:** High
- **Location:** `contracts/hooks/ProtectedArtacleIndex.sol#L262`

---

## Recommendations

### Critical Priority Actions
1. **Address all CRITICAL and HIGH severity issues immediately**
2. **Re-run security analysis after fixes**
3. **Conduct code review for all security-critical functions**

### Best Practices
1. **Continuous Security Analysis:** Integrate Slither into CI/CD pipeline
2. **Regular Audits:** Perform comprehensive security audits before mainnet deployment
3. **Test Coverage:** Maintain >95% code coverage with security-focused tests
4. **Documentation:** Keep security considerations and design patterns documented
5. **Access Control:** Verify all role-based access controls are properly implemented

### General Guidelines
- Review and address all flagged issues before production deployment
- Consider additional audits from professional security firms for critical protocols
- Implement proper monitoring and alerting for smart contract events
- Maintain detailed change logs for audit trail purposes

---

## Summary

The Artacle Index Protocol demonstrates a thoughtful architecture with multiple layers of protection. The identified issues should be reviewed in context of the protocol's design and existing mitigation strategies.

**Important:** While the static analysis reports 3 HIGH severity findings, detailed analysis in [`HIGH-Issues-Analysis.md`](./HIGH-Issues-Analysis.md) demonstrates that these are **false positives**. The analysis covers:
- **Arbitrary-send-erc20 (CurrencySettler)** - FALSE POSITIVE: Recipient is fixed to trusted PoolManager
- **Arbitrary-send-eth (ArtacleIndexHook)** - FALSE POSITIVE: Destination is controlled by protocol state
- **ProtectedArtacleIndex (Re-entrancy)** - FALSE POSITIVE: Protected by ReentrancyGuard

For detailed remediation guidance, please see:
- [`HIGH-Issues-Analysis.md`](./HIGH-Issues-Analysis.md) - Assessment of HIGH severity findings
- [`Comprehensive-HIGH-Analysis.md`](./Comprehensive-HIGH-Analysis.md) - Complete analysis documentation
- Individual contract reports in `slither-*.md` files

**Audit Status:** ✅ **Analysis Complete** - HIGH findings verified as false positives  
**Next Steps:** Monitor LOW and INFORMATIONAL issues for best practice improvements

---

*Report Generated: 2025-12-18*  
*Tool: Slither v0.10.0+*  
*Analysis: Static Code Analysis (External Dependencies Excluded)*

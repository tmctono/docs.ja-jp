---
title: ICorDebugModule2::SetJMCStatus メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129471"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="d31a0-102">ICorDebugModule2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="d31a0-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="d31a0-103">この ICorDebugModule2 内のすべてのクラスのすべてのメソッドのマイコードのみ (JMC) の状態を、指定した値に設定します。ただし、逆の値に設定するのは、`pTokens` 配列内のすべてのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="d31a0-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="d31a0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d31a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d31a0-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="d31a0-106">からコードをデバッグする場合は `true` に設定します。それ以外の場合は、を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="d31a0-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="d31a0-107">[in] `pTokens` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d31a0-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="d31a0-108">から`mdToken` 値の配列。各値は、JMC 状態がに設定されるメソッドを参照します。`bIsJustMycode`。</span><span class="sxs-lookup"><span data-stu-id="d31a0-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d31a0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d31a0-109">Remarks</span></span>  
 <span data-ttu-id="d31a0-110">`pTokens` 配列に指定されている各メソッドの JMC の状態は、`bIsJustMycode` 値の逆に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d31a0-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="d31a0-111">このモジュール内の他のすべてのメソッドの状態は、`bIsJustMycode` 値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d31a0-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="d31a0-112">`SetJMCStatus` メソッドは、このモジュール内の以前のすべての JMC 設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="d31a0-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="d31a0-113">すべての関数が正常に設定されている場合、`SetJMCStatus` メソッドは S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="d31a0-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="d31a0-114">`true` としてマークされている一部の関数がデバッグ可能でない場合は、CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="d31a0-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d31a0-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="d31a0-115">Requirements</span></span>  
 <span data-ttu-id="d31a0-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d31a0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d31a0-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d31a0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d31a0-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d31a0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d31a0-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d31a0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d438123dcefb901098954845596c210e5b76cea6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764108"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="3442b-102">ICorDebugModule2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="3442b-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="3442b-103">この ICorDebugModule2 を除く、指定された値でのすべてのクラスのすべてのメソッドだけマイ コードのみ (JMC) 状態を設定、`pTokens`配列で、逆の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="3442b-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3442b-104">構文</span><span class="sxs-lookup"><span data-stu-id="3442b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3442b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3442b-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="3442b-106">[in]設定`true`コードは、デバッグ対象以外の場合に場合に、設定`false`します。</span><span class="sxs-lookup"><span data-stu-id="3442b-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="3442b-107">[in] `pTokens` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="3442b-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="3442b-108">[in]配列の`mdToken`値、その JMC ステータスに設定するメソッドを指す各!`bIsJustMycode`します。</span><span class="sxs-lookup"><span data-stu-id="3442b-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3442b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3442b-109">Remarks</span></span>  
 <span data-ttu-id="3442b-110">指定されている各メソッドの JMC 状態、`pTokens`の反対に配列が設定されている、`bIsJustMycode`値。</span><span class="sxs-lookup"><span data-stu-id="3442b-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="3442b-111">このモジュールで他のすべてのメソッドの状態に設定、`bIsJustMycode`値。</span><span class="sxs-lookup"><span data-stu-id="3442b-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="3442b-112">`SetJMCStatus`メソッドは、このモジュール内のすべての以前 JMC 設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="3442b-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="3442b-113">`SetJMCStatus`メソッドは、すべての関数が正常に設定されている場合に S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="3442b-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="3442b-114">いくつかの関数の場合は、CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT がマークされている返します`true`デバッグ可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3442b-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3442b-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="3442b-115">Requirements</span></span>  
 <span data-ttu-id="3442b-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3442b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3442b-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3442b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3442b-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3442b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3442b-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3442b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

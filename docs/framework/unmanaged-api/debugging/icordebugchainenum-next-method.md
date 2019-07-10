---
title: ICorDebugChainEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4e8b1a76bcc56424e61991d36c94c5f2dfab8aa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745607"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="e5334-102">ICorDebugChainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="e5334-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="e5334-103">現在の位置から始まり、列挙体から ICorDebugChain インスタンスの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5334-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5334-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5334-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5334-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5334-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e5334-106">[in]数`ICorDebugChain`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5334-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="e5334-107">[out]それぞれが指すポインターの配列、`ICorDebugChain`チェーンを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e5334-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e5334-108">[out]数へのポインター`ICorDebugChain`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="e5334-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="e5334-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e5334-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5334-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5334-110">Requirements</span></span>  
 <span data-ttu-id="e5334-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5334-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5334-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5334-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5334-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5334-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5334-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5334-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

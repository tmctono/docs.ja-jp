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
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989236"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="e83f3-102">ICorDebugChainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="e83f3-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="e83f3-103">現在の位置から始まり、列挙体から ICorDebugChain インスタンスの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e83f3-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e83f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="e83f3-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e83f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e83f3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e83f3-106">[in]数`ICorDebugChain`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e83f3-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="e83f3-107">[out]それぞれが指すポインターの配列、`ICorDebugChain`チェーンを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e83f3-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e83f3-108">[out]数へのポインター`ICorDebugChain`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="e83f3-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="e83f3-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e83f3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e83f3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e83f3-110">Requirements</span></span>  
 <span data-ttu-id="e83f3-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e83f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e83f3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e83f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e83f3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e83f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e83f3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e83f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

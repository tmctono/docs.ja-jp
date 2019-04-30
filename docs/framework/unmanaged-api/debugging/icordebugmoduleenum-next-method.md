---
title: ICorDebugModuleEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942481"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="377b1-102">ICorDebugModuleEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="377b1-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="377b1-103">指定された"ICorDebugModule"インスタンスの数を取得`celt`列挙体の現在位置から。</span><span class="sxs-lookup"><span data-stu-id="377b1-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="377b1-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="377b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="377b1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="377b1-106">[in]数`ICorDebugModule`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="377b1-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="377b1-107">[out]それぞれが指すポインターの配列、`ICorDebugModule`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="377b1-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="377b1-108">[out]数へのポインター`ICorDebugModule`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="377b1-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="377b1-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="377b1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377b1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="377b1-110">Requirements</span></span>  
 <span data-ttu-id="377b1-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="377b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377b1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="377b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="377b1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="377b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="377b1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377b1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="377b1-115">See also</span></span>

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
ms.openlocfilehash: d7ad4a6b25fe6d53ab0b21066345451ae7c22c16
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213323"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="3f838-102">ICorDebugModuleEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="3f838-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="3f838-103">によって指定された "のモジュール" インスタンスの数を列挙から取得します。この数は `celt` 、現在の位置から開始します。</span><span class="sxs-lookup"><span data-stu-id="3f838-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f838-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f838-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f838-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f838-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3f838-106">から`ICorDebugModule`取得するインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="3f838-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="3f838-107">入出力ポインターの配列。それぞれがオブジェクトを指し `ICorDebugModule` ます。</span><span class="sxs-lookup"><span data-stu-id="3f838-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3f838-108">入出力実際に返されたインスタンスの数へのポインター `ICorDebugModule` 。</span><span class="sxs-lookup"><span data-stu-id="3f838-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="3f838-109">が1の場合、この値は null `celt` になります。</span><span class="sxs-lookup"><span data-stu-id="3f838-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f838-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f838-110">Requirements</span></span>  
 <span data-ttu-id="3f838-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f838-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f838-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f838-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f838-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f838-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f838-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f838-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f838-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f838-115">See also</span></span>

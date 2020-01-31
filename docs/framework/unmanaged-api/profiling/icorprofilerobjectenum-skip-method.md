---
title: ICorProfilerObjectEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 096489fcdc9d604e003386501c22967b45ba6d7f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861113"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="f5c60-102">ICorProfilerObjectEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="f5c60-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="f5c60-103">指定された数の要素がスキップされるように、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="f5c60-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c60-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5c60-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5c60-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c60-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f5c60-106">からスキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="f5c60-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5c60-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f5c60-107">Remarks</span></span>  
 <span data-ttu-id="f5c60-108">この列挙子のカーソルの新しい位置は、(現在位置) + `celt` です。</span><span class="sxs-lookup"><span data-stu-id="f5c60-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c60-109">要件</span><span class="sxs-lookup"><span data-stu-id="f5c60-109">Requirements</span></span>  
 <span data-ttu-id="f5c60-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5c60-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5c60-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5c60-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5c60-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5c60-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5c60-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5c60-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c60-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5c60-114">See also</span></span>

- [<span data-ttu-id="f5c60-115">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5c60-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)

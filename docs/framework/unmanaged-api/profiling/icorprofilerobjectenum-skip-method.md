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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bcc837fede7e7db59bdf88a0b5434a7c1924335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210946"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="5374e-102">ICorProfilerObjectEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="5374e-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="5374e-103">指定した要素数がスキップされるように、現在の位置からこの列挙子のカーソルを進めます。</span><span class="sxs-lookup"><span data-stu-id="5374e-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5374e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5374e-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5374e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5374e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5374e-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="5374e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5374e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5374e-107">Remarks</span></span>  
 <span data-ttu-id="5374e-108">この列挙子のカーソルの新しい位置は: (現在の位置) +`celt`します。</span><span class="sxs-lookup"><span data-stu-id="5374e-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5374e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5374e-109">Requirements</span></span>  
 <span data-ttu-id="5374e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5374e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5374e-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5374e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5374e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5374e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5374e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5374e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5374e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5374e-114">See also</span></span>

- [<span data-ttu-id="5374e-115">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5374e-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

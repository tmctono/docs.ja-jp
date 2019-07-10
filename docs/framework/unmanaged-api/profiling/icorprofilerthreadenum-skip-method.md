---
title: ICorProfilerThreadEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c394c2b17404351bd0813ab1eb21230a1edd9de
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781100"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="46975-102">ICorProfilerThreadEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="46975-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="46975-103">指定した数の要素をスキップするため、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="46975-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46975-104">構文</span><span class="sxs-lookup"><span data-stu-id="46975-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46975-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46975-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="46975-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="46975-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46975-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="46975-107">Return Value</span></span>  
 <span data-ttu-id="46975-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="46975-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="46975-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46975-109">HRESULT</span></span>|<span data-ttu-id="46975-110">説明</span><span class="sxs-lookup"><span data-stu-id="46975-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46975-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46975-111">S_OK</span></span>|<span data-ttu-id="46975-112">`celt` 要素がスキップされました。</span><span class="sxs-lookup"><span data-stu-id="46975-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="46975-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="46975-113">S_FALSE</span></span>|<span data-ttu-id="46975-114">少ない`celt`要素がスキップされたない要素があることを示します。</span><span class="sxs-lookup"><span data-stu-id="46975-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46975-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="46975-115">Remarks</span></span>  
 <span data-ttu-id="46975-116">この列挙子のカーソルの新しい位置は (現在の位置) +`celt`します。</span><span class="sxs-lookup"><span data-stu-id="46975-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46975-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="46975-117">Requirements</span></span>  
 <span data-ttu-id="46975-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46975-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46975-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46975-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46975-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46975-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46975-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46975-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46975-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="46975-122">See also</span></span>

- [<span data-ttu-id="46975-123">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46975-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="46975-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="46975-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

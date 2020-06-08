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
ms.openlocfilehash: 4218faf1c324175424ab20305224f7f2fa51bb7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494216"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="aad63-102">ICorProfilerThreadEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="aad63-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="aad63-103">指定した数の要素をスキップするため、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="aad63-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad63-104">構文</span><span class="sxs-lookup"><span data-stu-id="aad63-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aad63-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aad63-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="aad63-106">からスキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="aad63-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aad63-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="aad63-107">Return Value</span></span>  
 <span data-ttu-id="aad63-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="aad63-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="aad63-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aad63-109">HRESULT</span></span>|<span data-ttu-id="aad63-110">説明</span><span class="sxs-lookup"><span data-stu-id="aad63-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aad63-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aad63-111">S_OK</span></span>|<span data-ttu-id="aad63-112">`celt`要素はスキップされました。</span><span class="sxs-lookup"><span data-stu-id="aad63-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="aad63-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="aad63-113">S_FALSE</span></span>|<span data-ttu-id="aad63-114">より小さい `celt` 要素がスキップされました。これは、要素がこれ以上存在しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="aad63-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aad63-115">解説</span><span class="sxs-lookup"><span data-stu-id="aad63-115">Remarks</span></span>  
 <span data-ttu-id="aad63-116">この列挙子のカーソルの新しい位置は、(現在位置) + `celt` です。</span><span class="sxs-lookup"><span data-stu-id="aad63-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aad63-117">要件</span><span class="sxs-lookup"><span data-stu-id="aad63-117">Requirements</span></span>  
 <span data-ttu-id="aad63-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad63-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aad63-119">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aad63-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aad63-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aad63-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aad63-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aad63-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad63-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="aad63-122">See also</span></span>

- [<span data-ttu-id="aad63-123">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aad63-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="aad63-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aad63-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

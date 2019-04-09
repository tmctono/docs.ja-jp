---
title: ICorProfilerFunctionEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141651"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="3590e-102">ICorProfilerFunctionEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="3590e-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="3590e-103">指定した数の要素がスキップされるように、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="3590e-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3590e-104">構文</span><span class="sxs-lookup"><span data-stu-id="3590e-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3590e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3590e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3590e-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="3590e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3590e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3590e-107">Return Value</span></span>  
 <span data-ttu-id="3590e-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="3590e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3590e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3590e-109">HRESULT</span></span>|<span data-ttu-id="3590e-110">説明</span><span class="sxs-lookup"><span data-stu-id="3590e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3590e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3590e-111">S_OK</span></span>|`celt` <span data-ttu-id="3590e-112">要素がスキップされました。</span><span class="sxs-lookup"><span data-stu-id="3590e-112">elements were skipped.</span></span>|  
|<span data-ttu-id="3590e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3590e-113">S_FALSE</span></span>|<span data-ttu-id="3590e-114">少ない`celt`要素がスキップされたない要素があることを示します。</span><span class="sxs-lookup"><span data-stu-id="3590e-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3590e-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3590e-115">Remarks</span></span>  
 <span data-ttu-id="3590e-116">この列挙子のカーソルの新しい位置は (現在の位置) +`celt`します。</span><span class="sxs-lookup"><span data-stu-id="3590e-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3590e-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3590e-117">Requirements</span></span>  
 <span data-ttu-id="3590e-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3590e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3590e-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3590e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3590e-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3590e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3590e-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3590e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3590e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3590e-122">See also</span></span>

- [<span data-ttu-id="3590e-123">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3590e-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="3590e-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3590e-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

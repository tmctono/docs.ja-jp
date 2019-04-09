---
title: ICorProfilerModuleEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99db173aa7c6064d9f635412d539cc2d4509b24a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124658"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="017cd-102">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="017cd-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="017cd-103">アプリケーションまたはプロファイラーによってロードされたモジュールのコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="017cd-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="017cd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-104">Methods</span></span>  
  
|<span data-ttu-id="017cd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-105">Method</span></span>|<span data-ttu-id="017cd-106">説明</span><span class="sxs-lookup"><span data-stu-id="017cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="017cd-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="017cd-108">この `ICorProfilerModuleEnum` インターフェイスのコピーへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="017cd-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="017cd-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="017cd-110">アプリケーションによって読み込まれたマネージド モジュールの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="017cd-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="017cd-111">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="017cd-112">オブジェクトのシーケンシャル コレクションから、列挙子の現在の位置以降にある指定した数の隣接するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="017cd-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="017cd-113">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="017cd-114">列挙子のカーソルをシーケンスの開始位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="017cd-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="017cd-115">Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="017cd-116">指定した数の要素がスキップされるように、この列挙子のカーソルの位置を進めます。</span><span class="sxs-lookup"><span data-stu-id="017cd-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="017cd-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="017cd-117">Remarks</span></span>  
 <span data-ttu-id="017cd-118">`ICorProfilerModuleEnum` インターフェイスは列挙子です。</span><span class="sxs-lookup"><span data-stu-id="017cd-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="017cd-119">このインターフェイスにより、配列の受信側は、受信側に適した速度で送信側から要素をプルできます。</span><span class="sxs-lookup"><span data-stu-id="017cd-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="017cd-120">つまり、受信側は配列要素のフローを明示的に制御できるため、大きな配列をメソッド パラメーターとして渡す場合に関連する問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="017cd-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="017cd-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="017cd-121">Requirements</span></span>  
 <span data-ttu-id="017cd-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="017cd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="017cd-123">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="017cd-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="017cd-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="017cd-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="017cd-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="017cd-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="017cd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="017cd-126">See also</span></span>

- [<span data-ttu-id="017cd-127">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="017cd-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="017cd-128">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="017cd-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="017cd-129">EnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="017cd-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)

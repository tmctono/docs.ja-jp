---
title: ICorProfilerInfo7 インターフェイス
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134860"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="035e1-102">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="035e1-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="035e1-103">[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 以降のバージョンでサポート]</span><span class="sxs-lookup"><span data-stu-id="035e1-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="035e1-104">サブクラス[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)新しくを適用するメソッドをモジュールにメタデータを定義して、メモリ内のシンボルのストリームへのアクセスを提供するを提供します。</span><span class="sxs-lookup"><span data-stu-id="035e1-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="035e1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="035e1-105">Methods</span></span>  
  
|<span data-ttu-id="035e1-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="035e1-106">Method</span></span>|<span data-ttu-id="035e1-107">説明</span><span class="sxs-lookup"><span data-stu-id="035e1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="035e1-108">ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="035e1-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="035e1-109">新しく定義されたメタデータを適用、`IMetadataEmit::Define*`メソッドが指定されたモジュールにします。</span><span class="sxs-lookup"><span data-stu-id="035e1-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="035e1-110">GetInMemorySymbolsLength メソッド</span><span class="sxs-lookup"><span data-stu-id="035e1-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="035e1-111">メモリ内のシンボルのストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="035e1-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="035e1-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="035e1-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="035e1-113">メモリ内のシンボルのストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="035e1-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="035e1-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="035e1-114">Requirements</span></span>  
 <span data-ttu-id="035e1-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="035e1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="035e1-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="035e1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="035e1-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="035e1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="035e1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="035e1-118">See also</span></span>

- [<span data-ttu-id="035e1-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="035e1-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

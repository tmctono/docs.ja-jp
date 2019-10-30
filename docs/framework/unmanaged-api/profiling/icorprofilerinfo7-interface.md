---
title: ICorProfilerInfo7 インターフェイス
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4c7e94ffa60bcfaead009e1a8baa9b54b2e8ab7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125053"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="8b67d-102">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b67d-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="8b67d-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="8b67d-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="8b67d-104">新しく定義されたメタデータをモジュールに適用し、メモリ内シンボルストリームへのアクセスを提供するメソッドを提供する[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="8b67d-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b67d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b67d-105">Methods</span></span>  
  
|<span data-ttu-id="8b67d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b67d-106">Method</span></span>|<span data-ttu-id="8b67d-107">説明</span><span class="sxs-lookup"><span data-stu-id="8b67d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b67d-108">ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="8b67d-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="8b67d-109">`IMetadataEmit::Define*` メソッドによって新たに定義されたメタデータを、指定したモジュールに適用します。</span><span class="sxs-lookup"><span data-stu-id="8b67d-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="8b67d-110">GetInMemorySymbolsLength メソッド</span><span class="sxs-lookup"><span data-stu-id="8b67d-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="8b67d-111">メモリ内シンボルストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="8b67d-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="8b67d-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="8b67d-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="8b67d-113">メモリ内シンボルストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8b67d-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b67d-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="8b67d-114">Requirements</span></span>  
 <span data-ttu-id="8b67d-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b67d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b67d-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b67d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b67d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b67d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b67d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b67d-118">See also</span></span>

- [<span data-ttu-id="8b67d-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b67d-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

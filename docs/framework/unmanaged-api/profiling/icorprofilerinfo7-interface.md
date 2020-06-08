---
title: ICorProfilerInfo7 インターフェイス
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 0e9f76717aeff27e863245faac241927e7495076
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495490"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="7f091-102">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f091-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="7f091-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="7f091-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7f091-104">新しく定義されたメタデータをモジュールに適用し、メモリ内シンボルストリームへのアクセスを提供するメソッドを提供する[ICorProfilerInfo6](icorprofilerinfo6-interface.md)のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="7f091-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f091-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7f091-105">Methods</span></span>  
  
|<span data-ttu-id="7f091-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7f091-106">Method</span></span>|<span data-ttu-id="7f091-107">説明</span><span class="sxs-lookup"><span data-stu-id="7f091-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f091-108">ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="7f091-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="7f091-109">メソッドによって新たに定義されたメタデータ `IMetadataEmit::Define*` を、指定したモジュールに適用します。</span><span class="sxs-lookup"><span data-stu-id="7f091-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="7f091-110">GetInMemorySymbolsLength メソッド</span><span class="sxs-lookup"><span data-stu-id="7f091-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="7f091-111">メモリ内シンボルストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="7f091-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="7f091-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="7f091-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="7f091-113">メモリ内シンボルストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7f091-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f091-114">要件</span><span class="sxs-lookup"><span data-stu-id="7f091-114">Requirements</span></span>  
 <span data-ttu-id="7f091-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f091-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f091-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f091-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f091-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f091-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f091-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f091-118">See also</span></span>

- [<span data-ttu-id="7f091-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f091-119">Profiling Interfaces</span></span>](profiling-interfaces.md)

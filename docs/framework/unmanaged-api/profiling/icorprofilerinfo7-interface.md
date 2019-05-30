---
title: ICorProfilerInfo7 インターフェイス
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250986"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="d6525-102">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6525-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="d6525-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="d6525-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d6525-104">サブクラス[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)新しくを適用するメソッドをモジュールにメタデータを定義して、メモリ内のシンボルのストリームへのアクセスを提供するを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6525-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6525-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6525-105">Methods</span></span>  
  
|<span data-ttu-id="d6525-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6525-106">Method</span></span>|<span data-ttu-id="d6525-107">説明</span><span class="sxs-lookup"><span data-stu-id="d6525-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6525-108">ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="d6525-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="d6525-109">新しく定義されたメタデータを適用、`IMetadataEmit::Define*`メソッドが指定されたモジュールにします。</span><span class="sxs-lookup"><span data-stu-id="d6525-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="d6525-110">GetInMemorySymbolsLength メソッド</span><span class="sxs-lookup"><span data-stu-id="d6525-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="d6525-111">メモリ内のシンボルのストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="d6525-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="d6525-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="d6525-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="d6525-113">メモリ内のシンボルのストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d6525-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6525-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6525-114">Requirements</span></span>  
 <span data-ttu-id="d6525-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6525-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6525-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6525-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6525-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6525-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6525-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6525-118">See also</span></span>

- [<span data-ttu-id="d6525-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6525-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

---
title: IMetaDataDispenser インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225977"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="3201d-102">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3201d-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="3201d-103">新しいメタデータ スコープを作成または既存のものを開くメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3201d-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3201d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3201d-104">Methods</span></span>  
  
|<span data-ttu-id="3201d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3201d-105">Method</span></span>|<span data-ttu-id="3201d-106">説明</span><span class="sxs-lookup"><span data-stu-id="3201d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3201d-107">DefineScope メソッド</span><span class="sxs-lookup"><span data-stu-id="3201d-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="3201d-108">メモリの新しいメタデータを作成するには、新しい領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="3201d-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="3201d-109">OpenScope メソッド</span><span class="sxs-lookup"><span data-stu-id="3201d-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="3201d-110">既存のディスク上ファイルを開き、そのメタデータをメモリにマップされます。</span><span class="sxs-lookup"><span data-stu-id="3201d-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="3201d-111">OpenScopeOnMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="3201d-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="3201d-112">既存のメタデータを含むメモリの領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="3201d-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="3201d-113">つまり、このメソッドは、既存のデータはメタデータとして扱われますメモリの指定された領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="3201d-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3201d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="3201d-114">Requirements</span></span>  
 <span data-ttu-id="3201d-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3201d-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3201d-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3201d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3201d-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3201d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3201d-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3201d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3201d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3201d-119">See also</span></span>

- [<span data-ttu-id="3201d-120">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3201d-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3201d-121">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3201d-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

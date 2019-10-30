---
title: ICLRMetadataLocator インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: ec92214e33cd1acda8b2702d93deba1f0fb2aaa2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111026"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="3e117-102">ICLRMetadataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e117-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="3e117-103">ターゲットプロセス内のアセンブリのメタデータを検索するために、データアクセスサービス層によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e117-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e117-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e117-104">Methods</span></span>  
  
|<span data-ttu-id="3e117-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e117-105">Method</span></span>|<span data-ttu-id="3e117-106">説明</span><span class="sxs-lookup"><span data-stu-id="3e117-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e117-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="3e117-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="3e117-108">ターゲットプロセスからイメージのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e117-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e117-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e117-109">Remarks</span></span>  
 <span data-ttu-id="3e117-110">API クライアント (つまりデバッガー) は、特定のターゲット プロセスに応じてこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e117-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="3e117-111">たとえば、ライブプロセスの実装は、メモリダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="3e117-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e117-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="3e117-112">Requirements</span></span>  
 <span data-ttu-id="3e117-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e117-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e117-114">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="3e117-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3e117-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e117-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e117-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e117-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e117-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e117-117">See also</span></span>

- [<span data-ttu-id="3e117-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e117-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

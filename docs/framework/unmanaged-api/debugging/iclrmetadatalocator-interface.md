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
ms.openlocfilehash: 642391bce99328f3700d1783054943b6a450b22b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789020"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="637b2-102">ICLRMetadataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="637b2-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="637b2-103">ターゲットプロセス内のアセンブリのメタデータを検索するために、データアクセスサービス層によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="637b2-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="637b2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="637b2-104">Methods</span></span>  
  
|<span data-ttu-id="637b2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="637b2-105">Method</span></span>|<span data-ttu-id="637b2-106">説明</span><span class="sxs-lookup"><span data-stu-id="637b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="637b2-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="637b2-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="637b2-108">ターゲットプロセスからイメージのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="637b2-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="637b2-109">コメント</span><span class="sxs-lookup"><span data-stu-id="637b2-109">Remarks</span></span>  
 <span data-ttu-id="637b2-110">API クライアント (つまりデバッガー) は、特定のターゲット プロセスに応じてこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="637b2-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="637b2-111">たとえば、ライブプロセスの実装は、メモリダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="637b2-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="637b2-112">要件</span><span class="sxs-lookup"><span data-stu-id="637b2-112">Requirements</span></span>  
 <span data-ttu-id="637b2-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="637b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="637b2-114">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="637b2-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="637b2-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="637b2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="637b2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="637b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="637b2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="637b2-117">See also</span></span>

- [<span data-ttu-id="637b2-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="637b2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

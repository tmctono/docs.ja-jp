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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddc0429a6fa921e8e6ba3c55f3efe5373bea9576
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697850"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="6dc9f-102">ICLRMetadataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dc9f-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="6dc9f-103">データ アクセス サービス層でターゲット プロセス内でアセンブリのメタデータを検索するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6dc9f-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dc9f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6dc9f-104">Methods</span></span>  
  
|<span data-ttu-id="6dc9f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6dc9f-105">Method</span></span>|<span data-ttu-id="6dc9f-106">説明</span><span class="sxs-lookup"><span data-stu-id="6dc9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dc9f-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="6dc9f-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="6dc9f-108">ターゲット プロセスからのイメージのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="6dc9f-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dc9f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6dc9f-109">Remarks</span></span>  
 <span data-ttu-id="6dc9f-110">API クライアント (つまりデバッガー) は、特定のターゲット プロセスに応じてこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dc9f-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="6dc9f-111">たとえば、ライブ プロセスの実装はメモリ ダンプの異なるになります。</span><span class="sxs-lookup"><span data-stu-id="6dc9f-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc9f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6dc9f-112">Requirements</span></span>  
 <span data-ttu-id="6dc9f-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dc9f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc9f-114">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6dc9f-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6dc9f-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dc9f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dc9f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dc9f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc9f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dc9f-117">See also</span></span>

- [<span data-ttu-id="6dc9f-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dc9f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

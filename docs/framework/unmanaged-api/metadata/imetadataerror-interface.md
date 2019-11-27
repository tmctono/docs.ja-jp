---
title: IMetaDataError インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 44ecb73375f8a408fb0a38c3a2e2913f92ec4ca4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441620"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="0118b-102">IMetaDataError インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0118b-102">IMetaDataError Interface</span></span>
<span data-ttu-id="0118b-103">メタデータのマージ中にエラーを報告するためのコールバックメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="0118b-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0118b-104">`IMetaDataError` インターフェイスは、クライアントによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0118b-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0118b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0118b-105">Methods</span></span>  
  
|<span data-ttu-id="0118b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0118b-106">Method</span></span>|<span data-ttu-id="0118b-107">説明</span><span class="sxs-lookup"><span data-stu-id="0118b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0118b-108">OnError メソッド</span><span class="sxs-lookup"><span data-stu-id="0118b-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="0118b-109">メタデータのマージ中に発生したエラーの通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="0118b-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0118b-110">要件</span><span class="sxs-lookup"><span data-stu-id="0118b-110">Requirements</span></span>  
 <span data-ttu-id="0118b-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0118b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0118b-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0118b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0118b-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0118b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0118b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0118b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0118b-115">参照</span><span class="sxs-lookup"><span data-stu-id="0118b-115">See also</span></span>

- [<span data-ttu-id="0118b-116">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0118b-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

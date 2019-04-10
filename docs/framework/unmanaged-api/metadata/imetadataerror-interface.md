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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37f1f6055ec8fa68fe804780d2893d20c978e6bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188631"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="537c5-102">IMetaDataError インターフェイス</span><span class="sxs-lookup"><span data-stu-id="537c5-102">IMetaDataError Interface</span></span>
<span data-ttu-id="537c5-103">メタデータのマージ中にエラーを報告するためのコールバック機構を提供します。</span><span class="sxs-lookup"><span data-stu-id="537c5-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="537c5-104">`IMetaDataError`クライアントによってインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="537c5-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="537c5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="537c5-105">Methods</span></span>  
  
|<span data-ttu-id="537c5-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="537c5-106">Method</span></span>|<span data-ttu-id="537c5-107">説明</span><span class="sxs-lookup"><span data-stu-id="537c5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="537c5-108">OnError メソッド</span><span class="sxs-lookup"><span data-stu-id="537c5-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="537c5-109">メタデータのマージ中に発生したエラーの通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="537c5-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="537c5-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="537c5-110">Requirements</span></span>  
 <span data-ttu-id="537c5-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="537c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537c5-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="537c5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="537c5-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="537c5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="537c5-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="537c5-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="537c5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="537c5-115">See also</span></span>

- [<span data-ttu-id="537c5-116">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="537c5-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

---
title: Init メソッド
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119367"
---
# <a name="init-method"></a><span data-ttu-id="2cd95-102">Init メソッド</span><span class="sxs-lookup"><span data-stu-id="2cd95-102">Init Method</span></span>
<span data-ttu-id="2cd95-103">実装するオブジェクトを準備、 [IALink インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="2cd95-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd95-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cd95-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cd95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cd95-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="2cd95-106">[IMetaDataDispenserEx インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)メタデータ ディスペンサーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2cd95-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="2cd95-107">[IMetaDataError インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)省略可能なエラー処理インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2cd95-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cd95-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2cd95-108">Return Value</span></span>  
 <span data-ttu-id="2cd95-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="2cd95-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cd95-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cd95-110">Requirements</span></span>  
 <span data-ttu-id="2cd95-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cd95-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd95-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cd95-112">See also</span></span>

- [<span data-ttu-id="2cd95-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cd95-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2cd95-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cd95-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2cd95-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="2cd95-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

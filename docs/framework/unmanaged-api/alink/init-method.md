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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119367"
---
# <a name="init-method"></a><span data-ttu-id="d050b-102">Init メソッド</span><span class="sxs-lookup"><span data-stu-id="d050b-102">Init Method</span></span>
<span data-ttu-id="d050b-103">実装するオブジェクトを準備、 [IALink インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="d050b-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d050b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d050b-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d050b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d050b-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="d050b-106">[IMetaDataDispenserEx インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)メタデータ ディスペンサーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d050b-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="d050b-107">[IMetaDataError インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)省略可能なエラー処理インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d050b-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d050b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d050b-108">Return Value</span></span>  
 <span data-ttu-id="d050b-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="d050b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d050b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d050b-110">Requirements</span></span>  
 <span data-ttu-id="d050b-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="d050b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d050b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d050b-112">See also</span></span>

- [<span data-ttu-id="d050b-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d050b-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d050b-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d050b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d050b-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="d050b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

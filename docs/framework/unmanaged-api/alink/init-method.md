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
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787249"
---
# <a name="init-method"></a><span data-ttu-id="b0524-102">Init メソッド</span><span class="sxs-lookup"><span data-stu-id="b0524-102">Init Method</span></span>
<span data-ttu-id="b0524-103">使用する[Ialink インターフェイス](ialink-interface.md)を実装するオブジェクトを準備します。</span><span class="sxs-lookup"><span data-stu-id="b0524-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0524-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0524-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0524-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0524-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="b0524-106">[IMetaDataDispenserEx インターフェイス](../metadata/imetadatadispenserex-interface.md)のメタデータディスペンサーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b0524-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="b0524-107">[IMetaDataError インターフェイス](../metadata/imetadataerror-interface.md)は、省略可能なエラー処理インターフェイスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="b0524-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0524-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="b0524-108">Return Value</span></span>  
 <span data-ttu-id="b0524-109">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b0524-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0524-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b0524-110">Requirements</span></span>  
 <span data-ttu-id="b0524-111">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0524-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0524-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0524-112">See also</span></span>

- [<span data-ttu-id="b0524-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0524-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b0524-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0524-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b0524-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="b0524-115">ALink API</span></span>](index.md)

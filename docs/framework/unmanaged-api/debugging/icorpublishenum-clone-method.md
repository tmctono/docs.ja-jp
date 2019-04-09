---
title: ICorPublishEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0ce1d8c0074f62d35e16465b368269e233a713b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105132"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="2d1e8-102">ICorPublishEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1e8-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="2d1e8-103">このコピーを作成します[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d1e8-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d1e8-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d1e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d1e8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="2d1e8-106">[out]アドレスへのポインター、`ICorPublishEnum`オブジェクトのこのコピーである`ICorPublishEnum`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d1e8-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1e8-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d1e8-107">Requirements</span></span>  
 <span data-ttu-id="2d1e8-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d1e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d1e8-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2d1e8-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2d1e8-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d1e8-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2d1e8-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="2d1e8-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d1e8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1e8-112">See also</span></span>

- [<span data-ttu-id="2d1e8-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d1e8-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)

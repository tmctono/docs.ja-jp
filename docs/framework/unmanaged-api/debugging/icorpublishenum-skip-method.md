---
title: ICorPublishEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98892964eb21746580e9115f86fd1be0832d9f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993500"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="fea00-102">ICorPublishEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="fea00-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="fea00-103">指定数の項目では、列挙体にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="fea00-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea00-104">構文</span><span class="sxs-lookup"><span data-stu-id="fea00-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fea00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fea00-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fea00-106">[in]カーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="fea00-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fea00-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="fea00-107">Requirements</span></span>  
 <span data-ttu-id="fea00-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea00-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fea00-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fea00-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fea00-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fea00-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fea00-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fea00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea00-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fea00-112">See also</span></span>

- [<span data-ttu-id="fea00-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fea00-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)

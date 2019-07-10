---
title: ICorPublishAppDomain::GetID メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1a557191c5649f2ed87cf4f4dfdb4167133e597
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774260"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="741c8-102">ICorPublishAppDomain::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="741c8-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="741c8-103">この一意識別子を取得します。 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="741c8-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="741c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="741c8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="741c8-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="741c8-106">[out]アプリケーション ドメインの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="741c8-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="741c8-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="741c8-107">Remarks</span></span>  
 <span data-ttu-id="741c8-108">識別子は、格納しているプロセスのスコープ内でのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="741c8-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="741c8-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="741c8-109">Requirements</span></span>  
 <span data-ttu-id="741c8-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="741c8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="741c8-111">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="741c8-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="741c8-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="741c8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="741c8-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="741c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741c8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="741c8-114">See also</span></span>

- [<span data-ttu-id="741c8-115">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="741c8-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)

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
ms.openlocfilehash: 8d6e130981693268ae5c2cd615036b84ca8ed2d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790700"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="1b4c3-102">ICorPublishAppDomain::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="1b4c3-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="1b4c3-103">この[ICorPublishAppDomain](icorpublishappdomain-interface.md)の一意の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b4c3-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b4c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b4c3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b4c3-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="1b4c3-106">入出力アプリケーションドメインの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b4c3-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b4c3-107">コメント</span><span class="sxs-lookup"><span data-stu-id="1b4c3-107">Remarks</span></span>  
 <span data-ttu-id="1b4c3-108">識別子は、含んでいるプロセスのスコープ内でのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="1b4c3-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b4c3-109">要件</span><span class="sxs-lookup"><span data-stu-id="1b4c3-109">Requirements</span></span>  
 <span data-ttu-id="1b4c3-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b4c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b4c3-111">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="1b4c3-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1b4c3-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b4c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b4c3-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b4c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4c3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b4c3-114">See also</span></span>

- [<span data-ttu-id="1b4c3-115">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b4c3-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)

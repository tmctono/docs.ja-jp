---
title: ICorPublishAppDomainEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 0553d8b07e3a16dc31474b5470ba2dd8ba365cb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140504"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="2ea58-102">ICorPublishAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2ea58-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="2ea58-103">現在プロセスに存在する、指定した数のアプリケーションドメインを、現在の位置から取得します。</span><span class="sxs-lookup"><span data-stu-id="2ea58-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea58-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ea58-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ea58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ea58-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2ea58-106">から取得する要素の数。</span><span class="sxs-lookup"><span data-stu-id="2ea58-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="2ea58-107">入出力取得された[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)オブジェクトの配列へのポインター。各オブジェクトは、アプリケーションドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="2ea58-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2ea58-108">入出力実際に返されたアプリケーションドメインの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ea58-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="2ea58-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="2ea58-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ea58-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="2ea58-110">Requirements</span></span>  
 <span data-ttu-id="2ea58-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea58-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ea58-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="2ea58-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2ea58-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ea58-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ea58-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ea58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea58-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ea58-115">See also</span></span>

- [<span data-ttu-id="2ea58-116">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ea58-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36d48c3747c2d74f4c7f47268219283b07c9a39
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500196"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="7d3c4-102">ICorPublishAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="7d3c4-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="7d3c4-103">現在の位置から、プロセス内には、現在存在しているアプリケーション ドメインの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d3c4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d3c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d3c4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7d3c4-106">[in]取得する要素の数。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="7d3c4-107">[out]配列へのポインターの取得[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)アプリケーション ドメインを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7d3c4-108">[out]アプリケーション ドメインの数へのポインターが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="7d3c4-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d3c4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d3c4-110">Requirements</span></span>  
 <span data-ttu-id="7d3c4-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d3c4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d3c4-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7d3c4-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7d3c4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d3c4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d3c4-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d3c4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3c4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d3c4-115">See also</span></span>
- [<span data-ttu-id="7d3c4-116">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d3c4-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

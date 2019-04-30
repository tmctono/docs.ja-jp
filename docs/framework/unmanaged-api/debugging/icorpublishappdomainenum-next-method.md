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
ms.openlocfilehash: c14d364320c82f061ef606a402563dacfce28139
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986649"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="cd1e2-102">ICorPublishAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="cd1e2-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="cd1e2-103">現在の位置から、プロセス内には、現在存在しているアプリケーション ドメインの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd1e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd1e2-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd1e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd1e2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cd1e2-106">[in]取得する要素の数。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="cd1e2-107">[out]配列へのポインターの取得[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)アプリケーション ドメインを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cd1e2-108">[out]アプリケーション ドメインの数へのポインターが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="cd1e2-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd1e2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd1e2-110">Requirements</span></span>  
 <span data-ttu-id="cd1e2-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd1e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd1e2-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cd1e2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cd1e2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd1e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd1e2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd1e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1e2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd1e2-115">See also</span></span>

- [<span data-ttu-id="cd1e2-116">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd1e2-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

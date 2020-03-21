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
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178395"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="90c2f-102">ICorPublishAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="90c2f-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="90c2f-103">現在の位置から開始して、プロセスに現在存在するアプリケーション ドメインの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="90c2f-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="90c2f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90c2f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="90c2f-106">[in]取得する要素の数。</span><span class="sxs-lookup"><span data-stu-id="90c2f-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="90c2f-107">[アウト]取得した[ICorPublishAppDomain](icorpublishappdomain-interface.md)オブジェクトの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="90c2f-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="90c2f-108">[アウト]実際に返されるアプリケーション ドメインの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="90c2f-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="90c2f-109">この値は null`celt`の場合は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90c2f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c2f-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="90c2f-110">Requirements</span></span>  
 <span data-ttu-id="90c2f-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c2f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c2f-112">**ヘッダー:** コルパブ.idl,コルパブ.h</span><span class="sxs-lookup"><span data-stu-id="90c2f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="90c2f-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c2f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c2f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c2f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="90c2f-115">See also</span></span>

- [<span data-ttu-id="90c2f-116">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90c2f-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)

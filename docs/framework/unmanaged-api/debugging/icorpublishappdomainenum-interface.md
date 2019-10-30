---
title: ICorPublishAppDomainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: cbe2aa48a8b67b0b6e88f7b5267bc70848fe3cec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140328"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="de765-102">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de765-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="de765-103">プロセス内に現在存在する[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)オブジェクトのコレクションを走査するメソッドを提供する[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)インターフェイスのサブクラス。</span><span class="sxs-lookup"><span data-stu-id="de765-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de765-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="de765-104">Methods</span></span>  
  
|<span data-ttu-id="de765-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="de765-105">Method</span></span>|<span data-ttu-id="de765-106">説明</span><span class="sxs-lookup"><span data-stu-id="de765-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de765-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="de765-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="de765-108">現在の位置から開始して、指定した数の `ICorPublishAppDomain` インスタンスをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="de765-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de765-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="de765-109">Remarks</span></span>  
 <span data-ttu-id="de765-110">`ICorPublishAppDomainEnum` インターフェイスは、抽象インターフェイス[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)のメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="de765-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de765-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="de765-111">Requirements</span></span>  
 <span data-ttu-id="de765-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de765-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de765-113">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="de765-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="de765-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de765-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de765-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de765-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de765-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="de765-116">See also</span></span>

- [<span data-ttu-id="de765-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de765-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="de765-118">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="de765-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)

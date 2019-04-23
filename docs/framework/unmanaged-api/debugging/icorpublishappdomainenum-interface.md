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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090050"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="ab4d8-102">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab4d8-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="ab4d8-103">サブクラスの[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)のコレクションを走査するメソッドを提供するインターフェイス[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)プロセス内に現在存在するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ab4d8-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab4d8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab4d8-104">Methods</span></span>  
  
|<span data-ttu-id="ab4d8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab4d8-105">Method</span></span>|<span data-ttu-id="ab4d8-106">説明</span><span class="sxs-lookup"><span data-stu-id="ab4d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab4d8-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="ab4d8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="ab4d8-108">指定した数を取得`ICorPublishAppDomain`コレクションの現在の位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="ab4d8-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab4d8-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab4d8-109">Remarks</span></span>  
 <span data-ttu-id="ab4d8-110">`ICorPublishAppDomainEnum`インターフェイス、抽象インターフェイスのメソッドを実装[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab4d8-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab4d8-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab4d8-111">Requirements</span></span>  
 <span data-ttu-id="ab4d8-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab4d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab4d8-113">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ab4d8-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ab4d8-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab4d8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab4d8-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab4d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4d8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab4d8-116">See also</span></span>

- [<span data-ttu-id="ab4d8-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab4d8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ab4d8-118">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="ab4d8-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)

---
title: ICorPublishProcessEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103414"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="07332-102">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07332-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="07332-103">[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクトのコレクションを走査するメソッドを提供する[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)インターフェイスのサブクラス。</span><span class="sxs-lookup"><span data-stu-id="07332-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07332-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="07332-104">Methods</span></span>  
  
|<span data-ttu-id="07332-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="07332-105">Method</span></span>|<span data-ttu-id="07332-106">説明</span><span class="sxs-lookup"><span data-stu-id="07332-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07332-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="07332-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="07332-108">現在の位置から開始して、指定した数の `ICorPublishProcess` インスタンスをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="07332-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07332-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="07332-109">Remarks</span></span>  
 <span data-ttu-id="07332-110">`ICorPublishProcessEnum` インターフェイスは、抽象インターフェイス[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)のメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="07332-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="07332-111">`ICorPublishProcessEnum` インスタンスは、 [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)メソッドによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="07332-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="07332-112">`ICorPublishProcess` オブジェクトのコレクションの走査は、`ICorPublishProcessEnum` インスタンスの作成時に指定されたフィルター条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="07332-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07332-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="07332-113">Requirements</span></span>  
 <span data-ttu-id="07332-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07332-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07332-115">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="07332-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="07332-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07332-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07332-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07332-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07332-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="07332-118">See also</span></span>

- [<span data-ttu-id="07332-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07332-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="07332-120">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="07332-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)

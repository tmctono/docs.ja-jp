---
title: ICorPublishEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160136"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="f1941-102">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1941-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="f1941-103">プロセスとアプリケーション ドメインに関する情報の発行で使用される列挙子の抽象基底インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f1941-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1941-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-104">Methods</span></span>  
  
|<span data-ttu-id="f1941-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-105">Method</span></span>|<span data-ttu-id="f1941-106">説明</span><span class="sxs-lookup"><span data-stu-id="f1941-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1941-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="f1941-108">このコピーを作成します`ICorPublishEnum`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1941-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="f1941-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="f1941-110">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1941-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="f1941-111">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="f1941-112">列挙体の先頭のカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="f1941-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="f1941-113">Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="f1941-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="f1941-114">指定数の項目では、列挙体にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="f1941-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1941-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1941-115">Remarks</span></span>  
 <span data-ttu-id="f1941-116">次の列挙子から派生して`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="f1941-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="f1941-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="f1941-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="f1941-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f1941-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="f1941-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1941-119">Requirements</span></span>  
 <span data-ttu-id="f1941-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1941-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1941-121">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f1941-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f1941-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1941-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f1941-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f1941-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1941-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1941-124">See also</span></span>

- [<span data-ttu-id="f1941-125">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="f1941-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="f1941-126">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1941-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

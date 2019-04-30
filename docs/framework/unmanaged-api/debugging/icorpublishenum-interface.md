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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993539"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="9a8af-102">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a8af-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="9a8af-103">プロセスとアプリケーション ドメインに関する情報の発行で使用される列挙子の抽象基底インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="9a8af-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a8af-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-104">Methods</span></span>  
  
|<span data-ttu-id="9a8af-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-105">Method</span></span>|<span data-ttu-id="9a8af-106">説明</span><span class="sxs-lookup"><span data-stu-id="9a8af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a8af-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="9a8af-108">このコピーを作成します`ICorPublishEnum`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9a8af-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="9a8af-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="9a8af-110">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a8af-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="9a8af-111">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="9a8af-112">列挙体の先頭のカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a8af-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="9a8af-113">Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="9a8af-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="9a8af-114">指定数の項目では、列挙体にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a8af-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a8af-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a8af-115">Remarks</span></span>  
 <span data-ttu-id="9a8af-116">次の列挙子から派生して`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="9a8af-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="9a8af-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="9a8af-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="9a8af-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="9a8af-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="9a8af-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a8af-119">Requirements</span></span>  
 <span data-ttu-id="9a8af-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a8af-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8af-121">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="9a8af-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9a8af-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8af-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8af-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8af-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8af-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a8af-124">See also</span></span>

- [<span data-ttu-id="9a8af-125">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="9a8af-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="9a8af-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a8af-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

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
ms.openlocfilehash: a48e20413f466e25a9145e9dbf1ba93d90155770
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397038"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="f640c-102">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f640c-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="f640c-103">プロセス内に現在存在する[ICorPublishAppDomain](icorpublishappdomain-interface.md)オブジェクトのコレクションを走査するメソッドを提供する[ICorPublishEnum](icorpublishenum-interface.md)インターフェイスのサブクラス。</span><span class="sxs-lookup"><span data-stu-id="f640c-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f640c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f640c-104">Methods</span></span>  
  
|<span data-ttu-id="f640c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f640c-105">Method</span></span>|<span data-ttu-id="f640c-106">説明</span><span class="sxs-lookup"><span data-stu-id="f640c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f640c-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f640c-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="f640c-108">現在の位置から開始して、指定した数の `ICorPublishAppDomain` インスタンスをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="f640c-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f640c-109">解説</span><span class="sxs-lookup"><span data-stu-id="f640c-109">Remarks</span></span>  
 <span data-ttu-id="f640c-110">インターフェイスは、 `ICorPublishAppDomainEnum` 抽象インターフェイス[ICorPublishEnum](icorpublishenum-interface.md)のメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="f640c-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f640c-111">要件</span><span class="sxs-lookup"><span data-stu-id="f640c-111">Requirements</span></span>  
 <span data-ttu-id="f640c-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f640c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f640c-113">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="f640c-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f640c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f640c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f640c-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f640c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f640c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f640c-116">See also</span></span>

- [<span data-ttu-id="f640c-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f640c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f640c-118">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="f640c-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)

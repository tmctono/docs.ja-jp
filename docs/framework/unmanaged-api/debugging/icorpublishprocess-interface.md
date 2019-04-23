---
title: ICorPublishProcess インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182963"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="1778c-102">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1778c-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="1778c-103">表示するプロセスについての情報にアクセスするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1778c-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1778c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-104">Methods</span></span>  
  
|<span data-ttu-id="1778c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-105">Method</span></span>|<span data-ttu-id="1778c-106">説明</span><span class="sxs-lookup"><span data-stu-id="1778c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1778c-107">EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="1778c-108">取得、 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)これによって参照されるプロセス内のアプリケーション ドメインを含むインスタンス`ICorPublishProcess`します。</span><span class="sxs-lookup"><span data-stu-id="1778c-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="1778c-109">GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="1778c-110">これによって参照されるプロセスの実行可能ファイルの完全なパスを取得`ICorPublishProcess`します。</span><span class="sxs-lookup"><span data-stu-id="1778c-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="1778c-111">GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="1778c-112">これによって参照されるプロセスのオペレーティング システムの識別子を取得`ICorPublishProcess`します。</span><span class="sxs-lookup"><span data-stu-id="1778c-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="1778c-113">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="1778c-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="1778c-114">これによって、プロセスが参照されるかどうかを示す値を取得します`ICorPublishProcess`マネージ コードを実行することがわかっています。</span><span class="sxs-lookup"><span data-stu-id="1778c-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1778c-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="1778c-115">Requirements</span></span>  
 <span data-ttu-id="1778c-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1778c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1778c-117">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1778c-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1778c-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1778c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1778c-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1778c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1778c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1778c-120">See also</span></span>

- [<span data-ttu-id="1778c-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1778c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1778c-122">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="1778c-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)

---
title: CorpubPublish コクラス
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05d9eef36885aee05d88f7da994c8b168c3221b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130534"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="33473-102">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="33473-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="33473-103">アプリケーション ドメインとプロセスに関する情報を発行するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="33473-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33473-104">構文</span><span class="sxs-lookup"><span data-stu-id="33473-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="33473-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-105">Interfaces</span></span>  
  
|<span data-ttu-id="33473-106">Interface</span><span class="sxs-lookup"><span data-stu-id="33473-106">Interface</span></span>|<span data-ttu-id="33473-107">説明</span><span class="sxs-lookup"><span data-stu-id="33473-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="33473-108">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="33473-109">これらのプロセスでプロセスとアプリケーション ドメインに関する情報を公開するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="33473-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="33473-110">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="33473-111">表していると、プロセス内のアプリケーション ドメインに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="33473-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="33473-112">ICorPublishAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="33473-113">現在、プロセス内に存在するアプリケーション ドメインのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="33473-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="33473-114">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="33473-115">コンピューターで実行されているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="33473-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="33473-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33473-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="33473-117">コンピューターで実行されているプロセスのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="33473-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33473-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="33473-118">Remarks</span></span>  
 <span data-ttu-id="33473-119">発行の一般的なシナリオでは、開発者は、アプリケーション ドメイン内のコンピューターで実行されているマネージ コードをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33473-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="33473-120">ホスティング環境では、プロセス内で 1 つ以上のアプリケーション ドメインが実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33473-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="33473-121">開発者は、グラフィカル ユーザー インターフェイスまたはその他の手段を使用して、すべてのコンピューターで実行されているプロセスの一覧を表示して、特定のプロセスを選択したいです。</span><span class="sxs-lookup"><span data-stu-id="33473-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="33473-122">一覧には、すべてのマネージ コードを実行しているプロセス内でアプリケーション ドメインを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="33473-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="33473-123">開発者は特定のアプリケーション ドメインを識別し、そのドメインにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="33473-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33473-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="33473-124">Requirements</span></span>  
 <span data-ttu-id="33473-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33473-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33473-126">**ヘッダー:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="33473-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="33473-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33473-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="33473-128">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="33473-128">.NET Framework Versions:</span></span>**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33473-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="33473-129">See also</span></span>

- [<span data-ttu-id="33473-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="33473-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

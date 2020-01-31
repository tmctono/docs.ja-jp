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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790539"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="384cb-102">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="384cb-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="384cb-103">プロセスについて表示される情報にアクセスするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="384cb-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="384cb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-104">Methods</span></span>  
  
|<span data-ttu-id="384cb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-105">Method</span></span>|<span data-ttu-id="384cb-106">説明</span><span class="sxs-lookup"><span data-stu-id="384cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="384cb-107">EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="384cb-108">この `ICorPublishProcess`によって参照されるプロセス内のアプリケーションドメインを含む[ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="384cb-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="384cb-109">GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="384cb-110">この `ICorPublishProcess`によって参照されるプロセスの実行可能ファイルの完全パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="384cb-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="384cb-111">GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="384cb-112">この `ICorPublishProcess`によって参照されるプロセスのオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="384cb-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="384cb-113">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="384cb-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="384cb-114">この `ICorPublishProcess` によって参照されるプロセスがマネージコードを実行していることがわかっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="384cb-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="384cb-115">要件</span><span class="sxs-lookup"><span data-stu-id="384cb-115">Requirements</span></span>  
 <span data-ttu-id="384cb-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="384cb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384cb-117">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="384cb-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="384cb-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="384cb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="384cb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384cb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384cb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="384cb-120">See also</span></span>

- [<span data-ttu-id="384cb-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="384cb-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="384cb-122">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="384cb-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)

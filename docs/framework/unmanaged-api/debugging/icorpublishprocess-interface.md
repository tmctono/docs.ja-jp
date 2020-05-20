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
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421086"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="fc384-102">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc384-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="fc384-103">プロセスについて表示される情報にアクセスするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="fc384-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc384-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-104">Methods</span></span>  
  
|<span data-ttu-id="fc384-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-105">Method</span></span>|<span data-ttu-id="fc384-106">説明</span><span class="sxs-lookup"><span data-stu-id="fc384-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc384-107">EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="fc384-108">このによって参照されるプロセス内のアプリケーションドメインを格納している[ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)インスタンスを取得し `ICorPublishProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="fc384-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="fc384-109">GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="fc384-110">このによって参照されるプロセスの実行可能ファイルの完全パスを取得し `ICorPublishProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="fc384-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="fc384-111">GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="fc384-112">このによって参照されるプロセスのオペレーティングシステム識別子を取得し `ICorPublishProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="fc384-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="fc384-113">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="fc384-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="fc384-114">このによって参照されるプロセス `ICorPublishProcess` がマネージコードを実行していることがわかっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc384-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc384-115">要件</span><span class="sxs-lookup"><span data-stu-id="fc384-115">Requirements</span></span>  
 <span data-ttu-id="fc384-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc384-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc384-117">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="fc384-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fc384-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc384-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc384-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc384-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc384-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc384-120">See also</span></span>

- [<span data-ttu-id="fc384-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc384-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc384-122">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="fc384-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)

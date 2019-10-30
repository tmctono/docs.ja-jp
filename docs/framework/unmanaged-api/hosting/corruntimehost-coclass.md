---
title: CorRuntimeHost コクラス
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136904"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="2d216-102">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="2d216-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="2d216-103">共通言語ランタイムによって実行されるアプリケーションを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d216-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d216-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2d216-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d216-105">Interfaces</span></span>  
  
|<span data-ttu-id="2d216-106">Interface</span><span class="sxs-lookup"><span data-stu-id="2d216-106">Interface</span></span>|<span data-ttu-id="2d216-107">説明</span><span class="sxs-lookup"><span data-stu-id="2d216-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2d216-108">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d216-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="2d216-109">共通言語ランタイム (CLR: common language runtime) を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="2d216-110">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d216-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="2d216-111">ホストが共通言語ランタイムを明示的に開始または停止したり、アプリケーションドメインを作成および構成したり、既定のドメインにアクセスしたり、プロセスで実行されているすべてのドメインを列挙したりできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="2d216-112">IDebuggerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d216-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="2d216-113">デバッグサービスの状態に関する情報を取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="2d216-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d216-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="2d216-115">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="2d216-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="2d216-116">"IValidator"</span></span>|<span data-ttu-id="2d216-117">ポータブル実行可能イメージを検証し、検証エラーの詳細なレポートを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d216-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d216-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="2d216-118">Requirements</span></span>  
 <span data-ttu-id="2d216-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d216-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d216-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2d216-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2d216-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2d216-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d216-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d216-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d216-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d216-123">See also</span></span>

- [<span data-ttu-id="2d216-124">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="2d216-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)

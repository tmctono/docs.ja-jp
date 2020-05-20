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
ms.openlocfilehash: fe378307ce2bda6e1a267e46433ead70a0e2299e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616521"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="2317f-102">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="2317f-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="2317f-103">共通言語ランタイムによって実行されるアプリケーションを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2317f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2317f-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2317f-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-105">Interfaces</span></span>  
  
|<span data-ttu-id="2317f-106">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-106">Interface</span></span>|<span data-ttu-id="2317f-107">説明</span><span class="sxs-lookup"><span data-stu-id="2317f-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2317f-108">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="2317f-109">共通言語ランタイム (CLR: common language runtime) を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="2317f-110">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="2317f-111">ホストが共通言語ランタイムを明示的に開始または停止したり、アプリケーションドメインを作成および構成したり、既定のドメインにアクセスしたり、プロセスで実行されているすべてのドメインを列挙したりできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="2317f-112">IDebuggerInfo Iインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="2317f-113">デバッグサービスの状態に関する情報を取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="2317f-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2317f-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="2317f-115">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="2317f-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="2317f-116">"IValidator"</span></span>|<span data-ttu-id="2317f-117">ポータブル実行可能イメージを検証し、検証エラーの詳細なレポートを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2317f-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2317f-118">要件</span><span class="sxs-lookup"><span data-stu-id="2317f-118">Requirements</span></span>  
 <span data-ttu-id="2317f-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2317f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2317f-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2317f-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2317f-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2317f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2317f-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2317f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2317f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2317f-123">See also</span></span>

- [<span data-ttu-id="2317f-124">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="2317f-124">Hosting Coclasses</span></span>](hosting-coclasses.md)

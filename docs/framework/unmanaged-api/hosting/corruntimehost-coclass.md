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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218564"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="36837-102">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="36837-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="36837-103">共通言語ランタイムで実行されているアプリケーションを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36837-104">構文</span><span class="sxs-lookup"><span data-stu-id="36837-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="36837-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36837-105">Interfaces</span></span>  
  
|<span data-ttu-id="36837-106">Interface</span><span class="sxs-lookup"><span data-stu-id="36837-106">Interface</span></span>|<span data-ttu-id="36837-107">説明</span><span class="sxs-lookup"><span data-stu-id="36837-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="36837-108">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36837-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="36837-109">共通言語ランタイム (CLR) を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="36837-110">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36837-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="36837-111">ホストが起動し、作成して既定のドメインにアクセスして、プロセスで実行されているすべてのドメインを列挙するために、アプリケーション ドメインを構成する共通言語ランタイムを明示的に停止できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="36837-112">IDebuggerInfo Iインターフェイス</span><span class="sxs-lookup"><span data-stu-id="36837-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="36837-113">デバッグ サービスの状態に関する情報を取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="36837-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36837-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="36837-115">ガベージ コレクション システムに関する情報を取得するため、ガベージ コレクションの一部の側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="36837-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="36837-116">"IValidator"</span></span>|<span data-ttu-id="36837-117">ポータブル実行可能イメージの検証と検証エラーの詳細なレポートのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="36837-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36837-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="36837-118">Requirements</span></span>  
 <span data-ttu-id="36837-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36837-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36837-120">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="36837-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="36837-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="36837-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="36837-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="36837-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36837-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="36837-123">See also</span></span>

- [<span data-ttu-id="36837-124">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="36837-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)

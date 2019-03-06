---
title: ICorConfiguration::SetDebuggerThreadControl メソッド
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cecbbd7509fcd4f79aeb6e2711e8b7604c2f3a9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489692"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="c1b9e-102">ICorConfiguration::SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="c1b9e-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="c1b9e-103">デバッグ サービスが共通言語ランタイム (CLR) スレッドがブロックまたはブロック解除されたデバッグときに呼び出すコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c1b9e-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b9e-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1b9e-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1b9e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1b9e-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="c1b9e-106">[in]ポインター、 [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)ブロックおよびブロック解除スレッドのデバッグ サービスでのホストに通知するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1b9e-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1b9e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1b9e-107">Requirements</span></span>  
 <span data-ttu-id="c1b9e-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b9e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1b9e-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1b9e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1b9e-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c1b9e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1b9e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1b9e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b9e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1b9e-112">See also</span></span>
- [<span data-ttu-id="c1b9e-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1b9e-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)

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
ms.openlocfilehash: ebbc076f52c661a394eff51954fceefe8e439ded
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779887"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="9f19f-102">ICorConfiguration::SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="9f19f-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="9f19f-103">デバッグ サービスが共通言語ランタイム (CLR) スレッドがブロックまたはブロック解除されたデバッグときに呼び出すコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="9f19f-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f19f-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f19f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f19f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f19f-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="9f19f-106">[in]ポインター、 [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)ブロックおよびブロック解除スレッドのデバッグ サービスでのホストに通知するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f19f-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f19f-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f19f-107">Requirements</span></span>  
 <span data-ttu-id="9f19f-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f19f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f19f-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f19f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f19f-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9f19f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f19f-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f19f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f19f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f19f-112">See also</span></span>

- [<span data-ttu-id="9f19f-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f19f-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)

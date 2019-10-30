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
ms.openlocfilehash: 0f6a369691ab2e4e9fd2e5d9731fb1dc0a42ba11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127798"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="f05ec-102">ICorConfiguration::SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="f05ec-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="f05ec-103">共通言語ランタイム (CLR) スレッドがブロックされ、デバッグのためにブロック解除されると、デバッグサービスが呼び出すコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="f05ec-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f05ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="f05ec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f05ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f05ec-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="f05ec-106">からデバッグサービスによるスレッドのブロックおよびブロック解除についてホストに通知する[Iデバッガ Threadcontrol](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f05ec-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f05ec-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="f05ec-107">Requirements</span></span>  
 <span data-ttu-id="f05ec-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f05ec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f05ec-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f05ec-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f05ec-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f05ec-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f05ec-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f05ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05ec-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f05ec-112">See also</span></span>

- [<span data-ttu-id="f05ec-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f05ec-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)

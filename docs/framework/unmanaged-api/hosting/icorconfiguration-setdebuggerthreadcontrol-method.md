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
ms.openlocfilehash: d02b834b22ba7897e4939de88bc3c61c62ac2b0e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762410"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="15b3f-102">ICorConfiguration::SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="15b3f-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="15b3f-103">共通言語ランタイム (CLR) スレッドがブロックされ、デバッグのためにブロック解除されると、デバッグサービスが呼び出すコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="15b3f-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="15b3f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15b3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15b3f-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="15b3f-106">からデバッグサービスによるスレッドのブロックおよびブロック解除についてホストに通知する[Iデバッガ Threadcontrol](idebuggerthreadcontrol-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="15b3f-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b3f-107">要件</span><span class="sxs-lookup"><span data-stu-id="15b3f-107">Requirements</span></span>  
 <span data-ttu-id="15b3f-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15b3f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b3f-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="15b3f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15b3f-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="15b3f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15b3f-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b3f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b3f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="15b3f-112">See also</span></span>

- [<span data-ttu-id="15b3f-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15b3f-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)

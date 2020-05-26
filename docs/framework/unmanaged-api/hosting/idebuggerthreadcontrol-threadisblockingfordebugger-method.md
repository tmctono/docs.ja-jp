---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: f7cdc3fe9d52db56d0280bc602d3a9f2f54e8246
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805252"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="f1ddc-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="f1ddc-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="f1ddc-103">このコールバックを送信しているスレッドがデバッグサービス内でブロックされようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="f1ddc-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ddc-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1ddc-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="f1ddc-105">解説</span><span class="sxs-lookup"><span data-stu-id="f1ddc-105">Remarks</span></span>  
 <span data-ttu-id="f1ddc-106">`ThreadIsBlockingForDebugger`メソッドは常にランタイムスレッドで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1ddc-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="f1ddc-107">メソッドは、 `ThreadIsBlockingForDebugger` スレッドがブロックされている間に、ホストに別のアクションを実行する機会を与えます。</span><span class="sxs-lookup"><span data-stu-id="f1ddc-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ddc-108">要件</span><span class="sxs-lookup"><span data-stu-id="f1ddc-108">Requirements</span></span>  
 <span data-ttu-id="f1ddc-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ddc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ddc-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1ddc-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1ddc-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f1ddc-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1ddc-112">**.Net Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ddc-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ddc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1ddc-113">See also</span></span>

- [<span data-ttu-id="f1ddc-114">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1ddc-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)

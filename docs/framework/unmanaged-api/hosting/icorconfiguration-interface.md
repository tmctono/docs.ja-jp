---
title: ICorConfiguration インターフェイス
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762431"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="2f28e-102">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f28e-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="2f28e-103">共通言語ランタイム (CLR: common language runtime) を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f28e-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f28e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-104">Methods</span></span>  
  
|<span data-ttu-id="2f28e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-105">Method</span></span>|<span data-ttu-id="2f28e-106">説明</span><span class="sxs-lookup"><span data-stu-id="2f28e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f28e-107">AddDebuggerSpecialThread メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="2f28e-108">デバッグサービスに対して、マネージまたはアンマネージのデバッグシナリオでデバッガーがアプリケーションを停止している間に、特定のスレッドの実行を継続できるようにする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2f28e-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="2f28e-109">SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="2f28e-110">CLR スレッドがデバッグのためにブロックおよびブロック解除されるため、デバッグサービスが呼び出すコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f28e-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="2f28e-111">SetGCHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="2f28e-112">仮想メモリの制限を変更するようにホストに要求するために、ガベージコレクターによって使用されるコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f28e-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="2f28e-113">SetGCThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2f28e-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="2f28e-114">ガベージコレクションに対してブロックされる非ランタイムタスクのスレッドをスケジュールするためのコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f28e-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f28e-115">要件</span><span class="sxs-lookup"><span data-stu-id="2f28e-115">Requirements</span></span>  
 <span data-ttu-id="2f28e-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f28e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f28e-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2f28e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f28e-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2f28e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f28e-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f28e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f28e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f28e-120">See also</span></span>

- [<span data-ttu-id="2f28e-121">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f28e-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2f28e-122">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="2f28e-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)

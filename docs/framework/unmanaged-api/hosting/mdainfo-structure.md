---
title: MDAInfo 構造体
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123259"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="83ea2-102">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="83ea2-102">MDAInfo Structure</span></span>
<span data-ttu-id="83ea2-103">マネージデバッグアシスタント (MDA) の作成をトリガーする `Event_MDAFired` イベントについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ea2-104">構文</span><span class="sxs-lookup"><span data-stu-id="83ea2-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="83ea2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="83ea2-105">Members</span></span>  
  
|<span data-ttu-id="83ea2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="83ea2-106">Member</span></span>|<span data-ttu-id="83ea2-107">説明</span><span class="sxs-lookup"><span data-stu-id="83ea2-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="83ea2-108">現在の MDA のタイトル。</span><span class="sxs-lookup"><span data-stu-id="83ea2-108">The title of the current MDA.</span></span> <span data-ttu-id="83ea2-109">タイトルには、`Event_MDAFired` イベントをトリガーしたエラーの種類が示されます。</span><span class="sxs-lookup"><span data-stu-id="83ea2-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="83ea2-110">現在の MDA によって提供される出力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="83ea2-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ea2-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="83ea2-111">Remarks</span></span>  
 <span data-ttu-id="83ea2-112">マネージデバッグアシスタント (Mda) は、共通言語ランタイム (CLR) と連携して動作し、ランタイム実行エンジンで無効な条件を特定したり、の状態に関する追加情報をダンプしたりするなどのタスクを実行します。双発.</span><span class="sxs-lookup"><span data-stu-id="83ea2-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="83ea2-113">Mda は、トラップが困難なイベントに関する XML メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="83ea2-114">これらは、マネージコードとアンマネージコードの間の遷移をデバッグする場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="83ea2-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="83ea2-115">MDA の作成をトリガーするイベントが発生した場合、ランタイムは次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="83ea2-116">ホストが[ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)を呼び出して[Iactiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)インスタンスを登録していない場合に、`Event_MDAFired` イベントが通知されるようにするには、ランタイムは既定のホストされていない動作に進みます。</span><span class="sxs-lookup"><span data-stu-id="83ea2-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="83ea2-117">ホストがこのイベントのハンドラーを登録している場合、ランタイムはデバッガーがプロセスにアタッチされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="83ea2-118">存在する場合、ランタイムはデバッガーに中断します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="83ea2-119">デバッガーが続行されると、ホストが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="83ea2-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="83ea2-120">デバッガーがアタッチされていない場合、ランタイムは `IActionOnCLREvent::OnEvent` を呼び出し、`data` パラメーターとして `MDAInfo` インスタンスへのポインターを渡します。</span><span class="sxs-lookup"><span data-stu-id="83ea2-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="83ea2-121">ホストは mda をアクティブ化し、MDA がアクティブになったときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="83ea2-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="83ea2-122">これにより、ホストは、既定の動作をオーバーライドし、イベントを発生させたマネージスレッドを中止して、プロセスの状態が破損するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="83ea2-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="83ea2-123">Mda の使用方法の詳細については、「[マネージデバッグアシスタントによるエラーの診断](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83ea2-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ea2-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="83ea2-124">Requirements</span></span>  
 <span data-ttu-id="83ea2-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83ea2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83ea2-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="83ea2-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="83ea2-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="83ea2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83ea2-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83ea2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ea2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="83ea2-129">See also</span></span>

- [<span data-ttu-id="83ea2-130">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="83ea2-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="83ea2-131">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="83ea2-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

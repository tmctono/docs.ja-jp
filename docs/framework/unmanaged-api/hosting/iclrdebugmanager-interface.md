---
title: ICLRDebugManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198843"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="79d0f-102">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79d0f-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="79d0f-103">Id とフレンドリ名を関連付ける一連のタスクをホストできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79d0f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-104">Methods</span></span>  
  
|<span data-ttu-id="79d0f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-105">Method</span></span>|<span data-ttu-id="79d0f-106">説明</span><span class="sxs-lookup"><span data-stu-id="79d0f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79d0f-107">BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="79d0f-108">ホストとデバッガーは、id とフレンドリ名を関連付けるタスクの間の新しい接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="79d0f-109">EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="79d0f-110">タスクの一覧と、識別子とフレンドリ名の間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="79d0f-111">GetDacl メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="79d0f-112">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="79d0f-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="79d0f-113">IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="79d0f-114">デバッガーがプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="79d0f-115">SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="79d0f-116">リストを関連付けます[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)識別子とフレンドリ名を持つインスタンス。</span><span class="sxs-lookup"><span data-stu-id="79d0f-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="79d0f-117">SetDacl メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="79d0f-118">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="79d0f-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="79d0f-119">SetSymbolReadingPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="79d0f-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="79d0f-120">プログラム データベース (PDB) ファイルを読み取るためのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="79d0f-121">ポリシーは、呼び出し履歴で行番号およびファイルに関する情報が含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79d0f-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="79d0f-122">Remarks</span></span>  
 <span data-ttu-id="79d0f-123">シナリオをデバッグするには、ホストは、独自のプログラミング ロジックに従ってタスクをグループ化をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79d0f-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="79d0f-124">たとえばをグループ化は、開発者は、プロセスで実行されているすべてのタスクではなく、開発者の Api で必要なタスクのみを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d0f-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> `ICLRDebugManager` <span data-ttu-id="79d0f-125">この種のグループ化を実装するためにホストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="79d0f-125">allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79d0f-126">次の 3 つ`ICLRDebugManager`メソッド、 `BeginConnection`、`SetConnectionTasks`と`EndConnection`、互いに依存します。</span><span class="sxs-lookup"><span data-stu-id="79d0f-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="79d0f-127">期待どおりに動作する特定の順序で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d0f-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="79d0f-128">グループ化、および識別子とホストは、グループに割り当てます。 フレンドリ名ありませんにとって意味のある共通言語ランタイム (CLR)。</span><span class="sxs-lookup"><span data-stu-id="79d0f-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="79d0f-129">CLR は、デバッガーを利用して、情報を渡すだけです。</span><span class="sxs-lookup"><span data-stu-id="79d0f-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79d0f-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="79d0f-130">Requirements</span></span>  
 <span data-ttu-id="79d0f-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d0f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79d0f-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="79d0f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79d0f-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="79d0f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="79d0f-134">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="79d0f-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="79d0f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="79d0f-135">See also</span></span>

- [<span data-ttu-id="79d0f-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79d0f-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

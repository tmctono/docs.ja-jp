---
title: CLR ホスト インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80404e65263aa4ad245a8c8213630a4736bd7b11
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456875"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="e5993-102">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="e5993-103">アンマネージ インターフェイスについて説明をアプリケーションに共通言語ランタイム (CLR) を統合するホストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5993-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="e5993-104">情報は、.NET Framework version 2.0 およびそれ以降のバージョンに関係します。</span><span class="sxs-lookup"><span data-stu-id="e5993-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="e5993-105">これらのインターフェイスは、ホストのランタイム バージョン 1.0 および 1.1 では、いたよりもさらに多くの制御を有効にして、CLR とホストの実行モデルのより緊密に統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="e5993-106">.NET framework version 1.0 および 1.1 では、ホスティング モデルでは、アンマネージ ホストに、CLR を読み込むプロセス、イベント通知を受信して、特定の設定を構成するを有効になります。</span><span class="sxs-lookup"><span data-stu-id="e5993-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="e5993-107">ただし、一般に、ホストと CLR 個別に実行されてそのプロセスにします。</span><span class="sxs-lookup"><span data-stu-id="e5993-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="e5993-108">.NET Framework version 2.0 以降のバージョンでは、新しい抽象化レイヤーは、現在、Win32 アセンブリ内の型によって提供されるリソースの多くを提供し、一連のホストが構成可能な機能を拡張するホストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5993-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5993-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e5993-109">In This Section</span></span>  
 [<span data-ttu-id="e5993-110">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="e5993-111">登録済みのイベントのコールバックを実行するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="e5993-112">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="e5993-113">アパートメント内でのコールバックを行うためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="e5993-114">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="e5993-115">実行時構成の設定のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="e5993-116">ICatalogServices インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="e5993-117">カタログ サービスのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="e5993-118">(このインターフェイスは、.NET Framework インフラストラクチャをサポートしているし、コードから直接使用するものではありません)。</span><span class="sxs-lookup"><span data-stu-id="e5993-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="e5993-119">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="e5993-120">ホストと、CLR アセンブリの間の通信をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="e5993-121">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="e5993-122">ホストではなく、CLR によって読み込まれるアセンブリの一覧を管理します。</span><span class="sxs-lookup"><span data-stu-id="e5993-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="e5993-123">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="e5993-124">ホストにアクセスし、CLR のさまざまな側面を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="e5993-125">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="e5993-126">ホスト id とフレンドリ名を関連付ける一連のタスクを有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="e5993-127">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="e5993-128">エラー報告用にカスタムのヒープ ダンプを構成するホストを有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="e5993-129">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="e5993-130">ホストが CLR のガベージ コレクション システムとの対話を可能にするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="e5993-131">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="e5993-132">ホストを評価し、アセンブリのポリシー情報の変更を通知するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="e5993-133">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="e5993-134">特定のマネージ クラス、メソッド、プロパティ、およびフィールドを部分的に信頼されたコードでの実行をブロックするホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5993-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="e5993-135">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="e5993-136">ホストが、指定された I/O 要求の状態の CLR に通知できるようにするコールバック メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="e5993-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="e5993-137">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="e5993-138">ホストが、Win32 のと同様の手法を使用してメモリ不足の状態を報告できるように`CreateMemoryResourceNotification`関数。</span><span class="sxs-lookup"><span data-stu-id="e5993-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="e5993-139">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="e5993-140">ホストが登録および CLR イベントのコールバックを登録解除を有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="e5993-141">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="e5993-142">ポリシー エラーやタイムアウトが発生した場合に実行されるアクションを指定するホストを有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="e5993-143">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="e5993-144">ホストを作成し、その id を理解したりしなくても、clr の内部にあるアセンブリの id 情報を使用してアセンブリのプローブの id を取得できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="e5993-145">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="e5993-146">ホスト ファイルまたはアセンブリの id データを作成し、それらの id を理解したりしなくても、clr の内部にあるを使用してストリームによって参照されるアセンブリのセットを操作できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="e5993-147">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="e5993-148">同様の機能を提供します。 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)、ホスト コントロールのインターフェイスを設定する追加のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5993-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="e5993-149">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="e5993-150">要求されたタスクに関する情報を取得し、その同期実装でデッドロックを検出するために、ホストのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="e5993-151">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="e5993-152">ホストまたは関連するタスクについて、CLR に通知を提供する、clr の要求を行うことができるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="e5993-153">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="e5993-154">ホストが CLR に新しいタスクを作成し、現在実行中のタスクを取得し、地理的な言語とタスクのカルチャを設定することを明示的に要求できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="e5993-155">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="e5993-156">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="e5993-157">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="e5993-158">CLR を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="e5993-159">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="e5993-160">スレッド プールにアクセスするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="e5993-161">IDebuggerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="e5993-162">デバッグ サービスの状態に関する情報を取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="e5993-163">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="e5993-164">デバッグ サービスによるスレッドのブロックおよびブロックについて、ホストを通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="e5993-165">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="e5993-166">ガベージ コレクション システムに関する情報を取得するため、ガベージ コレクションの一部の側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="e5993-167">IGCHost2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="e5993-168">提供、 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)ホストがガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズの値より大きいに設定できるようにメソッド`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="e5993-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="e5993-169">IGCHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="e5993-170">ガベージ コレクターは、仮想メモリの制限を変更するホストを要求できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="e5993-171">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="e5993-172">本来はガベージ コレクションがブロックされるスレッドのスケジューリングに参加するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="e5993-173">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="e5993-174">ホストまたはホストが CLR によって読み込む必要のあるアセンブリのセットを指定するを有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="e5993-175">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="e5993-176">アセンブリと CLR とは無関係にモジュールを読み込むホストを有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="e5993-177">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="e5993-178">ホストによって実装される自動リセット イベントの表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="e5993-179">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="e5993-180">アセンブリの読み込みを設定して、ホストがサポートするホスト インターフェイスを決定するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="e5993-181">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="e5993-182">ホストのスレッドのクリティカル セクションの表現として機能します。</span><span class="sxs-lookup"><span data-stu-id="e5993-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="e5993-183">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="e5993-184">ガベージ コレクションのメカニズムが CLR によって実装内のイベントのホストに通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="e5993-185">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="e5993-186">ホストによって提供される I/O 完了ポートと対話する CLR を有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="e5993-187">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="e5993-188">CLR ホストを通じてヒープから詳細な割り当てを要求するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="e5993-189">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="e5993-190">手動リセット イベントの表現のホストの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="e5993-191">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="e5993-192">Win32 仮想メモリの標準の関数を使用する代わりに、ホストで仮想メモリの要求を行う CLR のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="e5993-193">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="e5993-194">ホストの場合、CLR を実行するアクションの中止、タイムアウト、またはエラーを通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="e5993-195">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="e5993-196">ホストによって実装されるセキュリティ コンテキスト情報を維持するために CLR を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5993-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="e5993-197">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="e5993-198">アクセスを有効にして、現在実行中のスレッドのセキュリティ コンテキストを制御するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="e5993-199">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="e5993-200">ホストによって実装されるセマフォの表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="e5993-201">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="e5993-202">CLR が同期の Win32 関数を使用する代わりに、ホストを呼び出すことによって同期プリミティブを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="e5993-203">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="e5993-204">タスクを管理するホストと通信するために CLR を有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="e5993-205">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="e5993-206">標準のオペレーティング システムのスレッドやファイバーの関数を使用する代わりに、ホストを通じてタスクを使用する CLR を有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="e5993-207">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="e5993-208">CLR スレッド プールを構成して、作業項目をスレッド プール キューのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="e5993-209">IManagedObject インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="e5993-210">マネージ オブジェクトを制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="e5993-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="e5993-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="e5993-212">ラップ解除の値渡しのマーシャ リングするオブジェクトの間接参照メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="e5993-213">ITypeName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="e5993-214">型名の情報を取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="e5993-215">(このインターフェイスは、.NET Framework インフラストラクチャをサポートしているし、コードから直接使用するものではありません)。</span><span class="sxs-lookup"><span data-stu-id="e5993-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="e5993-216">ITypeNameBuilder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="e5993-217">型名を構築するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-217">Provides methods for building a type name.</span></span> <span data-ttu-id="e5993-218">(このインターフェイスは、.NET Framework インフラストラクチャをサポートしているし、コードから直接使用するものではありません)。</span><span class="sxs-lookup"><span data-stu-id="e5993-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="e5993-219">ITypeNameFactory インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="e5993-220">型名を分解するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="e5993-221">(このインターフェイスは、.NET Framework インフラストラクチャをサポートしているし、コードから直接使用するものではありません)。</span><span class="sxs-lookup"><span data-stu-id="e5993-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="e5993-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="e5993-222">"IValidator"</span></span>  
 <span data-ttu-id="e5993-223">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5993-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5993-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5993-224">Related Sections</span></span>  
 [<span data-ttu-id="e5993-225">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="e5993-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="e5993-226">.NET Framework version 1.0 および 1.1 で提供されるホスティング インターフェイスについて説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5993-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="e5993-227">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5993-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="e5993-228">.NET Framework 4 で提供されるホスティング インターフェイスについて説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5993-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>

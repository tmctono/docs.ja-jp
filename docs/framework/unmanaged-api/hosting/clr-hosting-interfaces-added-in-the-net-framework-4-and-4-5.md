---
title: .NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: aea88430d8f83234a1568bcaf433c2a75492e23a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195925"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="69060-102">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="69060-103">ここでは、アンマネージホストが .NET Framework 4、.NET Framework 4.5、およびそれ以降のバージョンの共通言語ランタイム (CLR) をアプリケーションに統合するために使用できるインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69060-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="69060-104">これらのインターフェイスは、ホストがランタイムを構成してプロセスに読み込むためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="69060-105">.NET Framework 4 以降では、すべてのホストインターフェイスに次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="69060-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="69060-106">有効期間管理 (`AddRef` と `Release`)、カプセル化 (暗黙的なコンテキスト)、COM からの `QueryInterface` を使用します。</span><span class="sxs-lookup"><span data-stu-id="69060-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="69060-107">`BSTR`、`SAFEARRAY`、`VARIANT`などの COM 型は使用しません。</span><span class="sxs-lookup"><span data-stu-id="69060-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="69060-108">[CoCreateInstance 関数](https://go.microsoft.com/fwlink/?LinkId=142894)を使用するアパートメントモデル、集計、またはレジストリのアクティブ化はありません。</span><span class="sxs-lookup"><span data-stu-id="69060-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69060-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="69060-109">In This Section</span></span>  
 [<span data-ttu-id="69060-110">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="69060-111">アプリケーションドメインのメモリおよび CPU 使用率を検査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="69060-112">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="69060-113">既定のアプリケーションドメインを初期化し、初期化プロパティを指定するために使用されるアプリケーションドメインマネージャーをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="69060-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="69060-114">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="69060-115">[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)メソッドを提供します。これにより、ホストはガベージコレクションセグメントのサイズとガベージコレクションシステムのジェネレーション0の最大サイズを、`DWORD`より大きい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="69060-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="69060-116">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="69060-117">特定のバージョンの CLR を返し、インストールされているすべての CLRs の一覧を取得し、すべてのインプロセスランタイムを一覧表示し、アクティベーションインターフェイスを返し、アセンブリをコンパイルするために使用される CLR バージョンを検出するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="69060-118">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="69060-119">ポリシー条件、マネージアセンブリ、バージョン、および構成ファイルに基づいて CLR インターフェイスを提供する[Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="69060-120">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="69060-121">バージョン、ディレクトリ、読み込みステータスなど、特定のランタイムに関する情報を返すメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="69060-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="69060-123">厳密な名前でアセンブリに署名するための基本的なグローバル静的関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="69060-124">すべての[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)メソッドは、標準 COM hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="69060-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="69060-125">ICLRStrongName2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="69060-126">セキュリティで保護されたハッシュアルゴリズム (SHA-256、SHA-384、および SHA-512) の SHA-1 グループを使用して、厳密な名前を作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="69060-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="69060-127">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="69060-128">には、 [ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)のすべての機能が用意されています。また、には、現在のスレッドでスレッドの中止を遅延させることができるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="69060-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="69060-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="69060-129">Related Sections</span></span>  
 [<span data-ttu-id="69060-130">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="69060-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="69060-131">.NET Framework バージョン1.0 および1.1 で提供されるホストインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69060-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="69060-132">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69060-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="69060-133">.NET Framework バージョン2.0、3.0、および3.5 で提供されるホストインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69060-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="69060-134">ホスティング</span><span class="sxs-lookup"><span data-stu-id="69060-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="69060-135">.NET Framework でのホスティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69060-135">Introduces hosting in the .NET Framework.</span></span>

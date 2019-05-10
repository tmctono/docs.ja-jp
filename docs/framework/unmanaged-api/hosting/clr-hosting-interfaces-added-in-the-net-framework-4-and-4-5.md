---
title: .NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96bc833915dd74756220b5e79a2866b41389dd45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630504"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="38eaa-102">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="38eaa-103">このセクションがアンマネージ インターフェイスについて説明しますホストを使用して、共通言語ランタイム (CLR) 統合、 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、以降のバージョンをアプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="38eaa-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="38eaa-104">これらのインターフェイスは、ホストを構成し、ランタイムをプロセスに読み込むのためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="38eaa-105">以降では、 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]、すべてのホスティング インターフェイスで次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="38eaa-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="38eaa-106">有効期間管理を使用して、(`AddRef`と`Release`)、(暗黙のコンテキスト) をカプセル化し、 `QueryInterface` COM から</span><span class="sxs-lookup"><span data-stu-id="38eaa-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="38eaa-107">ある型を使用しないで COM など`BSTR`、 `SAFEARRAY`、または`VARIANT`します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="38eaa-108">アパートメント モデル、集計、またはレジストリのアクティブ化を使用するがない、 [CoCreateInstance 関数](https://go.microsoft.com/fwlink/?LinkId=142894)します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38eaa-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="38eaa-109">In This Section</span></span>  
 [<span data-ttu-id="38eaa-110">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="38eaa-111">アプリケーション ドメインのメモリと CPU 使用率を確認するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="38eaa-112">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="38eaa-113">初期化プロパティを指定して、既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーを指定するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="38eaa-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="38eaa-114">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="38eaa-115">提供、 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)メソッドで、ホストがガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズの値より大きいに設定できるように`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="38eaa-116">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="38eaa-117">CLR の特定のバージョンを返す、インストールされている Clr のすべてを一覧表示、すべてのプロセス内ランタイムを一覧表示、アクティブ化のインターフェイスを返す、アセンブリをコンパイルするために使用する CLR のバージョンを検出するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="38eaa-118">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="38eaa-119">提供、 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) CLR インターフェイスを提供する方法、ポリシーの条件、マネージ アセンブリ、バージョン、および構成ファイルに基づいています。</span><span class="sxs-lookup"><span data-stu-id="38eaa-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="38eaa-120">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="38eaa-121">バージョン、ディレクトリ、および負荷の状態を含む、特定のランタイムに関する情報を返すメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="38eaa-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="38eaa-123">厳密な名前を持つアセンブリに署名するための基本的なグローバル静的関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="38eaa-124">すべての[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)メソッドは、標準の COM Hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="38eaa-125">ICLRStrongName2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="38eaa-126">Sha-2 (sha-256、sha-384、および sha-512) のハッシュ アルゴリズムをセキュリティで保護グループを使用する厳密な名前を作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="38eaa-127">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="38eaa-128">すべての機能を提供、 [ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)。 さらに、現在のスレッドが遅延するスレッドの中止を許可するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="38eaa-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="38eaa-129">Related Sections</span></span>  
 [<span data-ttu-id="38eaa-130">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="38eaa-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="38eaa-131">.NET Framework version 1.0 および 1.1 で提供されるホスティング インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="38eaa-132">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38eaa-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="38eaa-133">.NET Framework バージョン 2.0、3.0、および 3.5 で提供されるホスティング インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="38eaa-134">ホスティング</span><span class="sxs-lookup"><span data-stu-id="38eaa-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="38eaa-135">.NET Framework でのホスティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38eaa-135">Introduces hosting in the .NET Framework.</span></span>

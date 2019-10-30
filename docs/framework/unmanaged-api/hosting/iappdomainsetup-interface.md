---
title: IAppDomainSetup インターフェイス
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126873"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="ff611-102">IAppDomainSetup インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff611-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="ff611-103">[ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)メソッドを呼び出して作成する前に、ホストが <xref:System.AppDomain?displayProperty=nameWithType> の種類を構成できるようにするプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff611-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ff611-104">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ff611-104">Properties</span></span>  
  
|<span data-ttu-id="ff611-105">property</span><span class="sxs-lookup"><span data-stu-id="ff611-105">Property</span></span>|<span data-ttu-id="ff611-106">説明</span><span class="sxs-lookup"><span data-stu-id="ff611-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="ff611-107">アプリケーションが格納されているディレクトリの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="ff611-108">アプリケーションの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="ff611-109">ファイルがシャドウコピーされるアプリケーション固有の領域の名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="ff611-110">アプリケーションの構成ファイルの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="ff611-111">動的に生成されたファイルが格納およびアクセスされるディレクトリの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="ff611-112">このドメインに関連付けられているライセンスファイルへのパスを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="ff611-113">プライベートアセンブリをプローブするために <xref:System.AppDomainSetup.ApplicationBase%2A> ディレクトリと結合されたディレクトリの一覧を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="ff611-114">アプリケーションの検索パスから <xref:System.AppDomainSetup.ApplicationBase%2A> を含めたり、除外したりする文字列値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="ff611-115">シャドウコピーされるアセンブリを含むディレクトリの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="ff611-116">シャドウコピーをオンまたはオフにするかどうかを示す文字列を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ff611-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="ff611-117">有効な値は "true" または "false" です。</span><span class="sxs-lookup"><span data-stu-id="ff611-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff611-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff611-118">Remarks</span></span>  
 <span data-ttu-id="ff611-119">`IAppDomainSetup` インターフェイスは、<xref:System.AppDomainSetup> 型が実装するマネージ <xref:System.IAppDomainSetup> インターフェイスに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ff611-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="ff611-120">プロパティの詳細については、「<xref:System.IAppDomainSetup?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff611-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="ff611-121">`IAppDomainSetup` は、作成前に <xref:System.AppDomain> インスタンスに追加できるアセンブリバインディング情報を表します。</span><span class="sxs-lookup"><span data-stu-id="ff611-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="ff611-122">たとえば、ホストは、<xref:System.AppDomainSetup.ApplicationBase%2A> プロパティを設定して、マネージアセンブリの共通言語ランタイム (CLR) プローブがルートディレクトリを確立することができます。</span><span class="sxs-lookup"><span data-stu-id="ff611-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff611-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="ff611-123">Requirements</span></span>  
 <span data-ttu-id="ff611-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff611-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff611-125">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff611-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff611-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ff611-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff611-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff611-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff611-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff611-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="ff611-129">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff611-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

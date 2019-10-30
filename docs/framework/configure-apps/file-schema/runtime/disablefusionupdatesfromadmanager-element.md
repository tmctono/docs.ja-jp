---
title: <disableFusionUpdatesFromADManager> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: 4e7375fddaa98b45766b29d911d555f773edcafa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117446"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="99d2b-102">\<disableFusionUpdatesFromADManager > 要素</span><span class="sxs-lookup"><span data-stu-id="99d2b-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="99d2b-103">アプリケーション ドメインの構成設定をランタイム ホストがオーバーライドする既定の動作を無効化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99d2b-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
<span data-ttu-id="99d2b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99d2b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99d2b-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="99d2b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="99d2b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disableFusionUpdatesFromADManager >**</span><span class="sxs-lookup"><span data-stu-id="99d2b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d2b-107">構文</span><span class="sxs-lookup"><span data-stu-id="99d2b-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99d2b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99d2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99d2b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99d2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99d2b-110">属性</span><span class="sxs-lookup"><span data-stu-id="99d2b-110">Attributes</span></span>  
  
|<span data-ttu-id="99d2b-111">属性</span><span class="sxs-lookup"><span data-stu-id="99d2b-111">Attribute</span></span>|<span data-ttu-id="99d2b-112">説明</span><span class="sxs-lookup"><span data-stu-id="99d2b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99d2b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="99d2b-113">enabled</span></span>|<span data-ttu-id="99d2b-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="99d2b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="99d2b-115">Fusion 設定をオーバーライドする既定の機能が無効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99d2b-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="99d2b-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="99d2b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="99d2b-117">[値]</span><span class="sxs-lookup"><span data-stu-id="99d2b-117">Value</span></span>|<span data-ttu-id="99d2b-118">説明</span><span class="sxs-lookup"><span data-stu-id="99d2b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99d2b-119">0</span><span class="sxs-lookup"><span data-stu-id="99d2b-119">0</span></span>|<span data-ttu-id="99d2b-120">Fusion の設定をオーバーライドする機能を無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="99d2b-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="99d2b-121">これは、.NET Framework 4 から始まる既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="99d2b-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="99d2b-122">1</span><span class="sxs-lookup"><span data-stu-id="99d2b-122">1</span></span>|<span data-ttu-id="99d2b-123">Fusion の設定をオーバーライドする機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="99d2b-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="99d2b-124">これにより、.NET Framework の以前のバージョンの動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="99d2b-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99d2b-125">子要素</span><span class="sxs-lookup"><span data-stu-id="99d2b-125">Child Elements</span></span>  
 <span data-ttu-id="99d2b-126">なし。</span><span class="sxs-lookup"><span data-stu-id="99d2b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99d2b-127">親要素</span><span class="sxs-lookup"><span data-stu-id="99d2b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="99d2b-128">要素</span><span class="sxs-lookup"><span data-stu-id="99d2b-128">Element</span></span>|<span data-ttu-id="99d2b-129">説明</span><span class="sxs-lookup"><span data-stu-id="99d2b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="99d2b-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="99d2b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="99d2b-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99d2b-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99d2b-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="99d2b-132">Remarks</span></span>  
 <span data-ttu-id="99d2b-133">.NET Framework 4 以降では、既定の動作として、<xref:System.AppDomainManager> オブジェクトが、<xref:System.AppDomainSetup.ConfigurationFile%2A> プロパティ、または <xref:System.AppDomainSetup> メソッドの実装に渡される <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> オブジェクトの <xref:System.AppDomainSetup.SetConfigurationBytes%2A> メソッドを使用して構成設定をオーバーライドできるようにします。<xref:System.AppDomainManager>のサブクラスにあります。</span><span class="sxs-lookup"><span data-stu-id="99d2b-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="99d2b-134">既定のアプリケーションドメインでは、変更した設定によって、アプリケーション構成ファイルで指定された設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="99d2b-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="99d2b-135">他のアプリケーションドメインについては、<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> または <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> メソッドに渡された構成設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="99d2b-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="99d2b-136">新しい構成情報を渡すか、null (Visual Basic で`Nothing`) を渡して、渡された構成情報を除外することができます。</span><span class="sxs-lookup"><span data-stu-id="99d2b-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="99d2b-137"><xref:System.AppDomainSetup.ConfigurationFile%2A> プロパティと <xref:System.AppDomainSetup.SetConfigurationBytes%2A> メソッドの両方に構成情報を渡さないでください。</span><span class="sxs-lookup"><span data-stu-id="99d2b-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="99d2b-138">構成情報を両方に渡す場合、<xref:System.AppDomainSetup.SetConfigurationBytes%2A> メソッドはアプリケーション構成ファイルの構成情報を上書きするため、<xref:System.AppDomainSetup.ConfigurationFile%2A> プロパティに渡す情報は無視されます。</span><span class="sxs-lookup"><span data-stu-id="99d2b-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="99d2b-139"><xref:System.AppDomainSetup.ConfigurationFile%2A> プロパティを使用する場合、<xref:System.AppDomainSetup.SetConfigurationBytes%2A> メソッドに null (`Nothing` Visual Basic) を渡して、<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> または <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> メソッドの呼び出しで指定された構成バイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="99d2b-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="99d2b-140">構成情報に加えて、<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> メソッドの実装に渡される <xref:System.AppDomainSetup> オブジェクトの次の設定を変更できます。 <xref:System.AppDomainSetup.ApplicationBase%2A>、<xref:System.AppDomainSetup.ApplicationName%2A>、<xref:System.AppDomainSetup.CachePath%2A>、<xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>、<xref:System.AppDomainSetup.DisallowBindingRedirects%2A>、<xref:System.AppDomainSetup.DisallowCodeDownload%2A>、<xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>、<xref:System.AppDomainSetup.DynamicBase%2A>、<xref:System.AppDomainSetup.LoaderOptimization%2A>、<xref:System.AppDomainSetup.PrivateBinPath%2A>、<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>、<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>、および <xref:System.AppDomainSetup.ShadowCopyFiles%2A>。</span><span class="sxs-lookup"><span data-stu-id="99d2b-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="99d2b-141">`<disableFusionUpdatesFromADManager>` 要素を使用する代わりに、レジストリ設定を作成するか、環境変数を設定することによって、既定の動作を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="99d2b-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="99d2b-142">レジストリで、`HKCU\Software\Microsoft\.NETFramework` または `HKLM\Software\Microsoft\.NETFramework`の下に `COMPLUS_disableFusionUpdatesFromADManager` という名前の DWORD 値を作成し、値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="99d2b-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="99d2b-143">コマンドラインで、環境変数 `COMPLUS_disableFusionUpdatesFromADManager` を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="99d2b-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99d2b-144">例</span><span class="sxs-lookup"><span data-stu-id="99d2b-144">Example</span></span>  
 <span data-ttu-id="99d2b-145">次の例は、`<disableFusionUpdatesFromADManager>` 要素を使用して Fusion 設定をオーバーライドする機能を無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="99d2b-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99d2b-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="99d2b-146">See also</span></span>

- [<span data-ttu-id="99d2b-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="99d2b-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="99d2b-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="99d2b-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="99d2b-149">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="99d2b-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

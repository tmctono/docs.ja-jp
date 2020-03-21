---
title: <loadFromRemoteSources> 要素
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154063"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="5c6fa-102">\<要素>リモートソースを読み込む</span><span class="sxs-lookup"><span data-stu-id="5c6fa-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="5c6fa-103">リモート ソースから読み込まれたアセンブリに .NET Framework 4 以降で完全な信頼を付与するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c6fa-104">Visual Studio プロジェクトのエラー一覧のエラー メッセージまたはビルド エラーが原因でこの資料に指示された場合は、「[方法 : Visual Studio で Web からアセンブリを使用する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="5c6fa-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c6fa-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c6fa-106">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c6fa-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5c6fa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<>からリモートソースを読み込む**</span><span class="sxs-lookup"><span data-stu-id="5c6fa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6fa-108">構文</span><span class="sxs-lookup"><span data-stu-id="5c6fa-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c6fa-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5c6fa-109">Attributes and elements</span></span>
 <span data-ttu-id="5c6fa-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c6fa-111">属性</span><span class="sxs-lookup"><span data-stu-id="5c6fa-111">Attributes</span></span>  
  
|<span data-ttu-id="5c6fa-112">属性</span><span class="sxs-lookup"><span data-stu-id="5c6fa-112">Attribute</span></span>|<span data-ttu-id="5c6fa-113">説明</span><span class="sxs-lookup"><span data-stu-id="5c6fa-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5c6fa-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5c6fa-115">リモート ソースから読み込まれるアセンブリに完全信頼を付与するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5c6fa-116">有効な属性</span><span class="sxs-lookup"><span data-stu-id="5c6fa-116">enabled attribute</span></span>  
  
|<span data-ttu-id="5c6fa-117">Value</span><span class="sxs-lookup"><span data-stu-id="5c6fa-117">Value</span></span>|<span data-ttu-id="5c6fa-118">説明</span><span class="sxs-lookup"><span data-stu-id="5c6fa-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5c6fa-119">リモート ソースからのアプリケーションに完全な信頼を付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="5c6fa-120">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5c6fa-121">リモート ソースからのアプリケーションに完全な信頼を付与します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c6fa-122">子要素</span><span class="sxs-lookup"><span data-stu-id="5c6fa-122">Child elements</span></span>  
 <span data-ttu-id="5c6fa-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="5c6fa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c6fa-124">親要素</span><span class="sxs-lookup"><span data-stu-id="5c6fa-124">Parent elements</span></span>  
  
|<span data-ttu-id="5c6fa-125">要素</span><span class="sxs-lookup"><span data-stu-id="5c6fa-125">Element</span></span>|<span data-ttu-id="5c6fa-126">説明</span><span class="sxs-lookup"><span data-stu-id="5c6fa-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5c6fa-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5c6fa-128">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c6fa-129">解説</span><span class="sxs-lookup"><span data-stu-id="5c6fa-129">Remarks</span></span>

<span data-ttu-id="5c6fa-130">.NET Framework 3.5 以前のバージョンでは、リモートの場所からアセンブリを読み込むと、アセンブリ内のコードは、アセンブリの読み込み元のゾーンに依存する許可セットを使用して部分的に信頼されて実行されます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="5c6fa-131">たとえば、Web サイトからアセンブリを読み込むと、そのアセンブリはインターネット ゾーンに読み込まれ、インターネット アクセス許可セットが付与されます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="5c6fa-132">つまり、インターネットサンドボックスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="5c6fa-133">.NET Framework 4 以降、コード アクセス セキュリティ (CAS) ポリシーは無効になり、アセンブリは完全信頼で読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="5c6fa-134">通常、これは以前にサンドボックス化されていたメソッドを読み込んだアセンブリに<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>完全な信頼を与えます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="5c6fa-135">これを防ぐために、リモート ソースから読み込まれたアセンブリでコードを実行する機能は、既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="5c6fa-136">既定では、リモート アセンブリを読み込もうとすると<xref:System.IO.FileLoadException>、次のような例外メッセージがスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="5c6fa-137">アセンブリを読み込んでそのコードを実行するには、次のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="5c6fa-138">アセンブリのサンドボックスを明示的に作成します (「[方法 : サンドボックスで部分的に信頼されたコードを実行](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)する」を参照)。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="5c6fa-139">アセンブリのコードを完全信頼で実行します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="5c6fa-140">これは`<loadFromRemoteSources>`、要素を構成することによって行います。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="5c6fa-141">このクラスでは、以前のバージョンの .NET Framework で部分信頼で実行されるアセンブリが 、.NET Framework 4 以降のバージョンで完全に信頼されたバージョンで実行されるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c6fa-142">アセンブリが完全信頼で実行されない場合は、この構成要素を設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="5c6fa-143">代わりに、アセンブリを読<xref:System.AppDomain>み込むサンドボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="5c6fa-144">要素`enabled`の`<loadFromRemoteSources>`属性は、コード アクセス セキュリティ (CAS) が無効になっている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="5c6fa-145">既定では、CAS ポリシーは .NET Framework 4 以降のバージョンでは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="5c6fa-146">に`enabled``true`設定すると、リモート アセンブリには完全な信頼が与えられます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="5c6fa-147">に`enabled`設定`true`されていない場合、a<xref:System.IO.FileLoadException>は次のいずれかの条件でスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="5c6fa-148">現在のドメインのサンドボックスの動作は、.NET Framework 3.5 での動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="5c6fa-149">これには、CAS ポリシーを無効にし、現在のドメインをサンドボックス化しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="5c6fa-150">読み込まれるアセンブリが`MyComputer`ゾーンから取得されていません。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="5c6fa-151">この例外`<loadFromRemoteSources>`がスロー`true`されないように要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="5c6fa-152">これにより、共通言語ランタイムを使用して、読み込まれたアセンブリをセキュリティでサンドボックス化することや、完全信頼で実行できることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="5c6fa-153">Notes</span><span class="sxs-lookup"><span data-stu-id="5c6fa-153">Notes</span></span>

- <span data-ttu-id="5c6fa-154">.NET Framework 4.5 以降のバージョンでは、ローカル ネットワーク上のアセンブリは既定で完全な信頼で実行されます。要素を有効にする`<loadFromRemoteSources>`必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="5c6fa-155">Web からコピーされたアプリケーションは、ローカル コンピューターに存在する場合でも、Web アプリケーションとして Windows によってフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="5c6fa-156">ファイル プロパティを変更して指定を変更するか、要素を`<loadFromRemoteSources>`使用してアセンブリに完全な信頼を付与できます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="5c6fa-157">代わりに、<xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>このメソッドを使用して、オペレーティング システムが Web から読み込まれたとフラグを立てたローカル アセンブリを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="5c6fa-158">Windows Virtual <xref:System.IO.FileLoadException> PC アプリケーションで実行されているアプリケーションで を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="5c6fa-159">これは、ホスト コンピューター上のリンクされたフォルダーからファイルを読み込もうとしたときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="5c6fa-160">また、[リモート デスクトップ サービス](/windows/win32/termserv/terminal-services-portal)(ターミナル サービス) を介してリンクされたフォルダからファイルを読み込もうとしたときにも発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="5c6fa-161">この例外を回避するには、 `enabled` `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="5c6fa-162">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="5c6fa-162">Configuration file</span></span>

<span data-ttu-id="5c6fa-163">この要素は、通常、アプリケーション構成ファイルで使用されますが、コンテキストに応じて他の構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="5c6fa-164">詳細については、.NET セキュリティブログの記事[「CAS ポリシーの暗黙的な使用: loadFromRemoteSources」](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="5c6fa-165">例</span><span class="sxs-lookup"><span data-stu-id="5c6fa-165">Example</span></span>

<span data-ttu-id="5c6fa-166">リモート ソースから読み込まれたアセンブリに完全な信頼を付与する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5c6fa-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="5c6fa-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c6fa-167">See also</span></span>

- [<span data-ttu-id="5c6fa-168">CAS ポリシーのより暗黙的な使用: 読み込みリモート ソース</span><span class="sxs-lookup"><span data-stu-id="5c6fa-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="5c6fa-169">方法 : サンドボックスで部分信頼コードを実行する</span><span class="sxs-lookup"><span data-stu-id="5c6fa-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="5c6fa-170">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5c6fa-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5c6fa-171">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5c6fa-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

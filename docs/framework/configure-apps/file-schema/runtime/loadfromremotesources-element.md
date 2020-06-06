---
title: <loadFromRemoteSources> 要素
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154063"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="d51f1-102">\<loadFromRemoteSources> 要素</span><span class="sxs-lookup"><span data-stu-id="d51f1-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="d51f1-103">リモートソースから読み込まれたアセンブリに .NET Framework 4 以降で完全信頼を付与するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d51f1-104">Visual Studio プロジェクトのエラー一覧またはビルドエラーのエラーメッセージが原因でこの記事にリダイレクトされた場合は、「[方法: Visual studio で Web からアセンブリを使用する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d51f1-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="d51f1-105">構文</span><span class="sxs-lookup"><span data-stu-id="d51f1-105">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d51f1-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d51f1-106">Attributes and elements</span></span>
 <span data-ttu-id="d51f1-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d51f1-108">属性</span><span class="sxs-lookup"><span data-stu-id="d51f1-108">Attributes</span></span>  
  
|<span data-ttu-id="d51f1-109">属性</span><span class="sxs-lookup"><span data-stu-id="d51f1-109">Attribute</span></span>|<span data-ttu-id="d51f1-110">説明</span><span class="sxs-lookup"><span data-stu-id="d51f1-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d51f1-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="d51f1-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="d51f1-112">リモートソースから読み込まれたアセンブリに完全信頼を付与するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-112">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d51f1-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="d51f1-113">enabled attribute</span></span>  
  
|<span data-ttu-id="d51f1-114">値</span><span class="sxs-lookup"><span data-stu-id="d51f1-114">Value</span></span>|<span data-ttu-id="d51f1-115">Description</span><span class="sxs-lookup"><span data-stu-id="d51f1-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d51f1-116">リモートソースからアプリケーションへの完全な信頼を付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="d51f1-116">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="d51f1-117">既定値です。</span><span class="sxs-lookup"><span data-stu-id="d51f1-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d51f1-118">リモートソースからアプリケーションへの完全な信頼を付与します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-118">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d51f1-119">子要素</span><span class="sxs-lookup"><span data-stu-id="d51f1-119">Child elements</span></span>  
 <span data-ttu-id="d51f1-120">なし。</span><span class="sxs-lookup"><span data-stu-id="d51f1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d51f1-121">親要素</span><span class="sxs-lookup"><span data-stu-id="d51f1-121">Parent elements</span></span>  
  
|<span data-ttu-id="d51f1-122">要素</span><span class="sxs-lookup"><span data-stu-id="d51f1-122">Element</span></span>|<span data-ttu-id="d51f1-123">Description</span><span class="sxs-lookup"><span data-stu-id="d51f1-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d51f1-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d51f1-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d51f1-125">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d51f1-126">解説</span><span class="sxs-lookup"><span data-stu-id="d51f1-126">Remarks</span></span>

<span data-ttu-id="d51f1-127">.NET Framework 3.5 以前のバージョンでは、リモートの場所からアセンブリを読み込む場合、アセンブリ内のコードは、読み込み元のゾーンに依存する許可セットを使用して部分信頼で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-127">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="d51f1-128">たとえば、web サイトからアセンブリを読み込むと、インターネットゾーンに読み込まれ、インターネットのアクセス許可セットが付与されます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-128">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="d51f1-129">つまり、インターネットサンドボックスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-129">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="d51f1-130">.NET Framework 4 以降では、コードアクセスセキュリティ (CAS) ポリシーが無効になり、アセンブリが完全信頼で読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-130">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="d51f1-131">通常、これは、以前にサンドボックス化されたメソッドで読み込まれたアセンブリに対して完全な信頼を付与 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-131">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="d51f1-132">これを回避するために、リモートソースから読み込まれたアセンブリ内のコードを実行する機能は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d51f1-132">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="d51f1-133">既定では、リモートアセンブリを読み込もうとすると、 <xref:System.IO.FileLoadException> 次のような例外メッセージを含むがスローされます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-133">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="d51f1-134">アセンブリを読み込んでコードを実行するには、次のいずれかを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-134">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="d51f1-135">アセンブリのサンドボックスを明示的に作成します (「[方法: サンドボックスで部分信頼コードを実行する](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d51f1-135">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="d51f1-136">アセンブリのコードを完全信頼で実行します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-136">Run the assembly's code in full trust.</span></span> <span data-ttu-id="d51f1-137">これを行うには、要素を構成し `<loadFromRemoteSources>` ます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-137">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="d51f1-138">以前のバージョンの .NET Framework で部分信頼で実行されるアセンブリが、.NET Framework 4 以降のバージョンで完全信頼で実行されるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-138">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d51f1-139">アセンブリを完全信頼で実行しない場合は、この構成要素を設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="d51f1-139">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="d51f1-140">代わりに、アセンブリを読み込むためのサンドボックスを作成し <xref:System.AppDomain> ます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-140">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="d51f1-141">`enabled`要素の属性は、 `<loadFromRemoteSources>` コードアクセスセキュリティ (CAS) が無効になっている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d51f1-141">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="d51f1-142">既定では、CAS ポリシーは .NET Framework 4 以降のバージョンで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d51f1-142">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="d51f1-143">をに設定した場合 `enabled` `true` 、リモートアセンブリには完全な信頼が付与されます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-143">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="d51f1-144">`enabled`がに設定されていない場合は、 `true` <xref:System.IO.FileLoadException> 次のいずれかの条件でがスローされます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-144">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="d51f1-145">現在のドメインのサンドボックスの動作は、.NET Framework 3.5 の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-145">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="d51f1-146">これには、CAS ポリシーを無効にし、現在のドメインをサンドボックス化しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="d51f1-147">読み込まれているアセンブリがゾーンからのものではありません `MyComputer` 。</span><span class="sxs-lookup"><span data-stu-id="d51f1-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="d51f1-148">要素を `<loadFromRemoteSources>` に設定すると、 `true` この例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="d51f1-148">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="d51f1-149">これにより、共通言語ランタイムに依存しないように指定して、読み込まれたアセンブリのセキュリティをサンドボックス化することができます。また、完全信頼での実行を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-149">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="d51f1-150">ノート</span><span class="sxs-lookup"><span data-stu-id="d51f1-150">Notes</span></span>

- <span data-ttu-id="d51f1-151">.NET Framework 4.5 以降のバージョンでは、ローカルネットワーク共有上のアセンブリは既定で完全信頼で実行されます。要素を有効にする必要はありません `<loadFromRemoteSources>` 。</span><span class="sxs-lookup"><span data-stu-id="d51f1-151">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="d51f1-152">アプリケーションが web からコピーされた場合、ローカルコンピューターに存在する場合でも、web アプリケーションとして Windows によってフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-152">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="d51f1-153">そのようなファイルのプロパティを変更することで、その指定を変更できます。また、要素を使用して `<loadFromRemoteSources>` 、アセンブリに完全信頼を付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-153">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="d51f1-154">別の方法として、メソッドを使用して、 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> オペレーティングシステムによって web から読み込まれたとしてフラグが設定されているローカルアセンブリを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-154">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="d51f1-155"><xref:System.IO.FileLoadException>Windows 仮想 PC アプリケーションで実行されているアプリケーションで、が取得される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-155">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="d51f1-156">これは、ホストコンピューター上のリンクフォルダーからファイルを読み込もうとした場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-156">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="d51f1-157">また、[リモートデスクトップサービス](/windows/win32/termserv/terminal-services-portal)(ターミナルサービス) にリンクされているフォルダーからファイルを読み込もうとした場合にも発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d51f1-157">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="d51f1-158">この例外を回避するには、 `enabled` をに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="d51f1-158">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="d51f1-159">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d51f1-159">Configuration file</span></span>

<span data-ttu-id="d51f1-160">この要素は通常、アプリケーション構成ファイルで使用されますが、コンテキストに応じて他の構成ファイルで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d51f1-160">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="d51f1-161">詳細については、.NET セキュリティブログの「 [CAS Policy: loadFromRemoteSources の暗黙的な使用方法](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d51f1-161">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="d51f1-162">例</span><span class="sxs-lookup"><span data-stu-id="d51f1-162">Example</span></span>

<span data-ttu-id="d51f1-163">次の例は、リモートソースから読み込まれたアセンブリに完全信頼を付与する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d51f1-163">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="d51f1-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="d51f1-164">See also</span></span>

- [<span data-ttu-id="d51f1-165">CAS ポリシーの暗黙的な使用方法: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="d51f1-165">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="d51f1-166">方法: サンドボックスで部分信頼コードを実行する</span><span class="sxs-lookup"><span data-stu-id="d51f1-166">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="d51f1-167">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d51f1-167">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d51f1-168">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d51f1-168">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

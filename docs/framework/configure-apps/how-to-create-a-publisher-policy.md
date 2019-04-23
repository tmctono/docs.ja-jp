---
title: '方法: 発行者ポリシーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: ce2df9d4cea601652ebde2032758137b01faacdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344664"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="6fdff-102">方法: 発行者ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6fdff-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="6fdff-103">アセンブリの販売できる状態の監視アプリケーションがアップグレード済みのアセンブリに発行者ポリシー ファイルを含めることによって、新しいバージョンのアセンブリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdff-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="6fdff-104">発行者ポリシー ファイルは、アセンブリのリダイレクトとコードの基本設定を指定し、アプリケーション構成ファイルと同じ形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="6fdff-105">発行者ポリシー ファイルがアセンブリにコンパイルし、グローバル アセンブリ キャッシュに配置します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="6fdff-106">パブリッシャー ポリシーを作成するのには、3 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="6fdff-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1. <span data-ttu-id="6fdff-107">発行者ポリシー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-107">Create a publisher policy file.</span></span>  
  
2. <span data-ttu-id="6fdff-108">発行者ポリシー アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-108">Create a publisher policy assembly.</span></span>  
  
3. <span data-ttu-id="6fdff-109">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="6fdff-110">パブリッシャー ポリシー用のスキーマについては、「[アセンブリ バージョンのリダイレクト](../../../docs/framework/configure-apps/redirect-assembly-versions.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="6fdff-111">次の例は、パブリッシャー ポリシー ファイルの 1 つのバージョンをリダイレクトする`myAssembly`間。</span><span class="sxs-lookup"><span data-stu-id="6fdff-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6fdff-112">コード ベースを指定する方法については、次を参照してください。[アセンブリの場所を指定する](../../../docs/framework/configure-apps/specify-assembly-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="6fdff-113">発行者ポリシー アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="6fdff-114">使用して、[アセンブリ リンカー (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)発行者ポリシー アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="6fdff-115">発行者ポリシー アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="6fdff-115">To create a publisher policy assembly</span></span>  
  
1. <span data-ttu-id="6fdff-116">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="6fdff-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="6fdff-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="6fdff-118">このコマンドでは。</span><span class="sxs-lookup"><span data-stu-id="6fdff-118">In this command:</span></span>  
  
    -   <span data-ttu-id="6fdff-119">*PublisherPolicyFile*引数は、発行者ポリシー ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="6fdff-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="6fdff-120">*PublisherPolicyAssemblyFile*引数は、このコマンドに起因する発行者ポリシー アセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="6fdff-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="6fdff-121">アセンブリ ファイルの名前は、形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdff-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="6fdff-122">**policy.**</span><span class="sxs-lookup"><span data-stu-id="6fdff-122">**policy.**</span></span> <span data-ttu-id="6fdff-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="6fdff-123">*majorNumber* **.**</span></span> <span data-ttu-id="6fdff-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="6fdff-124">*minorNumber* **.**</span></span> <span data-ttu-id="6fdff-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="6fdff-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="6fdff-126">*KeyPairFile*引数はキー ペアを含むファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="6fdff-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="6fdff-127">アセンブリと同じキーのペアで発行者ポリシー アセンブリに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdff-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="6fdff-128">*ProcessorArchitecture*引数は、プロセッサ固有のアセンブリの対象となるプラットフォームを識別します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6fdff-129">特定のプロセッサ アーキテクチャを対象とする機能は、.NET Framework version 2.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="6fdff-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="6fdff-130">次のコマンドと呼ばれる、発行者ポリシー アセンブリを作成する`policy.1.0.myAssembly`発行者ポリシー ファイルからと呼ばれる`pub.config`、内のキー ペアを使用して、アセンブリに厳密な名前を割り当てます、`sgKey.snk`ファイルを開き、アセンブリが、x86 を対象とするを指定します。プロセッサ アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="6fdff-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="6fdff-131">発行者ポリシー アセンブリは、それが適用されるアセンブリのプロセッサ アーキテクチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdff-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="6fdff-132">したがって、アセンブリがある場合、<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>の値<xref:System.Reflection.ProcessorArchitecture.MSIL>でそのアセンブリの発行者ポリシー アセンブリを作成する必要があります`/platform:anycpu`します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="6fdff-133">個別を提供する必要があります各プロセッサに固有のアセンブリの発行者ポリシー アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="6fdff-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="6fdff-134">このルールの結果は、アセンブリのプロセッサ アーキテクチャを変更するには、バージョン番号のメジャーまたはマイナー コンポーネントを変更する必要がありますが正しいプロセッサ アーキテクチャを持つ新しい発行者ポリシー アセンブリを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6fdff-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="6fdff-135">古い発行者ポリシー アセンブリは、アセンブリが別のプロセッサ アーキテクチャを持つアセンブリをサービスことはできません。</span><span class="sxs-lookup"><span data-stu-id="6fdff-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="6fdff-136">もう 1 つの結果は、プロセッサ アーキテクチャを常に指定されているため、.NET Framework の以前のバージョンを使用してコンパイルされたアセンブリの発行者ポリシー アセンブリを作成するバージョン 2.0 のリンカーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fdff-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6fdff-137">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="6fdff-138">使用して、[グローバル アセンブリ キャッシュ ツール (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6fdff-139">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加するには</span><span class="sxs-lookup"><span data-stu-id="6fdff-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1. <span data-ttu-id="6fdff-140">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="6fdff-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="6fdff-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="6fdff-142">次のコマンドは、追加`policy.1.0.myAssembly.dll`グローバル アセンブリ キャッシュにします。</span><span class="sxs-lookup"><span data-stu-id="6fdff-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6fdff-143">元の発行者ポリシー ファイルは、アセンブリと同じディレクトリにある場合を除き、発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加できません。</span><span class="sxs-lookup"><span data-stu-id="6fdff-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fdff-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fdff-144">See also</span></span>

- [<span data-ttu-id="6fdff-145">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="6fdff-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="6fdff-146">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="6fdff-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6fdff-147">構成ファイルを使用してアプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fdff-147">Configuring Apps by using Configuration Files</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="6fdff-148">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6fdff-148">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6fdff-149">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6fdff-149">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6fdff-150">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="6fdff-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)

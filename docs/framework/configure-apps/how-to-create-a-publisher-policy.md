---
title: '方法: 発行者ポリシーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 313af6046fda8dd8905e8bda4e8c4aec187ef8bf
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568403"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="63b55-102">方法: 発行者ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="63b55-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="63b55-103">アセンブリのベンダーは、アップグレードされたアセンブリに発行者ポリシーファイルを含めることによって、アプリケーションが新しいバージョンのアセンブリを使用する必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="63b55-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="63b55-104">発行者ポリシーファイルは、アセンブリリダイレクトとコードベース設定を指定し、アプリケーション構成ファイルと同じ形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="63b55-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="63b55-105">発行者ポリシーファイルは、アセンブリにコンパイルされ、グローバルアセンブリキャッシュに配置されます。</span><span class="sxs-lookup"><span data-stu-id="63b55-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="63b55-106">発行者ポリシーを作成するには、次の3つの手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="63b55-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="63b55-107">発行者ポリシーファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="63b55-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="63b55-108">発行者ポリシーアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="63b55-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="63b55-109">発行者ポリシーアセンブリをグローバルアセンブリキャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="63b55-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="63b55-110">発行元ポリシーのスキーマについては、「[アセンブリバージョンのリダイレクト](redirect-assembly-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b55-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="63b55-111">次の例は、あるバージョンの `myAssembly` を別のバージョンにリダイレクトする発行者ポリシーファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="63b55-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="63b55-112">コードベースを指定する方法については、「[アセンブリの場所の指定](specify-assembly-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b55-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="63b55-113">発行者ポリシーアセンブリを作成しています</span><span class="sxs-lookup"><span data-stu-id="63b55-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="63b55-114">[アセンブリリンカー (al.exe)](../tools/al-exe-assembly-linker.md)を使用して、発行者ポリシーアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="63b55-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="63b55-115">発行者ポリシーアセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="63b55-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="63b55-116">コマンドプロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="63b55-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="63b55-117">このコマンドでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="63b55-117">In this command:</span></span>

- <span data-ttu-id="63b55-118">`publisherPolicyFile` 引数は発行者ポリシーファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="63b55-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="63b55-119">`publisherPolicyAssemblyFile` 引数は、このコマンドの結果として生成される発行者ポリシーアセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="63b55-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="63b55-120">アセンブリファイル名は、次の形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="63b55-121">' majorNumber ' (' ポリシー.......................)</span><span class="sxs-lookup"><span data-stu-id="63b55-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="63b55-122">`keyPairFile` 引数は、キーペアを含むファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="63b55-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="63b55-123">アセンブリと発行者ポリシーアセンブリには、同じキーペアで署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="63b55-124">`processorArchitecture` 引数は、プロセッサ固有のアセンブリの対象となるプラットフォームを識別します。</span><span class="sxs-lookup"><span data-stu-id="63b55-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="63b55-125">特定のプロセッサアーキテクチャを対象とする機能は、.NET Framework 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="63b55-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="63b55-126">特定のプロセッサアーキテクチャを対象とする機能は、.NET Framework 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="63b55-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="63b55-127">次のコマンドは、`pub.config`という発行者ポリシーファイルから `policy.1.0.myAssembly` という発行者ポリシーアセンブリを作成し、`sgKey.snk` ファイルのキーペアを使用してアセンブリに厳密な名前を割り当て、アセンブリが x86 プロセッサアーキテクチャを対象とすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="63b55-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="63b55-128">発行者ポリシーアセンブリは、適用されるアセンブリのプロセッサアーキテクチャと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="63b55-129">したがって、アセンブリの <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> 値が <xref:System.Reflection.ProcessorArchitecture.MSIL>の場合は、そのアセンブリの発行者ポリシーアセンブリを `/platform:anycpu`で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="63b55-130">プロセッサ固有のアセンブリごとに個別の発行者ポリシーアセンブリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="63b55-131">このルールの結果として、アセンブリのプロセッサアーキテクチャを変更するには、バージョン番号のメジャーまたはマイナーコンポーネントを変更して、正しいプロセッサアーキテクチャを持つ新しい発行者ポリシーアセンブリを指定できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b55-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="63b55-132">アセンブリに異なるプロセッサアーキテクチャがある場合、古い発行者ポリシーアセンブリはアセンブリを処理できません。</span><span class="sxs-lookup"><span data-stu-id="63b55-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="63b55-133">また、バージョン2.0 リンカーを使用して、以前のバージョンの .NET Framework を使用してコンパイルされたアセンブリの発行者ポリシーアセンブリを作成することはできません。これは、常にプロセッサアーキテクチャを指定するためです。</span><span class="sxs-lookup"><span data-stu-id="63b55-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="63b55-134">発行者ポリシーアセンブリをグローバルアセンブリキャッシュに追加する</span><span class="sxs-lookup"><span data-stu-id="63b55-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="63b55-135">グローバル[アセンブリキャッシュツール (gacutil.exe)](../tools/gacutil-exe-gac-tool.md)を使用して、発行者ポリシーアセンブリをグローバルアセンブリキャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="63b55-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="63b55-136">発行者ポリシーアセンブリをグローバルアセンブリキャッシュに追加するには</span><span class="sxs-lookup"><span data-stu-id="63b55-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="63b55-137">コマンドプロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="63b55-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="63b55-138">次のコマンドは、`policy.1.0.myAssembly.dll` をグローバルアセンブリキャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="63b55-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="63b55-139">`/link` 引数で指定された元の発行者ポリシーファイルがアセンブリと同じディレクトリにある場合を除き、発行者ポリシーアセンブリをグローバルアセンブリキャッシュに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="63b55-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="63b55-140">参照</span><span class="sxs-lookup"><span data-stu-id="63b55-140">See also</span></span>

- [<span data-ttu-id="63b55-141">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="63b55-141">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="63b55-142">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="63b55-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="63b55-143">構成ファイルを使用したアプリの構成</span><span class="sxs-lookup"><span data-stu-id="63b55-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="63b55-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="63b55-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="63b55-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="63b55-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="63b55-146">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="63b55-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)

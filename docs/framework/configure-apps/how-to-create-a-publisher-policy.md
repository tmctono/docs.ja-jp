---
title: '方法: 発行者ポリシーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646054"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="6e1df-102">方法: 発行者ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6e1df-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="6e1df-103">アセンブリのベンダーは、アップグレードされたアセンブリに発行者ポリシー ファイルを含めることによって、アプリケーションが新しいバージョンのアセンブリを使用する必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e1df-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="6e1df-104">発行者ポリシー ファイルは、アセンブリ リダイレクトとコード ベースの設定を指定し、アプリケーション構成ファイルと同じ形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="6e1df-105">発行者ポリシー ファイルは、アセンブリにコンパイルされ、グローバル アセンブリ キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e1df-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="6e1df-106">発行者ポリシーの作成には、次の 3 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="6e1df-107">発行者ポリシー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="6e1df-108">発行者ポリシー アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="6e1df-109">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="6e1df-110">発行者ポリシーのスキーマについては、「アセンブリ[バージョンのリダイレクト」を参照してください](redirect-assembly-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1df-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="6e1df-111">次の例は、あるバージョンののを別の`myAssembly`バージョンにリダイレクトする発行者ポリシー ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e1df-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="6e1df-112">コード ベースを指定する方法については、「[アセンブリの場所を指定する](specify-assembly-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e1df-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="6e1df-113">発行者ポリシー アセンブリの作成</span><span class="sxs-lookup"><span data-stu-id="6e1df-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="6e1df-114">アセンブリ[リンカー (Al.exe) を](../tools/al-exe-assembly-linker.md)使用して、発行者ポリシー アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="6e1df-115">発行者ポリシー アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="6e1df-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="6e1df-116">コマンド プロンプトに、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="6e1df-117">このコマンドの説明:</span><span class="sxs-lookup"><span data-stu-id="6e1df-117">In this command:</span></span>

- <span data-ttu-id="6e1df-118">引数`publisherPolicyFile`は、発行者ポリシー ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="6e1df-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="6e1df-119">引数`publisherPolicyAssemblyFile`は、このコマンドの結果として作成される発行者ポリシー アセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="6e1df-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="6e1df-120">アセンブリ ファイル名は、次の形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="6e1df-121">'ポリシー.メジャーナンバー.マイナーナンバー.メインアセンブリ名.dll'</span><span class="sxs-lookup"><span data-stu-id="6e1df-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="6e1df-122">引数`keyPairFile`は、キーペアを含むファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="6e1df-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="6e1df-123">アセンブリと発行者ポリシー アセンブリに同じキー ペアで署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="6e1df-124">この`processorArchitecture`引数は、プロセッサ固有のアセンブリが対象とするプラットフォームを識別します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6e1df-125">特定のプロセッサ アーキテクチャを対象とする機能は、.NET Framework 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e1df-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="6e1df-126">特定のプロセッサ アーキテクチャを対象とする機能は、.NET Framework 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e1df-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="6e1df-127">次のコマンドは、 という名前の`policy.1.0.myAssembly`発行者ポリシー ファイルから呼`pub.config`び出される発行者ポリシー アセンブリを作成し、ファイル内のキー`sgKey.snk`ペアを使用してアセンブリに厳密な名前を割り当て、アセンブリが x86 プロセッサ アーキテクチャを対象とすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="6e1df-128">発行者ポリシー アセンブリは、適用先のアセンブリのプロセッサ アーキテクチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="6e1df-129">したがって、アセンブリの<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A><xref:System.Reflection.ProcessorArchitecture.MSIL>値が の場合、そのアセンブリの発行者ポリシー アセンブリは を使用`/platform:anycpu`して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="6e1df-130">プロセッサ固有のアセンブリごとに、個別の発行者ポリシー アセンブリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="6e1df-131">この規則の結果、アセンブリのプロセッサ アーキテクチャを変更するには、バージョン番号のメジャーまたはマイナーコンポーネントを変更して、新しい発行者ポリシー アセンブリに適切なプロセッサ アーキテクチャを提供できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1df-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="6e1df-132">アセンブリに別のプロセッサ アーキテクチャが設定されている場合、古い発行者ポリシー アセンブリはアセンブリにサービスを提供できません。</span><span class="sxs-lookup"><span data-stu-id="6e1df-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="6e1df-133">もう 1 つの結果として、バージョン 2.0 リンカーは、プロセッサ アーキテクチャを常に指定するため、以前のバージョンの .NET Framework を使用してコンパイルされたアセンブリの発行者ポリシー アセンブリを作成できません。</span><span class="sxs-lookup"><span data-stu-id="6e1df-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6e1df-134">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加する</span><span class="sxs-lookup"><span data-stu-id="6e1df-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="6e1df-135">グローバル[アセンブリ キャッシュ ツール (Gacutil.exe) を](../tools/gacutil-exe-gac-tool.md)使用して、発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6e1df-136">発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加するには</span><span class="sxs-lookup"><span data-stu-id="6e1df-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="6e1df-137">コマンド プロンプトに、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="6e1df-138">次のコマンドは`policy.1.0.myAssembly.dll`、グローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1df-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="6e1df-139">`/link`引数で指定された元の発行者ポリシー ファイルがアセンブリと同じディレクトリに存在しない限り、発行者ポリシー アセンブリをグローバル アセンブリ キャッシュに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e1df-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e1df-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e1df-140">See also</span></span>

- [<span data-ttu-id="6e1df-141">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="6e1df-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="6e1df-142">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="6e1df-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6e1df-143">構成ファイルを使用してアプリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6e1df-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="6e1df-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6e1df-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="6e1df-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6e1df-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="6e1df-146">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="6e1df-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)

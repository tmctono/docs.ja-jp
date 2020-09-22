---
title: '方法: Tlbimp.exe を使用してプライマリ相互運用機能アセンブリを生成する'
description: Windows SDK によって提供されるタイプ ライブラリ インポーター (Tlbimp.exe) を使用してプライマリ相互運用機能アセンブリを生成する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: 56ce10e0b6f9be988a06d44550cd3b9dc2efd188
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554157"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="f9ac7-103">方法: Tlbimp.exe を使用してプライマリ相互運用機能アセンブリを生成する</span><span class="sxs-lookup"><span data-stu-id="f9ac7-103">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="f9ac7-104">プライマリ相互運用機能アセンブリを生成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-104">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="f9ac7-105">Windows SDK によって提供される[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-105">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="f9ac7-106">プライマリ相互運用機能アセンブリを生成する最も簡単な方法は、[Tlbimp.exe (タイプ ライブラリ インポーター)](../tools/tlbimp-exe-type-library-importer.md) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-106">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="f9ac7-107">Tlbimp.exe は、次の保護機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-107">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="f9ac7-108">新規の相互運用機能アセンブリを作成するときには、その前に登録されている他のプライマリ相互運用機能アセンブリを調べて、入れ子になったタイプ ライブラリの参照がないかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-108">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="f9ac7-109">プライマリ相互運用機能アセンブリに厳密な名前が付くようにコンテナー名やファイル名を指定しない場合は、プライマリ相互運用機能アセンブリの生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-109">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="f9ac7-110">依存アセンブリへの参照を省略した場合は、プライマリ相互運用機能アセンブリの生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-110">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="f9ac7-111">プライマリ相互運用機能アセンブリではない依存アセンブリへの参照を追加した場合は、プライマリ相互運用機能アセンブリの生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-111">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="f9ac7-112">C# などの共通言語仕様 (CLS) に準拠した言語を使用して、ソース コードで手動によりプライマリ相互運用機能アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-112">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="f9ac7-113">この方法は、タイプ ライブラリが使用できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-113">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="f9ac7-114">厳密な名前でアセンブリに署名するには、暗号キー ペアが必要です。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-114">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="f9ac7-115">詳細については、「[キー ペアを作成する](../../standard/assembly/create-public-private-key-pair.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-115">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="f9ac7-116">Tlbimp.exe を使用してプライマリ相互運用機能アセンブリを生成する方法</span><span class="sxs-lookup"><span data-stu-id="f9ac7-116">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="f9ac7-117">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-117">At the command prompt, type:</span></span>

    <span data-ttu-id="f9ac7-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="f9ac7-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="f9ac7-119">このコマンドの *tlbfile* は COM タイプ ライブラリを含むファイル、*filename* はキー ペアを含むコンテナーまたはファイルの名前、*assemblyname* は厳密な名前で署名するアセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-119">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="f9ac7-120">プライマリ相互運用機能アセンブリは、他のプライマリ相互運用機能アセンブリのみを参照できます。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-120">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="f9ac7-121">アセンブリがサードパーティの COM タイプ ライブラリからタイプを参照する場合、プライマリ相互運用機能アセンブリを生成する前に、発行者からプライマリ相互運用機能アセンブリを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-121">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="f9ac7-122">発行者である場合は、参照元のプライマリ相互運用機能アセンブリを生成する前に、依存タイプ ライブラリのプライマリ相互運用機能アセンブリを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-122">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="f9ac7-123">元のタイプ ライブラリとは異なるバージョン番号の依存プライマリ相互運用機能アセンブリは、現在のディレクトリにインストールされている場合、検出できません。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-123">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="f9ac7-124">依存プライマリ相互運用機能アセンブリを Windows レジストリに登録するか、または **/reference** オプションを使用して、Tlbimp.exe が依存 DLL を検出できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-124">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="f9ac7-125">複数のバージョンのタイプ ライブラリをラップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-125">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="f9ac7-126">手順については、「[方法:複数のバージョンのタイプ ライブラリをラップする](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-126">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="f9ac7-127">例</span><span class="sxs-lookup"><span data-stu-id="f9ac7-127">Example</span></span>

<span data-ttu-id="f9ac7-128">次の例は、COM タイプ ライブラリ `LibUtil.tlb` をインポートし、アセンブリ `LibUtil.dll` にキー ファイル `CompanyA.snk` を使用して厳密な名前で署名します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-128">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="f9ac7-129">この例では、特定の名前空間名を省略することにより、既定の名前空間 `LibUtil` を生成します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-129">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="f9ac7-130">名前を (*VendorName*.*LibraryName* の名前付けガイドラインを使用して) より分かりやすくするために、次の例では既定のアセンブリ ファイル名と名前空間名をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-130">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="f9ac7-131">次の例では、`CompanyA.LibUtil.dll` を参照する `MyLib.tlb` をインポートし、アセンブリ `CompanyB.MyLib.dll` にキー ファイル `CompanyB.snk` を使用して厳密な名前で署名します。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-131">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="f9ac7-132">名前空間 `CompanyB.MyLib` は、既定の名前空間名をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f9ac7-132">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="f9ac7-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9ac7-133">See also</span></span>

- [<span data-ttu-id="f9ac7-134">方法: プライマリ相互運用機能アセンブリを登録する</span><span class="sxs-lookup"><span data-stu-id="f9ac7-134">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)

---
title: アセンブリのバージョン管理
ms.date: 08/20/2019
helpviewer_keywords:
- informational versions
- version numbers, assemblies
- assemblies [.NET Framework], versioning
- resolving assembly binding requests
- versioning, assemblies
ms.assetid: 775ad4fb-914f-453c-98ef-ce1089b6f903
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83797ba0934be1c29a3bf9ff37dde430477cfe23
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972511"
---
# <a name="assembly-versioning"></a><span data-ttu-id="43aee-102">アセンブリのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="43aee-102">Assembly versioning</span></span>
<span data-ttu-id="43aee-103">共通言語ランタイムを使用するアセンブリのバージョン管理は、すべてアセンブリ レベルで行われます。</span><span class="sxs-lookup"><span data-stu-id="43aee-103">All versioning of assemblies that use the common language runtime is done at the assembly level.</span></span> <span data-ttu-id="43aee-104">アセンブリの特定のバージョン、および依存する各アセンブリのバージョンは、アセンブリのマニフェストに記録されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-104">The specific version of an assembly and the versions of dependent assemblies are recorded in the assembly's manifest.</span></span> <span data-ttu-id="43aee-105">ランタイムの既定のバージョン ポリシーは、構成ファイル (アプリケーション構成ファイル、発行者ポリシー ファイル、コンピューター管理者の構成ファイル) に指定した明示的なバージョン ポリシーでオーバーライドされない限り、アプリケーションが作成およびテストされた時点のバージョンの場合にだけそのアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="43aee-105">The default version policy for the runtime is that applications run only with the versions they were built and tested with, unless overridden by explicit version policy in configuration files (the application configuration file, the publisher policy file, and the computer's administrator configuration file).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43aee-106">バージョン管理は、厳密な名前付きのアセンブリに対してだけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-106">Versioning is done only on assemblies with strong names.</span></span>  
  
 <span data-ttu-id="43aee-107">ランタイムは、アセンブリ バインディング要求を解決するために、いくつかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43aee-107">The runtime performs several steps to resolve an assembly binding request:</span></span>  
  
1. <span data-ttu-id="43aee-108">元のアセンブリ参照を確認し、バインド先のアセンブリのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="43aee-108">Checks the original assembly reference to determine the version of the assembly to be bound.</span></span>  
  
2. <span data-ttu-id="43aee-109">バージョン ポリシーを適用するために利用できる構成ファイルをすべてチェックします。</span><span class="sxs-lookup"><span data-stu-id="43aee-109">Checks for all applicable configuration files to apply version policy.</span></span>  
  
3. <span data-ttu-id="43aee-110">元のアセンブリ参照と、構成ファイルで指定されているリダイレクトから正しいアセンブリを判断し、呼び出し元のアセンブリにバインドされるバージョンを判断します。</span><span class="sxs-lookup"><span data-stu-id="43aee-110">Determines the correct assembly from the original assembly reference and any redirection specified in the configuration files, and determines the version that should be bound to the calling assembly.</span></span>  
  
4. <span data-ttu-id="43aee-111">グローバル アセンブリ キャッシュと、構成ファイルで指定されたコードベースをチェックした後、「[ランタイムがアセンブリを検索する方法](../../framework/deployment/how-the-runtime-locates-assemblies.md)」に説明されているプローブ規則を使用して、アプリケーションのディレクトリとサブディレクトリをチェックします。</span><span class="sxs-lookup"><span data-stu-id="43aee-111">Checks the global assembly cache, codebases specified in configuration files, and then checks the application's directory and subdirectories using the probing rules explained in [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="43aee-112">これらの手順を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="43aee-112">The following illustration shows these steps:</span></span>  
  
 ![アセンブリ バインディング要求の解決手順を示す図。](./media/versioning/resolve-assembly-binding-request.gif)
  
 <span data-ttu-id="43aee-114">アプリケーションの設定の詳細については、「[アプリの構成](../../../docs/framework/configure-apps/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43aee-114">For more information about configuring applications, see [Configure apps](../../../docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="43aee-115">バインド ポリシーの詳細については、「[ランタイムがアセンブリを検索する方法](../../framework/deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43aee-115">For more information about binding policy, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="43aee-116">バージョン情報</span><span class="sxs-lookup"><span data-stu-id="43aee-116">Version information</span></span>  
 <span data-ttu-id="43aee-117">各アセンブリは、次の 2 種類の形でバージョン情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="43aee-117">Each assembly has two distinct ways of expressing version information:</span></span>  
  
- <span data-ttu-id="43aee-118">アセンブリのバージョン番号。アセンブリ名やカルチャ情報と共に、アセンブリの識別子を構成します。</span><span class="sxs-lookup"><span data-stu-id="43aee-118">The assembly's version number, which, together with the assembly name and culture information, is part of the assembly's identity.</span></span> <span data-ttu-id="43aee-119">この番号は、バージョン ポリシーを強制適用するためにランタイムで使用され、実行時の型解決プロセスで重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="43aee-119">This number is used by the runtime to enforce version policy and plays a key part in the type resolution process at run time.</span></span>  
  
- <span data-ttu-id="43aee-120">補足バージョン。これは、情報の提供だけを目的とした、追加のバージョン情報を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="43aee-120">An informational version, which is a string that represents additional version information included for informational purposes only.</span></span>  
  
### <a name="assembly-version-number"></a><span data-ttu-id="43aee-121">アセンブリのバージョン番号</span><span class="sxs-lookup"><span data-stu-id="43aee-121">Assembly version number</span></span>  
 <span data-ttu-id="43aee-122">各アセンブリの識別子には、バージョン番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43aee-122">Each assembly has a version number as part of its identity.</span></span> <span data-ttu-id="43aee-123">そのため、バージョン番号が異なる 2 つのアセンブリは、ランタイムでは、まったく異なるアセンブリと見なされます。</span><span class="sxs-lookup"><span data-stu-id="43aee-123">As such, two assemblies that differ by version number are considered by the runtime to be completely different assemblies.</span></span> <span data-ttu-id="43aee-124">このバージョン番号は、次に示す形式の 4 つの部分から成る文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-124">This version number is physically represented as a four-part string with the following format:</span></span>  
  
 <span data-ttu-id="43aee-125">\<*メジャー バージョン*>.\<*マイナー バージョン*>.\<*ビルド番号*>.\<*改訂番号*></span><span class="sxs-lookup"><span data-stu-id="43aee-125">\<*major version*>.\<*minor version*>.\<*build number*>.\<*revision*></span></span>  
  
 <span data-ttu-id="43aee-126">たとえばバージョン 1.5.1254.0 の場合、1 はメジャー バージョン、5 はマイナー バージョン、1254 はビルド番号、0 はリビジョン番号を表します。</span><span class="sxs-lookup"><span data-stu-id="43aee-126">For example, version 1.5.1254.0 indicates 1 as the major version, 5 as the minor version, 1254 as the build number, and 0 as the revision number.</span></span>  
  
 <span data-ttu-id="43aee-127">バージョン番号は、アセンブリ名や公開キーなどのほかの識別子情報や、アプリケーションに関連付けられているほかの複数のアセンブリの関係や識別子に関する情報と共に、アセンブリ マニフェストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-127">The version number is stored in the assembly manifest along with other identity information, including the assembly name and public key, as well as information on relationships and identities of other assemblies connected with the application.</span></span>  
  
 <span data-ttu-id="43aee-128">アセンブリの作成時に、開発ツールによって、アセンブリ マニフェストで参照される各アセンブリについての依存情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-128">When an assembly is built, the development tool records dependency information for each assembly that is referenced in the assembly manifest.</span></span> <span data-ttu-id="43aee-129">ランタイムは、これらのバージョン番号と、管理者、アプリケーション、または発行者が設定した構成情報を組み合わせて使用し、参照先アセンブリの正しいバージョンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="43aee-129">The runtime uses these version numbers, in conjunction with configuration information set by an administrator, an application, or a publisher, to load the proper version of a referenced assembly.</span></span>  
  
 <span data-ttu-id="43aee-130">バージョン管理の目的のため、ランタイムでは、通常の名前の付いたアセンブリと、厳密な名前の付いたアセンブリが区別されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-130">The runtime distinguishes between regular and strong-named assemblies for the purposes of versioning.</span></span> <span data-ttu-id="43aee-131">バージョンのチェックは、厳密な名前付きのアセンブリに対してだけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-131">Version checking only occurs with strong-named assemblies.</span></span>  
  
 <span data-ttu-id="43aee-132">バージョン バインド ポリシーの指定については、「[アプリの構成](../../../docs/framework/configure-apps/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43aee-132">For information about specifying version binding policies, see [Configure apps](../../../docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="43aee-133">ランタイムがバージョン情報を使用して特定のアセンブリを見つけ出す方法については、「[ランタイムがアセンブリを検索する方法](../../framework/deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43aee-133">For information about how the runtime uses version information to find a particular assembly, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
### <a name="assembly-informational-version"></a><span data-ttu-id="43aee-134">アセンブリの情報バージョン</span><span class="sxs-lookup"><span data-stu-id="43aee-134">Assembly informational version</span></span>  
 <span data-ttu-id="43aee-135">補足バージョンは、情報の提供だけを目的として、追加のバージョン情報をアセンブリに追加するための文字列です。この情報は実行時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="43aee-135">The informational version is a string that attaches additional version information to an assembly for informational purposes only; this information is not used at run time.</span></span> <span data-ttu-id="43aee-136">補足バージョンはテキスト ベースで、その製品のマーケティング資料、パッケージ、あるいは製品名に対応するものであり、実行時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="43aee-136">The text-based informational version corresponds to the product's marketing literature, packaging, or product name and is not used by the runtime.</span></span> <span data-ttu-id="43aee-137">たとえば、補足バージョンの例は "共通言語ランタイム バージョン 1.0" や "NET Control SP 2" などになります。</span><span class="sxs-lookup"><span data-stu-id="43aee-137">For example, an informational version could be "Common Language Runtime version 1.0" or "NET Control SP 2".</span></span> <span data-ttu-id="43aee-138">Microsoft Windows のファイル プロパティ ダイアログの [バージョン] タブでは、この情報は [製品バージョン] という項目に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-138">On the Version tab of the file properties dialog in Microsoft Windows, this information appears in the item "Product Version".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43aee-139">任意のテキストを指定できますが、文字列がアセンブリのバージョン番号で使用されている形式でなかったり、形式が正しくてもワイルドカードを含んでいたりすると、コンパイルで警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-139">Although you can specify any text, a warning message appears on compilation if the string is not in the format used by the assembly version number, or if it is in that format but contains wildcards.</span></span> <span data-ttu-id="43aee-140">この警告は、実行には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="43aee-140">This warning is harmless.</span></span>  
  
 <span data-ttu-id="43aee-141">補足バージョンは、カスタム属性 <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType> を使って表されます。</span><span class="sxs-lookup"><span data-stu-id="43aee-141">The informational version is represented using the custom attribute <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43aee-142">補足バージョン属性の詳細については、「[アセンブリ属性の設定](set-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43aee-142">For more information about the informational version attribute, see [Set assembly attributes](set-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43aee-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="43aee-143">See also</span></span>

- [<span data-ttu-id="43aee-144">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="43aee-144">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="43aee-145">アプリの構成</span><span class="sxs-lookup"><span data-stu-id="43aee-145">Configure apps</span></span>](../../framework/configure-apps/index.md)
- [<span data-ttu-id="43aee-146">アセンブリ属性の設定</span><span class="sxs-lookup"><span data-stu-id="43aee-146">Set assembly attributes</span></span>](set-attributes.md)
- [<span data-ttu-id="43aee-147">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="43aee-147">Assemblies in .NET</span></span>](index.md)

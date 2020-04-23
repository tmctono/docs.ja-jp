---
title: C# の予約済み属性:グローバル属性
ms.date: 04/09/2020
description: 属性は、プログラムのセマンティクスをさらに理解するためにコンパイラから使用されるメタデータを提供します
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389806"
---
# <a name="reserved-attributes-assembly-level-attributes"></a><span data-ttu-id="6a6e1-103">予約済みの属性:アセンブリ レベルの属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-103">Reserved attributes: Assembly level attributes</span></span>

<span data-ttu-id="6a6e1-104">ほとんどの属性は、クラスやメソッドなど、特定の言語要素に適用されます。ただし、属性の中にはグローバルなものがあり、アセンブリまたはモジュール全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-104">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="6a6e1-105">たとえば、<xref:System.Reflection.AssemblyVersionAttribute> 属性は、次のように、バージョン情報をアセンブリに埋め込むときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-105">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

<span data-ttu-id="6a6e1-106">ソース コードでは、グローバル属性は、トップレベルの `using` ディレクティブより後、型、モジュール、または名前空間の宣言より前に指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-106">Global attributes appear in the source code after any top level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="6a6e1-107">グローバル属性は複数のソース ファイルに指定できますが、それらのファイルは、1 つのコンパイル パスでコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-107">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="6a6e1-108">Visual Studio によって、.NET Framework プロジェクトの AssemblyInfo.cs ファイルにグローバル属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-108">Visual Studio adds global attributes to the AssemblyInfo.cs file in .NET Framework projects.</span></span> <span data-ttu-id="6a6e1-109">これらの属性は、.NET Core プロジェクトには追加されません。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-109">These attributes aren't added to .NET Core projects.</span></span>

<span data-ttu-id="6a6e1-110">アセンブリの属性は、アセンブリに関する情報を提供する値です。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-110">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="6a6e1-111">これらは次のカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-111">They fall into the following categories:</span></span>

- <span data-ttu-id="6a6e1-112">アセンブリ ID 属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-112">Assembly identity attributes</span></span>
- <span data-ttu-id="6a6e1-113">情報属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-113">Informational attributes</span></span>
- <span data-ttu-id="6a6e1-114">アセンブリ マニフェスト属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-114">Assembly manifest attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="6a6e1-115">アセンブリ ID 属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-115">Assembly identity attributes</span></span>

<span data-ttu-id="6a6e1-116">アセンブリの ID は、名前、バージョン、カルチャの 3 つの属性によって識別されます (適用できる場合は厳密な名前も使用されます)。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-116">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="6a6e1-117">アセンブリの完全な名前を形成するこれらの属性は、コード内でアセンブリを参照するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-117">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="6a6e1-118">アセンブリのバージョンとカルチャは、属性を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-118">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="6a6e1-119">ただし、名前の値は、コンパイラ、[[アセンブリ情報] ダイアログ ボックス](/visualstudio/ide/reference/assembly-information-dialog-box)の Visual Studio IDE、またはアセンブリ リンカー (Al.exe) (アセンブリの作成時) によって設定されます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-119">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created.</span></span> <span data-ttu-id="6a6e1-120">アセンブリ名は、アセンブリ マニフェストに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-120">The assembly name is based on the assembly manifest.</span></span> <span data-ttu-id="6a6e1-121"><xref:System.Reflection.AssemblyFlagsAttribute> 属性は、アセンブリの複数のコピーが共存できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-121">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="6a6e1-122">次の表に ID 属性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-122">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="6a6e1-123">属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-123">Attribute</span></span>|<span data-ttu-id="6a6e1-124">目的</span><span class="sxs-lookup"><span data-stu-id="6a6e1-124">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="6a6e1-125">アセンブリのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-125">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="6a6e1-126">アセンブリがサポートするカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-126">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="6a6e1-127">同じコンピューター、同じプロセス、または同じアプリケーション ドメインでの side-by-side 実行をアセンブリがサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-127">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

## <a name="informational-attributes"></a><span data-ttu-id="6a6e1-128">情報属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-128">Informational attributes</span></span>

<span data-ttu-id="6a6e1-129">情報属性は、追加の会社情報または製品情報をアセンブリに指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-129">You use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="6a6e1-130">次の表は、<xref:System.Reflection?displayProperty=nameWithType> 名前空間で定義されている情報属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-130">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="6a6e1-131">属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-131">Attribute</span></span>|<span data-ttu-id="6a6e1-132">目的</span><span class="sxs-lookup"><span data-stu-id="6a6e1-132">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="6a6e1-133">アセンブリ マニフェストの製品名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-133">Specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="6a6e1-134">アセンブリ マニフェストの商標を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-134">Specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="6a6e1-135">アセンブリ マニフェストの情報バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-135">Specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="6a6e1-136">アセンブリ マニフェストの会社名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-136">Specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="6a6e1-137">アセンブリ マニフェストの著作権を指定するカスタム属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-137">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="6a6e1-138">Win32 ファイル バージョン リソースの特定のバージョン番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-138">Sets a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="6a6e1-139">アセンブリが共通言語仕様 (CLS) に準拠しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-139">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="6a6e1-140">アセンブリ マニフェスト属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-140">Assembly manifest attributes</span></span>

<span data-ttu-id="6a6e1-141">アセンブリ マニフェスト属性を使用すると、アセンブリ マニフェストの情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-141">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="6a6e1-142">属性には、タイトル、説明、既定のエイリアス、および構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-142">The attributes include title, description, default alias, and configuration.</span></span> <span data-ttu-id="6a6e1-143">次の表は、<xref:System.Reflection?displayProperty=nameWithType> 名前空間で定義されているアセンブリ マニフェスト属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-143">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="6a6e1-144">属性</span><span class="sxs-lookup"><span data-stu-id="6a6e1-144">Attribute</span></span>|<span data-ttu-id="6a6e1-145">目的</span><span class="sxs-lookup"><span data-stu-id="6a6e1-145">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="6a6e1-146">アセンブリ マニフェストのアセンブリ タイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-146">Specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="6a6e1-147">アセンブリ マニフェストのアセンブリの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-147">Specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="6a6e1-148">アセンブリ マニフェストのアセンブリ構成 (小売、デバッグなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-148">Specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="6a6e1-149">アセンブリ マニフェストのわかりやすい既定の別名を定義します。</span><span class="sxs-lookup"><span data-stu-id="6a6e1-149">Defines a friendly default alias for an assembly manifest</span></span>|

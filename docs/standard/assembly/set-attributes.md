---
title: アセンブリ属性を設定する
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: fe003a6c74da59c1cb47a0f12a8597143916e320
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138642"
---
# <a name="set-assembly-attributes"></a><span data-ttu-id="118fb-102">アセンブリ属性を設定する</span><span class="sxs-lookup"><span data-stu-id="118fb-102">Set assembly attributes</span></span>

<span data-ttu-id="118fb-103">アセンブリの属性は、アセンブリに関する情報を提供する値です。</span><span class="sxs-lookup"><span data-stu-id="118fb-103">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="118fb-104">属性は、次のような情報に分類されます。</span><span class="sxs-lookup"><span data-stu-id="118fb-104">The attributes are divided into the following sets of information:</span></span>

- <span data-ttu-id="118fb-105">アセンブリ ID 属性</span><span class="sxs-lookup"><span data-stu-id="118fb-105">Assembly identity attributes</span></span>

- <span data-ttu-id="118fb-106">情報属性</span><span class="sxs-lookup"><span data-stu-id="118fb-106">Informational attributes</span></span>

- <span data-ttu-id="118fb-107">アセンブリ マニフェスト属性</span><span class="sxs-lookup"><span data-stu-id="118fb-107">Assembly manifest attributes</span></span>

- <span data-ttu-id="118fb-108">厳密な名前の属性</span><span class="sxs-lookup"><span data-stu-id="118fb-108">Strong name attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="118fb-109">アセンブリ ID 属性</span><span class="sxs-lookup"><span data-stu-id="118fb-109">Assembly identity attributes</span></span>

<span data-ttu-id="118fb-110">アセンブリは、名前、バージョン、およびカルチャの 3 つの属性と、適用される場合は厳密な名前によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="118fb-110">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="118fb-111">これらの属性は、アセンブリの完全な名前を形成し、コード内でアセンブリを参照するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="118fb-111">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="118fb-112">属性を使用して、アセンブリのバージョンとのカルチャを設定できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-112">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="118fb-113">コンパイラまたは [アセンブリ リンカー (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) は、アセンブリの作成時に、アセンブリ マニフェストを含むファイルに基づいて名前の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="118fb-113">The compiler or the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>

<span data-ttu-id="118fb-114">バージョン属性とカルチャ属性について次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="118fb-114">The following table describes the version and culture attributes.</span></span>

|<span data-ttu-id="118fb-115">アセンブリ ID 属性</span><span class="sxs-lookup"><span data-stu-id="118fb-115">Assembly identity attribute</span></span>|<span data-ttu-id="118fb-116">説明</span><span class="sxs-lookup"><span data-stu-id="118fb-116">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="118fb-117">アセンブリがサポートするカルチャを示す列挙フィールド。</span><span class="sxs-lookup"><span data-stu-id="118fb-117">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="118fb-118">アセンブリがカルチャに依存しないように指定することもできます。その場合は、アセンブリが既定のカルチャのリソースを格納することを意味します。</span><span class="sxs-lookup"><span data-stu-id="118fb-118">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="118fb-119">**注:** ランタイムは、カルチャ属性が null に設定されていないすべてのアセンブリを、サテライト アセンブリとして扱います。</span><span class="sxs-lookup"><span data-stu-id="118fb-119">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="118fb-120">そのようなアセンブリには、サテライト アセンブリ バインディング規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="118fb-120">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="118fb-121">詳細については、「[ランタイムがアセンブリを検索する方法](../../framework/deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="118fb-121">For more information, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="118fb-122">アセンブリを並列で実行できるかどうかなどのアセンブリ属性を設定する値。</span><span class="sxs-lookup"><span data-stu-id="118fb-122">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="118fb-123">*major*.*minor*.*build*.*revision* 形式の数値 (たとえば、2.4.0.0)。</span><span class="sxs-lookup"><span data-stu-id="118fb-123">Numeric value in the format *major*.*minor*.*build*.*revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="118fb-124">共通言語ランタイムは、この値を使用して、厳密な名前付きアセンブリでのバインディング操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="118fb-124">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="118fb-125">**注:** <xref:System.Reflection.AssemblyInformationalVersionAttribute> 属性がアセンブリに適用されない場合、<xref:System.Reflection.AssemblyVersionAttribute> 属性によって指定されたバージョン番号が <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>、<xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>、および <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> の各プロパティで使用されます。</span><span class="sxs-lookup"><span data-stu-id="118fb-125">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|

<span data-ttu-id="118fb-126">バージョン属性とカルチャ属性をアセンブリに適用する方法を次のコード例で示します。</span><span class="sxs-lookup"><span data-stu-id="118fb-126">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a><span data-ttu-id="118fb-127">情報属性</span><span class="sxs-lookup"><span data-stu-id="118fb-127">Informational attributes</span></span>

<span data-ttu-id="118fb-128">情報属性は、追加の会社情報または製品情報をアセンブリに指定する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-128">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="118fb-129">アセンブリに適用できる情報属性について、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="118fb-129">The following table describes the informational attributes you can apply to an assembly.</span></span>

|<span data-ttu-id="118fb-130">情報属性</span><span class="sxs-lookup"><span data-stu-id="118fb-130">Informational attribute</span></span>|<span data-ttu-id="118fb-131">説明</span><span class="sxs-lookup"><span data-stu-id="118fb-131">Description</span></span>|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="118fb-132">会社名を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-132">String value specifying a company name.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="118fb-133">著作権情報を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-133">String value specifying copyright information.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="118fb-134">Win32 ファイル バージョン番号を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-134">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="118fb-135">通常、この属性の既定値はアセンブリ バージョンです。</span><span class="sxs-lookup"><span data-stu-id="118fb-135">This normally defaults to the assembly version.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="118fb-136">完全な製品バージョン番号など、共通言語ランタイムによって使用されないバージョン情報を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-136">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="118fb-137">**注:** この属性をアセンブリに適用した場合は、<xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> プロパティを使用して、この属性で指定された文字列を実行時に取得できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-137">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="118fb-138">この文字列は、<xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> プロパティと <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> プロパティによって提供されるパスとレジストリ キーにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="118fb-138">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="118fb-139">製品情報を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-139">String value specifying product information.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="118fb-140">商標情報を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-140">String value specifying trademark information.</span></span>|

<span data-ttu-id="118fb-141">これらの属性は、アセンブリの [Windows のプロパティ] ページに表示できます。また、独自の Win32 リソース ファイルを指定するために、 **/win32res** コンパイラ オプションを使用してこれらの属性をオーバーライドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="118fb-141">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="118fb-142">アセンブリ マニフェスト属性</span><span class="sxs-lookup"><span data-stu-id="118fb-142">Assembly manifest attributes</span></span>

<span data-ttu-id="118fb-143">アセンブリ マニフェストの属性を使用すると、タイトル、説明、既定のエイリアス、構成などの情報をアセンブリ マニフェストに指定できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-143">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="118fb-144">アセンブリ マニフェスト属性について、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="118fb-144">The following table describes the assembly manifest attributes.</span></span>

|<span data-ttu-id="118fb-145">アセンブリ マニフェスト属性</span><span class="sxs-lookup"><span data-stu-id="118fb-145">Assembly manifest attribute</span></span>|<span data-ttu-id="118fb-146">説明</span><span class="sxs-lookup"><span data-stu-id="118fb-146">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="118fb-147">Retail (製品版) や Debug (デバッグ) など、アセンブリの構成を示す文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-147">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="118fb-148">ランタイムはこの値を使用しません。</span><span class="sxs-lookup"><span data-stu-id="118fb-148">The runtime does not use this value.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="118fb-149">アセンブリの参照に使用する既定のエイリアスを指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-149">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="118fb-150">この値は、アセンブリ自体の名前がフレンドリ名ではない場合 (GUID 値の場合など) に、フレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="118fb-150">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="118fb-151">この値は、完全なアセンブリ名の短い形式としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-151">This value can also be used as a short form of the full assembly name.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="118fb-152">アセンブリの特性と目的を要約した短い説明を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-152">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="118fb-153">アセンブリのフレンドリ名を指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-153">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="118fb-154">たとえば、*comdlg* という名前のアセンブリに Microsoft Common Dialog Control というタイトルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="118fb-154">For example, an assembly named *comdlg* might have the title Microsoft Common Dialog Control.</span></span>|

## <a name="strong-name-attributes"></a><span data-ttu-id="118fb-155">厳密な名前の属性</span><span class="sxs-lookup"><span data-stu-id="118fb-155">Strong name attributes</span></span>

<span data-ttu-id="118fb-156">厳密な名前の属性を使用すると、アセンブリに厳密な名前を設定できます。</span><span class="sxs-lookup"><span data-stu-id="118fb-156">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="118fb-157">厳密な名前の属性について、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="118fb-157">The following table describes the strong name attributes.</span></span>

|<span data-ttu-id="118fb-158">厳密な名前の属性</span><span class="sxs-lookup"><span data-stu-id="118fb-158">Strong name attribute</span></span>|<span data-ttu-id="118fb-159">説明</span><span class="sxs-lookup"><span data-stu-id="118fb-159">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="118fb-160">遅延署名が使用されていることを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="118fb-160">Boolean value indicating that delay signing is being used.</span></span>|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="118fb-161">この属性のコンストラクターにパラメーターとして渡される公開キー (遅延署名を使用する場合) または公開キーと秘密キーの両方を格納するファイルの名前を示す文字列値。</span><span class="sxs-lookup"><span data-stu-id="118fb-161">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="118fb-162">なお、このファイル名は、ソース ファイルのパスではなく出力ファイルのパスから見た相対パス名 ( *.exe* または *.dll*) です。</span><span class="sxs-lookup"><span data-stu-id="118fb-162">Note that the file name is relative to the output file path (the *.exe* or *.dll*), not the source file path.</span></span>|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="118fb-163">この属性のコンストラクターにパラメーターとして渡されるキー ペアを格納するキー コンテナーを示します。</span><span class="sxs-lookup"><span data-stu-id="118fb-163">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|

<span data-ttu-id="118fb-164">次のコード例では、遅延署名を使用し、*myKey.snk* という公開キー ファイルを使用する厳密な名前付きアセンブリを作成する場合に適用する属性を示します。</span><span class="sxs-lookup"><span data-stu-id="118fb-164">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called *myKey.snk*.</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a><span data-ttu-id="118fb-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="118fb-165">See also</span></span>

- [<span data-ttu-id="118fb-166">アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="118fb-166">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="118fb-167">アセンブリを使用したプログラム</span><span class="sxs-lookup"><span data-stu-id="118fb-167">Program with assemblies</span></span>](program.md)

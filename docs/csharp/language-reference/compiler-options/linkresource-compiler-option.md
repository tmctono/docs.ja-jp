---
title: -linkresource (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 454915454f3faf15933257f3e3e221afec51d0ee
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606755"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="ce3e2-102">-linkresource (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="ce3e2-102">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="ce3e2-103">.NET Framework のリソースへのリンクを出力ファイルに作成します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="ce3e2-104">リソース ファイルが出力ファイルに追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="ce3e2-105">これに対し、[-resource](./resource-compiler-option.md) オプションはリソース ファイルを出力ファイルに埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-105">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3e2-106">構文</span><span class="sxs-lookup"><span data-stu-id="ce3e2-106">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce3e2-107">引数</span><span class="sxs-lookup"><span data-stu-id="ce3e2-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="ce3e2-108">アセンブリからリンクする .NET Framework のリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="ce3e2-109">`identifier` (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ce3e2-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="ce3e2-110">リソースの論理名。リソースを読み込むために使われる名前です。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="ce3e2-111">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="ce3e2-112">`accessibility-modifier` (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ce3e2-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="ce3e2-113">リソースのアクセシビリティ。パブリックまたはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="ce3e2-114">既定値はパブリックです。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce3e2-115">解説</span><span class="sxs-lookup"><span data-stu-id="ce3e2-115">Remarks</span></span>  
 <span data-ttu-id="ce3e2-116">既定では、リンクされたリソースは、C# コンパイラで作成されるときにアセンブリ内でパブリックになります。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="ce3e2-117">リソースをプライベートにするには、アクセシビリティ修飾子として `private` を指定します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="ce3e2-118">`public` または `private` 以外の他の修飾子は許可されません。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="ce3e2-119">**-linkresource** には、 **-target:module** 以外のいずれかの [-target](./target-compiler-option.md) オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-119">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="ce3e2-120">`filename` が [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) や開発環境などで作成された .NET Framework リソース ファイルである場合は、<xref:System.Resources> 名前空間のメンバーを使ってそのファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="ce3e2-121">詳細については、<xref:System.Resources.ResourceManager?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce3e2-122">それ以外のすべてのリソースに対しては、<xref:System.Reflection.Assembly> クラスの `GetManifestResource` メソッドを使用して、実行時にリソースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-122">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="ce3e2-123">`filename` で指定するファイルはどのような形式でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="ce3e2-124">たとえば、ネイティブ DLL をアセンブリの一部にすることで、グローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージド コードからアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="ce3e2-125">以下の例の 2 番目で、その方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="ce3e2-126">同じことをアセンブリ リンカーで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="ce3e2-127">以下の例の 3 番目で、その方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="ce3e2-128">詳しくは、「[Al.exe (アセンブリ リンカー)](../../../framework/tools/al-exe-assembly-linker.md)」および「[アセンブリとグローバル アセンブリ キャッシュの使用](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-128">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="ce3e2-129">**-linkres** は **-linkresource** の省略形式です。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-129">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="ce3e2-130">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce3e2-131">例</span><span class="sxs-lookup"><span data-stu-id="ce3e2-131">Example</span></span>  
 <span data-ttu-id="ce3e2-132">`in.cs` をコンパイルして、リソース ファイル `rf.resource` にリンクします。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="ce3e2-133">例</span><span class="sxs-lookup"><span data-stu-id="ce3e2-133">Example</span></span>  
 <span data-ttu-id="ce3e2-134">`A.cs` をコンパイルして DLL を作成し、ネイティブ DLL N.dll にリンクして、出力をグローバル アセンブリ キャッシュ (GAC) に配置します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="ce3e2-135">この例では、A.dll と N.dll の両方を GAC に置きます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="ce3e2-136">例</span><span class="sxs-lookup"><span data-stu-id="ce3e2-136">Example</span></span>  
 <span data-ttu-id="ce3e2-137">この例では、前の例と同じことを行いますが、アセンブリ リンカー オプションを使います。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce3e2-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce3e2-138">See also</span></span>

- [<span data-ttu-id="ce3e2-139">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="ce3e2-139">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ce3e2-140">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="ce3e2-140">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="ce3e2-141">アセンブリとグローバル アセンブリ キャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="ce3e2-141">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="ce3e2-142">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="ce3e2-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

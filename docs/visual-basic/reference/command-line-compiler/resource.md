---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: a781d543dd32ffb3d0ac0b11c544dbfd8cd5d806
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348568"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="66fc2-102">-リソース (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66fc2-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="66fc2-103">マネージド リソースをアセンブリに埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="66fc2-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66fc2-104">構文</span><span class="sxs-lookup"><span data-stu-id="66fc2-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="66fc2-105">または</span><span class="sxs-lookup"><span data-stu-id="66fc2-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="66fc2-106">引数</span><span class="sxs-lookup"><span data-stu-id="66fc2-106">Arguments</span></span>  
  
|<span data-ttu-id="66fc2-107">用語</span><span class="sxs-lookup"><span data-stu-id="66fc2-107">Term</span></span>|<span data-ttu-id="66fc2-108">Definition</span><span class="sxs-lookup"><span data-stu-id="66fc2-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="66fc2-109">必須。</span><span class="sxs-lookup"><span data-stu-id="66fc2-109">Required.</span></span> <span data-ttu-id="66fc2-110">出力ファイルに埋め込むリソースファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="66fc2-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="66fc2-111">既定では、`filename` はアセンブリで公開されています。</span><span class="sxs-lookup"><span data-stu-id="66fc2-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="66fc2-112">ファイル名にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="66fc2-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="66fc2-113">省略可。</span><span class="sxs-lookup"><span data-stu-id="66fc2-113">Optional.</span></span> <span data-ttu-id="66fc2-114">リソースの論理名。読み込みに使用される名前。</span><span class="sxs-lookup"><span data-stu-id="66fc2-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="66fc2-115">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="66fc2-115">The default is the name of the file.</span></span> <span data-ttu-id="66fc2-116">必要に応じて、次のように、アセンブリマニフェストでリソースがパブリックであるかプライベートであるかを指定できます。 `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="66fc2-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66fc2-117">コメント</span><span class="sxs-lookup"><span data-stu-id="66fc2-117">Remarks</span></span>  
 <span data-ttu-id="66fc2-118">リソースファイルを出力ファイルに配置せずに、リソースをアセンブリにリンクするには、`-linkresource` を使用します。</span><span class="sxs-lookup"><span data-stu-id="66fc2-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="66fc2-119">たとえば、 [resgen.exe (リソースファイルジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md)や開発環境などによって作成された .NET Framework のリソースファイル `filename` 場合は、<xref:System.Resources> 名前空間のメンバーを使用してアクセスできます (詳細については、「<xref:System.Resources.ResourceManager>」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="66fc2-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="66fc2-120">実行時に他のすべてのリソースにアクセスするには、次のいずれかの方法を使用します。 <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>、<xref:System.Reflection.Assembly.GetManifestResourceNames%2A>、または <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>。</span><span class="sxs-lookup"><span data-stu-id="66fc2-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="66fc2-121">`-resource` の省略形は `-res` です。</span><span class="sxs-lookup"><span data-stu-id="66fc2-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="66fc2-122">Visual Studio IDE で `-resource` を設定する方法の詳細については、「[アプリケーションリソースの管理 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66fc2-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66fc2-123">例</span><span class="sxs-lookup"><span data-stu-id="66fc2-123">Example</span></span>  
 <span data-ttu-id="66fc2-124">次のコードでは、`In.vb` をコンパイルし、リソースファイル `Rf.resource`をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="66fc2-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="66fc2-125">参照</span><span class="sxs-lookup"><span data-stu-id="66fc2-125">See also</span></span>

- [<span data-ttu-id="66fc2-126">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="66fc2-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="66fc2-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="66fc2-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="66fc2-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66fc2-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="66fc2-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66fc2-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="66fc2-130">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="66fc2-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

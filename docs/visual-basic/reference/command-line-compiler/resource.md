---
title: -リソース (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589510"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="3cf96-102">-リソース (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cf96-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="3cf96-103">マネージド リソースをアセンブリに埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="3cf96-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf96-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cf96-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cf96-105">引数</span><span class="sxs-lookup"><span data-stu-id="3cf96-105">Arguments</span></span>  
  
|<span data-ttu-id="3cf96-106">用語</span><span class="sxs-lookup"><span data-stu-id="3cf96-106">Term</span></span>|<span data-ttu-id="3cf96-107">定義</span><span class="sxs-lookup"><span data-stu-id="3cf96-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="3cf96-108">必須。</span><span class="sxs-lookup"><span data-stu-id="3cf96-108">Required.</span></span> <span data-ttu-id="3cf96-109">出力ファイルに埋め込むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3cf96-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="3cf96-110">既定では、`filename`アセンブリ内でパブリックです。</span><span class="sxs-lookup"><span data-stu-id="3cf96-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="3cf96-111">ファイル名を引用符で囲みます ("")、スペースが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="3cf96-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="3cf96-112">任意。</span><span class="sxs-lookup"><span data-stu-id="3cf96-112">Optional.</span></span> <span data-ttu-id="3cf96-113">リソースの論理名ファイルを読み込むための名前。</span><span class="sxs-lookup"><span data-stu-id="3cf96-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="3cf96-114">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="3cf96-114">The default is the name of the file.</span></span> <span data-ttu-id="3cf96-115">必要に応じて、次のようには、パブリックまたはプライベート アセンブリ マニフェストでにリソースかどうかを指定できます。 `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="3cf96-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf96-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cf96-116">Remarks</span></span>  
 <span data-ttu-id="3cf96-117">使用`-linkresource`出力ファイルにリソース ファイルを配置することがなく、アセンブリにリソースをリンクします。</span><span class="sxs-lookup"><span data-stu-id="3cf96-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="3cf96-118">場合`filename`作成例についてでの .NET Framework リソース ファイルには、 [Resgen.exe (リソース ファイル ジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md)または開発環境でアクセスできるメンバー間で、 <xref:System.Resources> (参照名前空間<xref:System.Resources.ResourceManager>詳細については)。</span><span class="sxs-lookup"><span data-stu-id="3cf96-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="3cf96-119">実行時にその他のすべてのリソースにアクセスするには、次のいずれかを使用: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>、 <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>、または<xref:System.Reflection.Assembly.GetManifestResourceStream%2A>します。</span><span class="sxs-lookup"><span data-stu-id="3cf96-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="3cf96-120">`-resource` の省略形は `-res` です。</span><span class="sxs-lookup"><span data-stu-id="3cf96-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="3cf96-121">設定する方法については`-resource`、Visual Studio IDE で、次を参照してください。[アプリケーション リソースの管理 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)します。</span><span class="sxs-lookup"><span data-stu-id="3cf96-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cf96-122">例</span><span class="sxs-lookup"><span data-stu-id="3cf96-122">Example</span></span>  
 <span data-ttu-id="3cf96-123">次のコードのコンパイル`In.vb`とリソース ファイルのアタッチ`Rf.resource`します。</span><span class="sxs-lookup"><span data-stu-id="3cf96-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cf96-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf96-124">See also</span></span>

- [<span data-ttu-id="3cf96-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="3cf96-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3cf96-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="3cf96-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="3cf96-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cf96-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="3cf96-128">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cf96-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="3cf96-129">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="3cf96-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

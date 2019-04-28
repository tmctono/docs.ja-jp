---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 5555f83107a40b40c7f05c7cc5729f721727f67c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793940"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="5626e-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5626e-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="5626e-103">マネージド リソースへのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="5626e-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5626e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5626e-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5626e-105">引数</span><span class="sxs-lookup"><span data-stu-id="5626e-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="5626e-106">必須。</span><span class="sxs-lookup"><span data-stu-id="5626e-106">Required.</span></span> <span data-ttu-id="5626e-107">アセンブリにリンクするリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="5626e-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="5626e-108">ファイル名にスペースが含まれている場合は、名前を引用符で囲みます ("")。</span><span class="sxs-lookup"><span data-stu-id="5626e-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="5626e-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5626e-109">Optional.</span></span> <span data-ttu-id="5626e-110">リソースの論理名。</span><span class="sxs-lookup"><span data-stu-id="5626e-110">The logical name for the resource.</span></span> <span data-ttu-id="5626e-111">リソースの読み込みに使用される名前です。</span><span class="sxs-lookup"><span data-stu-id="5626e-111">The name that is used to load the resource.</span></span> <span data-ttu-id="5626e-112">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="5626e-112">The default is the name of the file.</span></span> <span data-ttu-id="5626e-113">かどうか、ファイルがパブリックかプライベート アセンブリ マニフェストの例を指定する必要に応じて、:`-linkres:filename.res,myname.res,public`します。</span><span class="sxs-lookup"><span data-stu-id="5626e-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="5626e-114">既定では、`filename`アセンブリ内でパブリックです。</span><span class="sxs-lookup"><span data-stu-id="5626e-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5626e-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="5626e-115">Remarks</span></span>  
 <span data-ttu-id="5626e-116">`-linkresource`オプションは、リソース ファイルを出力ファイルに埋め込まれません。 を使用して、`-resource`これを実行するオプション。</span><span class="sxs-lookup"><span data-stu-id="5626e-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="5626e-117">`-linkresource`オプションでは、いずれかが必要です、`-target`以外のオプション`-target:module`します。</span><span class="sxs-lookup"><span data-stu-id="5626e-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="5626e-118">場合`filename`は、[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]リソース ファイルの作成例については、によって、 [Resgen.exe (リソース ファイル ジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md)または開発環境でアクセスできるメンバー間で、<xref:System.Resources>名前空間。</span><span class="sxs-lookup"><span data-stu-id="5626e-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="5626e-119">(詳細については、「<xref:System.Resources.ResourceManager>」を参照してください)。実行時にその他のすべてのリソースにアクセスするで始まるメソッドを使用して`GetManifestResource`で、<xref:System.Reflection.Assembly>クラス。</span><span class="sxs-lookup"><span data-stu-id="5626e-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="5626e-120">ファイル名には、任意のファイル形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5626e-120">The file name can be any file format.</span></span> <span data-ttu-id="5626e-121">たとえば、ネイティブ DLL をアセンブリの一部にすることで、グローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージド コードからアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5626e-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="5626e-122">`-linkresource` の省略形は `-linkres` です。</span><span class="sxs-lookup"><span data-stu-id="5626e-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5626e-123">`-linkresource`オプションは、Visual Studio 開発環境から使用できません。 コマンドラインからコンパイルするときにのみ、は使用できます。</span><span class="sxs-lookup"><span data-stu-id="5626e-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5626e-124">例</span><span class="sxs-lookup"><span data-stu-id="5626e-124">Example</span></span>  
 <span data-ttu-id="5626e-125">次のコードのコンパイル`in.vb`とリソース ファイルへのリンク`rf.resource`します。</span><span class="sxs-lookup"><span data-stu-id="5626e-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5626e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5626e-126">See also</span></span>

- [<span data-ttu-id="5626e-127">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5626e-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5626e-128">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5626e-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="5626e-129">-リソース (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5626e-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="5626e-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="5626e-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

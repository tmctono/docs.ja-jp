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
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924861"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="d36c8-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d36c8-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="d36c8-103">マネージド リソースへのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="d36c8-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="d36c8-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d36c8-105">引数</span><span class="sxs-lookup"><span data-stu-id="d36c8-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="d36c8-106">必須。</span><span class="sxs-lookup"><span data-stu-id="d36c8-106">Required.</span></span> <span data-ttu-id="d36c8-107">アセンブリにリンクするリソースファイル。</span><span class="sxs-lookup"><span data-stu-id="d36c8-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="d36c8-108">ファイル名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d36c8-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="d36c8-109">任意。</span><span class="sxs-lookup"><span data-stu-id="d36c8-109">Optional.</span></span> <span data-ttu-id="d36c8-110">リソースの論理名。</span><span class="sxs-lookup"><span data-stu-id="d36c8-110">The logical name for the resource.</span></span> <span data-ttu-id="d36c8-111">リソースの読み込みに使用される名前。</span><span class="sxs-lookup"><span data-stu-id="d36c8-111">The name that is used to load the resource.</span></span> <span data-ttu-id="d36c8-112">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="d36c8-112">The default is the name of the file.</span></span> <span data-ttu-id="d36c8-113">必要に応じて、ファイルがアセンブリマニフェスト内でパブリックであるかプライベートであるかを`-linkres:filename.res,myname.res,public`指定できます (例:)。</span><span class="sxs-lookup"><span data-stu-id="d36c8-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="d36c8-114">既定では`filename` 、はアセンブリ内で公開されています。</span><span class="sxs-lookup"><span data-stu-id="d36c8-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d36c8-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="d36c8-115">Remarks</span></span>  
 <span data-ttu-id="d36c8-116">オプションでは、リソースファイルは出力ファイルに埋め込まれません`-resource` 。これを行うには、オプションを使用します。 `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="d36c8-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="d36c8-117">オプションには、以外`-target:module`の`-target`オプションのいずれかが必要です。 `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="d36c8-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="d36c8-118">が`filename` [resgen.exe (リソースファイルジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md)や開発環境などで作成された .NET Framework のリソースファイルである場合は、 <xref:System.Resources>名前空間のメンバーを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d36c8-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="d36c8-119">(詳細については、「<xref:System.Resources.ResourceManager>」を参照してください)。実行時に他のすべてのリソースにアクセスするには、 `GetManifestResource` <xref:System.Reflection.Assembly>クラスので始まるメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d36c8-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="d36c8-120">ファイル名には任意のファイル形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d36c8-120">The file name can be any file format.</span></span> <span data-ttu-id="d36c8-121">たとえば、ネイティブ DLL をアセンブリの一部にすることで、グローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージド コードからアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d36c8-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="d36c8-122">`-linkresource` の省略形は `-linkres` です。</span><span class="sxs-lookup"><span data-stu-id="d36c8-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d36c8-123">この`-linkresource`オプションは、Visual Studio 開発環境では使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d36c8-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d36c8-124">例</span><span class="sxs-lookup"><span data-stu-id="d36c8-124">Example</span></span>  
 <span data-ttu-id="d36c8-125">次のコードは`in.vb` 、コンパイルしてリソース`rf.resource`ファイルにリンクします。</span><span class="sxs-lookup"><span data-stu-id="d36c8-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d36c8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d36c8-126">See also</span></span>

- [<span data-ttu-id="d36c8-127">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d36c8-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d36c8-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d36c8-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="d36c8-129">-リソース (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d36c8-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="d36c8-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="d36c8-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

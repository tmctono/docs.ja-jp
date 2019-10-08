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
ms.openlocfilehash: dee5384696d543442f3280b9fdb535a7d9b6f863
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005489"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="029ec-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="029ec-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="029ec-103">マネージド リソースへのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="029ec-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="029ec-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="029ec-105">または</span><span class="sxs-lookup"><span data-stu-id="029ec-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="029ec-106">引数</span><span class="sxs-lookup"><span data-stu-id="029ec-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="029ec-107">必須。</span><span class="sxs-lookup"><span data-stu-id="029ec-107">Required.</span></span> <span data-ttu-id="029ec-108">アセンブリにリンクするリソースファイル。</span><span class="sxs-lookup"><span data-stu-id="029ec-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="029ec-109">ファイル名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="029ec-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="029ec-110">任意。</span><span class="sxs-lookup"><span data-stu-id="029ec-110">Optional.</span></span> <span data-ttu-id="029ec-111">リソースの論理名。</span><span class="sxs-lookup"><span data-stu-id="029ec-111">The logical name for the resource.</span></span> <span data-ttu-id="029ec-112">リソースの読み込みに使用される名前。</span><span class="sxs-lookup"><span data-stu-id="029ec-112">The name that is used to load the resource.</span></span> <span data-ttu-id="029ec-113">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="029ec-113">The default is the name of the file.</span></span> <span data-ttu-id="029ec-114">必要に応じて、ファイルがアセンブリマニフェスト内でパブリックであるかプライベートであるかを指定できます。たとえば、`-linkres:filename.res,myname.res,public` です。</span><span class="sxs-lookup"><span data-stu-id="029ec-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="029ec-115">既定では、`filename` はアセンブリ内で公開されています。</span><span class="sxs-lookup"><span data-stu-id="029ec-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="029ec-116">コメント</span><span class="sxs-lookup"><span data-stu-id="029ec-116">Remarks</span></span>  
 <span data-ttu-id="029ec-117">@No__t-0 オプションでは、リソースファイルは出力ファイルに埋め込まれません。これを行うには、`-resource` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="029ec-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="029ec-118">@No__t-0 オプションには、`-target:module` 以外の `-target` オプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="029ec-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="029ec-119">@No__t-0 は、 [resgen.exe (リソースファイルジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md)や開発環境などで作成された .NET Framework のリソースファイルである場合、<xref:System.Resources> 名前空間のメンバーを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="029ec-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="029ec-120">(詳細については、「<xref:System.Resources.ResourceManager>」を参照してください)。実行時に他のすべてのリソースにアクセスするには、<xref:System.Reflection.Assembly> クラスの `GetManifestResource` で始まるメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="029ec-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="029ec-121">ファイル名には任意のファイル形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="029ec-121">The file name can be any file format.</span></span> <span data-ttu-id="029ec-122">たとえば、ネイティブ DLL をアセンブリの一部にすることで、グローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージド コードからアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="029ec-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="029ec-123">`-linkresource` の省略形は `-linkres` です。</span><span class="sxs-lookup"><span data-stu-id="029ec-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="029ec-124">@No__t-0 オプションは、Visual Studio 開発環境では使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="029ec-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="029ec-125">例</span><span class="sxs-lookup"><span data-stu-id="029ec-125">Example</span></span>  
 <span data-ttu-id="029ec-126">次のコードは `in.vb` をコンパイルし、リソースファイル `rf.resource` にリンクします。</span><span class="sxs-lookup"><span data-stu-id="029ec-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="029ec-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="029ec-127">See also</span></span>

- [<span data-ttu-id="029ec-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="029ec-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="029ec-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="029ec-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="029ec-130">-リソース (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="029ec-130">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="029ec-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="029ec-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

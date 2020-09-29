---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 8c4f753f94aedaf0a4f997a3f9b99fb3f417abf8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065685"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="74dae-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74dae-102">-linkresource (Visual Basic)</span></span>

<span data-ttu-id="74dae-103">マネージド リソースへのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="74dae-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74dae-104">構文</span><span class="sxs-lookup"><span data-stu-id="74dae-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="74dae-105">or</span><span class="sxs-lookup"><span data-stu-id="74dae-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="74dae-106">引数</span><span class="sxs-lookup"><span data-stu-id="74dae-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="74dae-107">必須です。</span><span class="sxs-lookup"><span data-stu-id="74dae-107">Required.</span></span> <span data-ttu-id="74dae-108">アセンブリにリンクするリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="74dae-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="74dae-109">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます (" ")。</span><span class="sxs-lookup"><span data-stu-id="74dae-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="74dae-110">任意。</span><span class="sxs-lookup"><span data-stu-id="74dae-110">Optional.</span></span> <span data-ttu-id="74dae-111">リソースの論理名。</span><span class="sxs-lookup"><span data-stu-id="74dae-111">The logical name for the resource.</span></span> <span data-ttu-id="74dae-112">リソースの読み込みに使用される名前。</span><span class="sxs-lookup"><span data-stu-id="74dae-112">The name that is used to load the resource.</span></span> <span data-ttu-id="74dae-113">既定値は、ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="74dae-113">The default is the name of the file.</span></span> <span data-ttu-id="74dae-114">必要に応じて、アセンブリ マニフェストでファイルをパブリックとプライベートのどちらにするかを指定できます (例: `-linkres:filename.res,myname.res,public`)。</span><span class="sxs-lookup"><span data-stu-id="74dae-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="74dae-115">既定では、アセンブリで `filename` はパブリックとなります。</span><span class="sxs-lookup"><span data-stu-id="74dae-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74dae-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="74dae-116">Remarks</span></span>  

 <span data-ttu-id="74dae-117">`-linkresource` オプションでは、リソース ファイルは出力ファイルに埋め込まれません。これを行うには、`-resource` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="74dae-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="74dae-118">`-linkresource` オプションでは、`-target:module` 以外の `-target` オプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="74dae-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="74dae-119">`filename` が、たとえば [Resgen.exe (リソース ファイル ジェネレーター)](../../../framework/tools/resgen-exe-resource-file-generator.md) や開発環境で作成された .NET Framework リソース ファイルである場合は、<xref:System.Resources> 名前空間のメンバーを使用してアクセスできます</span><span class="sxs-lookup"><span data-stu-id="74dae-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="74dae-120">(詳細は、<xref:System.Resources.ResourceManager> を参照)。実行時に他のすべてのリソースにアクセスするには、<xref:System.Reflection.Assembly> クラスの `GetManifestResource` で始まるメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="74dae-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="74dae-121">ファイル名には任意のファイル形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="74dae-121">The file name can be any file format.</span></span> <span data-ttu-id="74dae-122">たとえば、ネイティブ DLL をアセンブリの一部にすることで、グローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージド コードからアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="74dae-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="74dae-123">`-linkresource` の省略形は `-linkres` です。</span><span class="sxs-lookup"><span data-stu-id="74dae-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74dae-124">`-linkresource` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="74dae-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74dae-125">例</span><span class="sxs-lookup"><span data-stu-id="74dae-125">Example</span></span>  

 <span data-ttu-id="74dae-126">次のコードでは `in.vb` がコンパイルされ、リソース ファイル `rf.resource` にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="74dae-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="74dae-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="74dae-127">See also</span></span>

- [<span data-ttu-id="74dae-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="74dae-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="74dae-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74dae-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="74dae-130">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74dae-130">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="74dae-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="74dae-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

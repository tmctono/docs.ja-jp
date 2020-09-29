---
description: -addmodule (C# コンパイラ オプション)
title: -addmodule (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150571"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="e56d0-103">-addmodule (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="e56d0-103">-addmodule (C# Compiler Options)</span></span>

<span data-ttu-id="e56d0-104">このオプションを使用すると、スイッチで作成されたモジュールが現在のコンパイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e56d0-104">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56d0-105">構文</span><span class="sxs-lookup"><span data-stu-id="e56d0-105">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e56d0-106">引数</span><span class="sxs-lookup"><span data-stu-id="e56d0-106">Arguments</span></span>  

 <span data-ttu-id="e56d0-107">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="e56d0-107">`file`, `file2`</span></span>  
 <span data-ttu-id="e56d0-108">メタデータを含む出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="e56d0-108">An output file that contains metadata.</span></span> <span data-ttu-id="e56d0-109">このファイルには、アセンブリ マニフェストを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="e56d0-109">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="e56d0-110">複数のファイルをインポートするには、コンマかセミコロンでファイル名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="e56d0-110">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e56d0-111">注釈</span><span class="sxs-lookup"><span data-stu-id="e56d0-111">Remarks</span></span>  

 <span data-ttu-id="e56d0-112">**-addmodule** で追加したモジュールはすべて、実行時に出力ファイルと同じディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56d0-112">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="e56d0-113">つまり、コンパイル時にはあるゆるディレクトリのモジュールを指定できますが、そのモジュールは実行時にアプリケーション ディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56d0-113">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="e56d0-114">実行時にモジュールがアプリケーション ディレクトリにない場合、<xref:System.TypeLoadException> が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e56d0-114">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="e56d0-115">`file` には、アセンブリを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="e56d0-115">`file` cannot contain an assembly.</span></span> <span data-ttu-id="e56d0-116">たとえば、出力ファイルが [-target:module](./target-module-compiler-option.md) で作成された場合、そのメタデータは **-addmodule** でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e56d0-116">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="e56d0-117">出力ファイルが **-target:module** ではなく **-target** オプションで作成された場合、そのメタデータは **-addmodule** ではインポートできませんが、[-reference](./reference-compiler-option.md) でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e56d0-117">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e56d0-118">このコンパイラ オプションは Visual Studio では利用できません。プロジェクトはモジュールを参照できません。</span><span class="sxs-lookup"><span data-stu-id="e56d0-118">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="e56d0-119">また、このコンパイラ オプションをプログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e56d0-119">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e56d0-120">例</span><span class="sxs-lookup"><span data-stu-id="e56d0-120">Example</span></span>  

 <span data-ttu-id="e56d0-121">ソース ファイル `input.cs` をコンパイルし、`metad1.netmodule` と `metad2.netmodule` からメタデータを追加し、`out.exe` を生成します。</span><span class="sxs-lookup"><span data-stu-id="e56d0-121">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e56d0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e56d0-122">See also</span></span>

- [<span data-ttu-id="e56d0-123">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="e56d0-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e56d0-124">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="e56d0-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e56d0-125">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="e56d0-125">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="e56d0-126">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="e56d0-126">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)

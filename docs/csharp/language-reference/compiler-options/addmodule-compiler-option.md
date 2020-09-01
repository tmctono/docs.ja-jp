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
ms.openlocfilehash: bcc615d52aec0a09ebf3913b3ece71f2cbfcbda9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126126"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="b9ed9-103">-addmodule (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="b9ed9-103">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="b9ed9-104">このオプションを使用すると、スイッチで作成されたモジュールが現在のコンパイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-104">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ed9-105">構文</span><span class="sxs-lookup"><span data-stu-id="b9ed9-105">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b9ed9-106">引数</span><span class="sxs-lookup"><span data-stu-id="b9ed9-106">Arguments</span></span>  
 <span data-ttu-id="b9ed9-107">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="b9ed9-107">`file`, `file2`</span></span>  
 <span data-ttu-id="b9ed9-108">メタデータを含む出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-108">An output file that contains metadata.</span></span> <span data-ttu-id="b9ed9-109">このファイルには、アセンブリ マニフェストを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-109">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="b9ed9-110">複数のファイルをインポートするには、コンマかセミコロンでファイル名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-110">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ed9-111">注釈</span><span class="sxs-lookup"><span data-stu-id="b9ed9-111">Remarks</span></span>  
 <span data-ttu-id="b9ed9-112">**-addmodule** で追加したモジュールはすべて、実行時に出力ファイルと同じディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-112">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="b9ed9-113">つまり、コンパイル時にはあるゆるディレクトリのモジュールを指定できますが、そのモジュールは実行時にアプリケーション ディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-113">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="b9ed9-114">実行時にモジュールがアプリケーション ディレクトリにない場合、<xref:System.TypeLoadException> が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-114">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="b9ed9-115">`file` には、アセンブリを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-115">`file` cannot contain an assembly.</span></span> <span data-ttu-id="b9ed9-116">たとえば、出力ファイルが [-target:module](./target-module-compiler-option.md) で作成された場合、そのメタデータは **-addmodule** でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-116">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="b9ed9-117">出力ファイルが **-target:module** ではなく **-target** オプションで作成された場合、そのメタデータは **-addmodule** ではインポートできませんが、[-reference](./reference-compiler-option.md) でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-117">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="b9ed9-118">このコンパイラ オプションは Visual Studio では利用できません。プロジェクトはモジュールを参照できません。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-118">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="b9ed9-119">また、このコンパイラ オプションをプログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-119">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9ed9-120">例</span><span class="sxs-lookup"><span data-stu-id="b9ed9-120">Example</span></span>  
 <span data-ttu-id="b9ed9-121">ソース ファイル `input.cs` をコンパイルし、`metad1.netmodule` と `metad2.netmodule` からメタデータを追加し、`out.exe` を生成します。</span><span class="sxs-lookup"><span data-stu-id="b9ed9-121">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9ed9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9ed9-122">See also</span></span>

- [<span data-ttu-id="b9ed9-123">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="b9ed9-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="b9ed9-124">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="b9ed9-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="b9ed9-125">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="b9ed9-125">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="b9ed9-126">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="b9ed9-126">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)

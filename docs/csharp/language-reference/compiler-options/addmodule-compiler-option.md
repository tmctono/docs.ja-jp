---
title: -addmodule (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: 148a63c37cfbc4c60448adccde10947e91e22bb9
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970186"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="cdf46-102">-addmodule (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="cdf46-102">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="cdf46-103">このオプションを使用すると、スイッチで作成されたモジュールが現在のコンパイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdf46-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdf46-104">構文</span><span class="sxs-lookup"><span data-stu-id="cdf46-104">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdf46-105">引数</span><span class="sxs-lookup"><span data-stu-id="cdf46-105">Arguments</span></span>  
 <span data-ttu-id="cdf46-106">`file`、 `file2`</span><span class="sxs-lookup"><span data-stu-id="cdf46-106">`file`, `file2`</span></span>  
 <span data-ttu-id="cdf46-107">メタデータを含む出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="cdf46-107">An output file that contains metadata.</span></span> <span data-ttu-id="cdf46-108">このファイルには、アセンブリ マニフェストを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="cdf46-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="cdf46-109">複数のファイルをインポートするには、コンマかセミコロンでファイル名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="cdf46-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdf46-110">解説</span><span class="sxs-lookup"><span data-stu-id="cdf46-110">Remarks</span></span>  
 <span data-ttu-id="cdf46-111">**-addmodule** で追加したモジュールはすべて、実行時に出力ファイルと同じディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf46-111">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="cdf46-112">つまり、コンパイル時にはあるゆるディレクトリのモジュールを指定できますが、そのモジュールは実行時にアプリケーション ディレクトリに置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf46-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="cdf46-113">実行時にモジュールがアプリケーション ディレクトリにない場合、<xref:System.TypeLoadException> が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cdf46-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="cdf46-114">`file` には、アセンブリを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="cdf46-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="cdf46-115">たとえば、出力ファイルが [-target:module](./target-module-compiler-option.md) で作成された場合、そのメタデータは **-addmodule** でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cdf46-115">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="cdf46-116">出力ファイルが **-target:module** ではなく **-target** オプションで作成された場合、そのメタデータは **-addmodule** ではインポートできませんが、[-reference](./reference-compiler-option.md) でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cdf46-116">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="cdf46-117">このコンパイラ オプションは Visual Studio では利用できません。プロジェクトはモジュールを参照できません。</span><span class="sxs-lookup"><span data-stu-id="cdf46-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="cdf46-118">また、このコンパイラ オプションをプログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf46-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdf46-119">例</span><span class="sxs-lookup"><span data-stu-id="cdf46-119">Example</span></span>  
 <span data-ttu-id="cdf46-120">ソース ファイル `input.cs` をコンパイルし、`metad1.netmodule` と `metad2.netmodule` からメタデータを追加し、`out.exe` を生成します。</span><span class="sxs-lookup"><span data-stu-id="cdf46-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdf46-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdf46-121">See also</span></span>

- [<span data-ttu-id="cdf46-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="cdf46-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cdf46-123">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="cdf46-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="cdf46-124">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="cdf46-124">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="cdf46-125">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="cdf46-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)

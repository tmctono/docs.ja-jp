---
description: -target:module (C# コンパイラ オプション)
title: -target:module (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128453"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="db620-103">-target:module (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="db620-103">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="db620-104">このオプションでは、コンパイラはアセンブリ マニフェストを生成しません。</span><span class="sxs-lookup"><span data-stu-id="db620-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db620-105">構文</span><span class="sxs-lookup"><span data-stu-id="db620-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="db620-106">解説</span><span class="sxs-lookup"><span data-stu-id="db620-106">Remarks</span></span>  
 <span data-ttu-id="db620-107">既定では、このオプションを使用してコンパイルすることによって作成された出力ファイルに、.netmodule という拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="db620-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="db620-108">アセンブリ マニフェストのないファイルは、.NET Framework 共通言語ランタイムで読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="db620-108">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="db620-109">ただし、このようなファイルは、[-addmodule](./addmodule-compiler-option.md) を使用して、アセンブリのアセンブリ マニフェストに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="db620-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="db620-110">複数のモジュールが 1 回のコンパイルで作成される場合、あるモジュールの [internal](../keywords/internal.md) 型をコンパイル中に別のモジュールで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="db620-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="db620-111">あるモジュールのコードが別のモジュールの `internal` 型を参照する場合は、**-addmodule** を使用して、両方のモジュールをアセンブリ マニフェストに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="db620-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="db620-112">Visual Studio 開発環境では、モジュールの作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db620-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="db620-113">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.ProjectProperties3.OutputType%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db620-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db620-114">例</span><span class="sxs-lookup"><span data-stu-id="db620-114">Example</span></span>  
 <span data-ttu-id="db620-115">`in.cs` をコンパイルし、`in.netmodule` を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="db620-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="db620-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="db620-116">See also</span></span>

- [<span data-ttu-id="db620-117">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="db620-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="db620-118">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="db620-118">C# Compiler Options</span></span>](./index.md)

---
title: -target:module (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 25421df2e9306071ce3506aaf7affd1b259d1c32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602448"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="67f4b-102">-target:module (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="67f4b-102">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="67f4b-103">このオプションでは、コンパイラはアセンブリ マニフェストを生成しません。</span><span class="sxs-lookup"><span data-stu-id="67f4b-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="67f4b-104">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="67f4b-105">解説</span><span class="sxs-lookup"><span data-stu-id="67f4b-105">Remarks</span></span>  
 <span data-ttu-id="67f4b-106">既定では、このオプションを使用してコンパイルすることによって作成された出力ファイルに、.netmodule という拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="67f4b-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="67f4b-107">アセンブリ マニフェストのないファイルは、.NET Framework 共通言語ランタイムで読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="67f4b-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="67f4b-108">ただし、このようなファイルは、[-addmodule](./addmodule-compiler-option.md) を使用して、アセンブリのアセンブリ マニフェストに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="67f4b-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="67f4b-109">複数のモジュールが 1 回のコンパイルで作成される場合、あるモジュールの [internal](../keywords/internal.md) 型をコンパイル中に別のモジュールで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="67f4b-109">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="67f4b-110">あるモジュールのコードが別のモジュールの `internal` 型を参照する場合は、 **-addmodule** を使用して、両方のモジュールをアセンブリ マニフェストに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f4b-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="67f4b-111">Visual Studio 開発環境では、モジュールの作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="67f4b-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="67f4b-112">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67f4b-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67f4b-113">例</span><span class="sxs-lookup"><span data-stu-id="67f4b-113">Example</span></span>  
 <span data-ttu-id="67f4b-114">`in.cs` をコンパイルし、`in.netmodule` を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="67f4b-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="67f4b-115">参照</span><span class="sxs-lookup"><span data-stu-id="67f4b-115">See also</span></span>

- [<span data-ttu-id="67f4b-116">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="67f4b-116">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="67f4b-117">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="67f4b-117">C# Compiler Options</span></span>](./index.md)

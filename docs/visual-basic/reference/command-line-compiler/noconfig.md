---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964393"
---
# <a name="-noconfig"></a><span data-ttu-id="5abdb-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="5abdb-102">-noconfig</span></span>
<span data-ttu-id="5abdb-103">コンパイラが、一般的に使用される .NET Framework アセンブリを自動的に参照したり`System` 、 `Microsoft.VisualBasic`名前空間および名前空間をインポートしたりしないように指定します。</span><span class="sxs-lookup"><span data-stu-id="5abdb-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5abdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="5abdb-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="5abdb-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5abdb-105">Remarks</span></span>  
 <span data-ttu-id="5abdb-106">オプション`-noconfig`は、vbc.exe ファイルと同じディレクトリにある vbc.exe ファイルでコンパイルしないようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="5abdb-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="5abdb-107">Vbc.exe ファイルは、一般的に使用される .NET Framework アセンブリを参照し`System` 、 `Microsoft.VisualBasic`名前空間と名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="5abdb-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="5abdb-108">コンパイラは、オプションが指定されて`-nostdlib`いない限り、システム .dll アセンブリを暗黙的に参照します。</span><span class="sxs-lookup"><span data-stu-id="5abdb-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="5abdb-109">オプション`-nostdlib`は、vbc.exe でコンパイルしないようにコンパイラに指示するか、または自動的に .dll アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="5abdb-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5abdb-110">Mscorlib.dll および Microsoft の .dll アセンブリは常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="5abdb-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="5abdb-111">Vbc.exe ファイルを変更して、すべての vbc.exe コンパイルに含める必要のある追加のコンパイラオプションを指定できます ( `-noconfig`オプションを指定する場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="5abdb-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="5abdb-112">詳しくは、「[@ (応答ファイルの指定)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5abdb-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="5abdb-113">コンパイラは、最後に`vbc`コマンドに渡されたオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="5abdb-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="5abdb-114">したがって、コマンドラインのオプションは、Vbc.exe ファイルの同じオプションの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5abdb-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5abdb-115">この`-noconfig`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5abdb-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abdb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5abdb-116">See also</span></span>

- [<span data-ttu-id="5abdb-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5abdb-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="5abdb-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5abdb-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5abdb-119">@ (応答ファイルの指定)</span><span class="sxs-lookup"><span data-stu-id="5abdb-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="5abdb-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5abdb-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

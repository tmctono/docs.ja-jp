---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789026"
---
# <a name="-noconfig"></a><span data-ttu-id="5c579-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="5c579-102">-noconfig</span></span>
<span data-ttu-id="5c579-103">コンパイラが自動的に参照していないこと、一般的に使用される指定[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]アセンブリまたはインポート、`System`と`Microsoft.VisualBasic`名前空間。</span><span class="sxs-lookup"><span data-stu-id="5c579-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c579-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c579-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="5c579-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c579-105">Remarks</span></span>  
 <span data-ttu-id="5c579-106">`-noconfig`オプション Vbc.exe ファイルと同じディレクトリにある Vbc.rsp ファイルを使用してコンパイルにしないコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="5c579-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="5c579-107">Vbc.rsp ファイルを一般的に使用される参照[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]アセンブリとインポート、`System`と`Microsoft.VisualBasic`名前空間。</span><span class="sxs-lookup"><span data-stu-id="5c579-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="5c579-108">コンパイラは、System.dll アセンブリを暗黙的に参照しない限り、`-nostdlib`オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c579-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="5c579-109">`-nostdlib`オプション Vbc.rsp でコンパイルや System.dll アセンブリの参照を自動的にコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="5c579-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c579-110">Mscorlib.dll および Microsoft.VisualBasic.dll のアセンブリは、常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="5c579-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="5c579-111">Vbc.exe のすべてのコンパイルに含める必要がある追加のコンパイラ オプションを指定する Vbc.rsp ファイルを変更することができます (を指定する場合を除いて、`-noconfig`オプション)。</span><span class="sxs-lookup"><span data-stu-id="5c579-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="5c579-112">詳しくは、「[@ (応答ファイルの指定)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5c579-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="5c579-113">コンパイラに渡されるオプションの処理、`vbc`最後コマンドします。</span><span class="sxs-lookup"><span data-stu-id="5c579-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="5c579-114">そのため、コマンドラインで任意のオプションは、Vbc.rsp ファイル内の同じオプションの設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="5c579-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c579-115">`-noconfig`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="5c579-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c579-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c579-116">See also</span></span>

- [<span data-ttu-id="5c579-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c579-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="5c579-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5c579-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5c579-119">@ (応答ファイルの指定)</span><span class="sxs-lookup"><span data-stu-id="5c579-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="5c579-120">-参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c579-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

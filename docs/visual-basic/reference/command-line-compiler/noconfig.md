---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005436"
---
# <a name="-noconfig"></a><span data-ttu-id="ab3c7-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ab3c7-102">-noconfig</span></span>
<span data-ttu-id="ab3c7-103">コンパイラが、一般的に使用される .NET Framework アセンブリを自動的に参照したり、`System` と `Microsoft.VisualBasic` の名前空間をインポートしたりしないように指定します。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab3c7-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="ab3c7-105">コメント</span><span class="sxs-lookup"><span data-stu-id="ab3c7-105">Remarks</span></span>  
 <span data-ttu-id="ab3c7-106">@No__t-0 オプションは、Vbc.exe ファイルと同じディレクトリにある Vbc.exe ファイルでコンパイルしないようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="ab3c7-107">Vbc.exe ファイルは、一般的に使用される .NET Framework アセンブリを参照し、@no__t 0 と `Microsoft.VisualBasic` の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="ab3c7-108">コンパイラは、`-nostdlib` オプションが指定されていない限り、システム .dll アセンブリを暗黙的に参照します。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="ab3c7-109">@No__t-0 オプションは、Vbc.exe を使用してコンパイルしないようにコンパイラに指示します。または、自動的に .dll アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab3c7-110">Mscorlib.dll および Microsoft の .dll アセンブリは常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="ab3c7-111">Vbc.exe ファイルを変更して、すべての Vbc.exe コンパイルに含める必要のある追加のコンパイラオプションを指定することができます (`-noconfig` オプションを指定する場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="ab3c7-112">詳しくは、「[@ (応答ファイルの指定)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="ab3c7-113">コンパイラは、最後に `vbc` コマンドに渡されたオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="ab3c7-114">したがって、コマンドラインのオプションは、Vbc.exe ファイルの同じオプションの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab3c7-115">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab3c7-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3c7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab3c7-116">See also</span></span>

- [<span data-ttu-id="ab3c7-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab3c7-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="ab3c7-118">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="ab3c7-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ab3c7-119">@ (応答ファイルの指定)</span><span class="sxs-lookup"><span data-stu-id="ab3c7-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="ab3c7-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab3c7-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

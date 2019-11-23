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
# <a name="-noconfig"></a><span data-ttu-id="9bfb3-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="9bfb3-102">-noconfig</span></span>
<span data-ttu-id="9bfb3-103">コンパイラが、一般的に使用される .NET Framework アセンブリを自動的に参照したり、`System` と `Microsoft.VisualBasic` 名前空間をインポートしたりしないように指定します。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bfb3-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bfb3-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="9bfb3-105">コメント</span><span class="sxs-lookup"><span data-stu-id="9bfb3-105">Remarks</span></span>  
 <span data-ttu-id="9bfb3-106">`-noconfig` オプションは、Vbc.exe ファイルと同じディレクトリにある Vbc.exe ファイルでコンパイルしないようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="9bfb3-107">Vbc.exe ファイルは、一般的に使用される .NET Framework アセンブリを参照し、`System` と `Microsoft.VisualBasic` 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="9bfb3-108">コンパイラは、`-nostdlib` オプションを指定しない限り、システム .dll アセンブリを暗黙的に参照します。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="9bfb3-109">`-nostdlib` オプションは、Vbc.exe でコンパイルしないようにコンパイラに指示します。または、自動的に .dll アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bfb3-110">Mscorlib.dll および Microsoft の .dll アセンブリは常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="9bfb3-111">Vbc.exe ファイルを変更して、すべての Vbc.exe コンパイルに含める必要のある追加のコンパイラオプションを指定することができます (`-noconfig` オプションを指定する場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="9bfb3-112">詳しくは、「[@ (応答ファイルの指定)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="9bfb3-113">コンパイラは、最後に `vbc` コマンドに渡されたオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="9bfb3-114">したがって、コマンドラインのオプションは、Vbc.exe ファイルの同じオプションの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bfb3-115">`-noconfig` オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bfb3-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfb3-116">参照</span><span class="sxs-lookup"><span data-stu-id="9bfb3-116">See also</span></span>

- [<span data-ttu-id="9bfb3-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bfb3-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="9bfb3-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="9bfb3-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9bfb3-119">@ (応答ファイルの指定)</span><span class="sxs-lookup"><span data-stu-id="9bfb3-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="9bfb3-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bfb3-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

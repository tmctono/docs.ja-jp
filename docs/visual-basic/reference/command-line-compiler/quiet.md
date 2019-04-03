---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 32f82eb428c1d3bc427a10b9ca7a1a5feb9e339a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816539"
---
# <a name="-quiet"></a><span data-ttu-id="68ef6-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="68ef6-102">-quiet</span></span>
<span data-ttu-id="68ef6-103">コンパイラで構文関連のエラーと警告のコードが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="68ef6-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ef6-104">構文</span><span class="sxs-lookup"><span data-stu-id="68ef6-104">Syntax</span></span>  
  
```  
-quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="68ef6-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="68ef6-105">Remarks</span></span>  
 <span data-ttu-id="68ef6-106">既定では、`-quiet` は無効です。</span><span class="sxs-lookup"><span data-stu-id="68ef6-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="68ef6-107">コンパイラは、構文に関連するエラーまたは警告を報告、ときにも、ソース コードから行を出力します。</span><span class="sxs-lookup"><span data-stu-id="68ef6-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="68ef6-108">コンパイラ出力を解析するアプリケーションでは、診断のテキストのみを出力するコンパイラのより便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="68ef6-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="68ef6-109">次の例では、`Module1`出力なしでコンパイル時に、ソース コードを含むエラー`-quiet`します。</span><span class="sxs-lookup"><span data-stu-id="68ef6-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="68ef6-110">Output:</span><span class="sxs-lookup"><span data-stu-id="68ef6-110">Output:</span></span>  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 <span data-ttu-id="68ef6-111">コンパイルされた`-quiet`コンパイラは、次のオプションのみを出力します。</span><span class="sxs-lookup"><span data-stu-id="68ef6-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="68ef6-112">`-quiet`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="68ef6-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68ef6-113">例</span><span class="sxs-lookup"><span data-stu-id="68ef6-113">Example</span></span>  
 <span data-ttu-id="68ef6-114">次のコードのコンパイル`T2.vb`構文に関連するコンパイラ診断のコードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="68ef6-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="68ef6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ef6-115">See also</span></span>

- [<span data-ttu-id="68ef6-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="68ef6-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="68ef6-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="68ef6-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

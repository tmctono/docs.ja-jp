---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 75369c3bcb19afbf98bfb80bc3e439f996d2a9d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796079"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="47efe-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47efe-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="47efe-103">UTF-8 エンコードを使用してコンパイラ出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="47efe-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47efe-104">構文</span><span class="sxs-lookup"><span data-stu-id="47efe-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="47efe-105">引数</span><span class="sxs-lookup"><span data-stu-id="47efe-105">Arguments</span></span>  
 <span data-ttu-id="47efe-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="47efe-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="47efe-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47efe-107">Optional.</span></span> <span data-ttu-id="47efe-108">このオプションの既定値は`-utf8output-`、つまり、コンパイラの出力は utf-8 エンコードを使用しません。</span><span class="sxs-lookup"><span data-stu-id="47efe-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="47efe-109">`-utf8output` を指定することは、`-utf8output+` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="47efe-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47efe-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="47efe-110">Remarks</span></span>  
 <span data-ttu-id="47efe-111">国際対応の構成によっては、コンパイラの出力は、コンソールで正常に表示できません。</span><span class="sxs-lookup"><span data-stu-id="47efe-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="47efe-112">このような状況では、次のように使用します。`-utf8output`してコンパイラ出力をファイルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="47efe-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47efe-113">`-utf8output`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="47efe-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47efe-114">例</span><span class="sxs-lookup"><span data-stu-id="47efe-114">Example</span></span>  
 <span data-ttu-id="47efe-115">次のコードのコンパイル`In.vb`表示をコンパイラに指示して utf-8 エンコードを使用して出力します。</span><span class="sxs-lookup"><span data-stu-id="47efe-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="47efe-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="47efe-116">See also</span></span>

- [<span data-ttu-id="47efe-117">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="47efe-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="47efe-118">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="47efe-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

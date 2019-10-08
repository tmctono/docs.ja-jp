---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: adcb518cbe8397549c3ae3b3a8ca9f0ecf9dc38e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004661"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="23432-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23432-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="23432-103">UTF-8 エンコードを使用してコンパイラ出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="23432-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23432-104">構文</span><span class="sxs-lookup"><span data-stu-id="23432-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="23432-105">引数</span><span class="sxs-lookup"><span data-stu-id="23432-105">Arguments</span></span>  
 <span data-ttu-id="23432-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="23432-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="23432-107">任意。</span><span class="sxs-lookup"><span data-stu-id="23432-107">Optional.</span></span> <span data-ttu-id="23432-108">このオプションの既定値は `-utf8output-` です。これは、コンパイラの出力で UTF-8 エンコードが使用されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="23432-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="23432-109">`-utf8output` を指定することは、`-utf8output+` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="23432-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23432-110">コメント</span><span class="sxs-lookup"><span data-stu-id="23432-110">Remarks</span></span>  
 <span data-ttu-id="23432-111">国際対応の構成によっては、コンパイラの出力をコンソールに正しく表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="23432-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="23432-112">このような場合は、@no__t 0 を使用して、コンパイラの出力をファイルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="23432-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23432-113">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="23432-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23432-114">例</span><span class="sxs-lookup"><span data-stu-id="23432-114">Example</span></span>  
 <span data-ttu-id="23432-115">次のコードは `In.vb` をコンパイルし、UTF-8 エンコーディングを使用して出力を表示するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="23432-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="23432-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23432-116">See also</span></span>

- [<span data-ttu-id="23432-117">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="23432-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="23432-118">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="23432-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

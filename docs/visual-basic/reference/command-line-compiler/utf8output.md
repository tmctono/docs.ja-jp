---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937271"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="0f414-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f414-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="0f414-103">UTF-8 エンコードを使用してコンパイラ出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f414-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f414-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f414-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f414-105">引数</span><span class="sxs-lookup"><span data-stu-id="0f414-105">Arguments</span></span>  
 <span data-ttu-id="0f414-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0f414-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0f414-107">任意。</span><span class="sxs-lookup"><span data-stu-id="0f414-107">Optional.</span></span> <span data-ttu-id="0f414-108">このオプションの既定値は`-utf8output-`です。これは、コンパイラの出力で utf-8 エンコーディングが使用されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0f414-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="0f414-109">`-utf8output` を指定することは、`-utf8output+` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="0f414-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f414-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f414-110">Remarks</span></span>  
 <span data-ttu-id="0f414-111">国際対応の構成によっては、コンパイラの出力をコンソールに正しく表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f414-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="0f414-112">このような場合は`-utf8output` 、を使用して、コンパイラの出力をファイルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="0f414-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f414-113">この`-utf8output`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f414-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f414-114">例</span><span class="sxs-lookup"><span data-stu-id="0f414-114">Example</span></span>  
 <span data-ttu-id="0f414-115">次のコードで`In.vb`は、utf-8 エンコーディングを使用して出力を表示するようにコンパイラをコンパイルし、指示します。</span><span class="sxs-lookup"><span data-stu-id="0f414-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f414-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f414-116">See also</span></span>

- [<span data-ttu-id="0f414-117">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="0f414-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0f414-118">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="0f414-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

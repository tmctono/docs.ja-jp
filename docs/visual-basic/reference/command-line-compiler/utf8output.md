---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 2faebb7870cbc019d479215563261f331f9fddcf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085075"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="18e81-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18e81-102">-utf8output (Visual Basic)</span></span>

<span data-ttu-id="18e81-103">UTF-8 エンコードを使用してコンパイラ出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="18e81-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e81-104">構文</span><span class="sxs-lookup"><span data-stu-id="18e81-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="18e81-105">引数</span><span class="sxs-lookup"><span data-stu-id="18e81-105">Arguments</span></span>  

 <span data-ttu-id="18e81-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="18e81-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="18e81-107">任意。</span><span class="sxs-lookup"><span data-stu-id="18e81-107">Optional.</span></span> <span data-ttu-id="18e81-108">このオプションの既定値は `-utf8output-` です。これは、コンパイラ出力で UTF-8 エンコードが使用されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="18e81-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="18e81-109">`-utf8output` を指定することは、`-utf8output+` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="18e81-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18e81-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="18e81-110">Remarks</span></span>  

 <span data-ttu-id="18e81-111">地域と言語の構成によっては、コンパイラ出力をコンソールに正しく表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="18e81-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="18e81-112">このような場合は、`-utf8output` を使用して、コンパイラ出力をファイルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="18e81-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18e81-113">`-utf8output` オプションは、Visual Studio 開発環境内からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="18e81-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18e81-114">例</span><span class="sxs-lookup"><span data-stu-id="18e81-114">Example</span></span>  

 <span data-ttu-id="18e81-115">次のコードでは `In.vb` をコンパイルし、UTF-8 エンコードを使用して出力を表示するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="18e81-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="18e81-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="18e81-116">See also</span></span>

- [<span data-ttu-id="18e81-117">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="18e81-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="18e81-118">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="18e81-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

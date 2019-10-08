---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004977"
---
# <a name="-verbose"></a><span data-ttu-id="2356a-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="2356a-102">-verbose</span></span>
<span data-ttu-id="2356a-103">コンパイラによって、詳細なステータスとエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2356a-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2356a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2356a-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2356a-105">引数</span><span class="sxs-lookup"><span data-stu-id="2356a-105">Arguments</span></span>  
 <span data-ttu-id="2356a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2356a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2356a-107">任意。</span><span class="sxs-lookup"><span data-stu-id="2356a-107">Optional.</span></span> <span data-ttu-id="2356a-108">@No__t-0 の指定は、`-verbose+` を指定した場合と同じです。これにより、コンパイラは詳細なメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="2356a-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="2356a-109">このオプションの既定値は `-verbose-` です。</span><span class="sxs-lookup"><span data-stu-id="2356a-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2356a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="2356a-110">Remarks</span></span>  
 <span data-ttu-id="2356a-111">@No__t-0 オプションは、コンパイラによって発行されたエラーの合計数に関する情報を表示し、どのアセンブリがモジュールによって読み込まれているかを報告し、現在コンパイルされているファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="2356a-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2356a-112">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2356a-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2356a-113">例</span><span class="sxs-lookup"><span data-stu-id="2356a-113">Example</span></span>  
 <span data-ttu-id="2356a-114">次のコードは `In.vb` をコンパイルし、詳細な状態情報を表示するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="2356a-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2356a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2356a-115">See also</span></span>

- [<span data-ttu-id="2356a-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2356a-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2356a-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2356a-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: c5bf988d819a8df8aed99588abbb30e19d14b1ac
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084984"
---
# <a name="-verbose"></a><span data-ttu-id="e5df0-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="e5df0-102">-verbose</span></span>

<span data-ttu-id="e5df0-103">コンパイラによって詳細なステータス メッセージとエラー メッセージが生成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="e5df0-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5df0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5df0-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5df0-105">引数</span><span class="sxs-lookup"><span data-stu-id="e5df0-105">Arguments</span></span>  

 <span data-ttu-id="e5df0-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e5df0-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e5df0-107">任意。</span><span class="sxs-lookup"><span data-stu-id="e5df0-107">Optional.</span></span> <span data-ttu-id="e5df0-108">`-verbose` を指定することは、`-verbose+` を指定することと同じです。これにより、コンパイラで詳細なメッセージが出力されます。</span><span class="sxs-lookup"><span data-stu-id="e5df0-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="e5df0-109">このオプションの既定値は `-verbose-` です。</span><span class="sxs-lookup"><span data-stu-id="e5df0-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5df0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5df0-110">Remarks</span></span>  

 <span data-ttu-id="e5df0-111">`-verbose` オプションでは、コンパイラによって発行されたエラーの合計数に関する情報を表示し、どのアセンブリがモジュールに読み込まれているかを報告します。また、どのファイルが現在コンパイルされているかを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5df0-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5df0-112">`-verbose` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5df0-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5df0-113">例</span><span class="sxs-lookup"><span data-stu-id="e5df0-113">Example</span></span>  

 <span data-ttu-id="e5df0-114">次のコードでは `In.vb` がコンパイルされ、詳細情報を表示するようにコンパイラに指示されます。</span><span class="sxs-lookup"><span data-stu-id="e5df0-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5df0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5df0-115">See also</span></span>

- [<span data-ttu-id="e5df0-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="e5df0-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e5df0-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="e5df0-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

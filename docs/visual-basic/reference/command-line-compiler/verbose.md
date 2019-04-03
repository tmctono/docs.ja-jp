---
title: -詳細
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832793"
---
# <a name="-verbose"></a><span data-ttu-id="534ec-102">-詳細</span><span class="sxs-lookup"><span data-stu-id="534ec-102">-verbose</span></span>
<span data-ttu-id="534ec-103">詳細なステータスおよびエラー メッセージを生成するためにコンパイラ ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="534ec-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="534ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="534ec-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="534ec-105">引数</span><span class="sxs-lookup"><span data-stu-id="534ec-105">Arguments</span></span>  
 <span data-ttu-id="534ec-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="534ec-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="534ec-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="534ec-107">Optional.</span></span> <span data-ttu-id="534ec-108">指定する`-verbose`は指定した場合と同じ`-verbose+`、これにより、コンパイラから詳細なメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="534ec-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="534ec-109">このオプションの既定値は`-verbose-`します。</span><span class="sxs-lookup"><span data-stu-id="534ec-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="534ec-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="534ec-110">Remarks</span></span>  
 <span data-ttu-id="534ec-111">`-verbose`オプションについては、コンパイラによって発行されたエラーの総数が表示されます、アセンブリ、モジュールから読み込んでいるおよびファイルがコンパイルされている現在が表示されます。</span><span class="sxs-lookup"><span data-stu-id="534ec-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="534ec-112">`-verbose`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="534ec-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="534ec-113">例</span><span class="sxs-lookup"><span data-stu-id="534ec-113">Example</span></span>  
 <span data-ttu-id="534ec-114">次のコードのコンパイル`In.vb`し、詳細なステータス情報を表示することをコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="534ec-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="534ec-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="534ec-115">See also</span></span>

- [<span data-ttu-id="534ec-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="534ec-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="534ec-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="534ec-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

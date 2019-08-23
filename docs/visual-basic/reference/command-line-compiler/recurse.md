---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956273"
---
# <a name="-recurse"></a><span data-ttu-id="f368e-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="f368e-102">-recurse</span></span>
<span data-ttu-id="f368e-103">指定されたディレクトリまたはプロジェクトディレクトリのすべての子ディレクトリにあるソースコードファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f368e-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f368e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f368e-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f368e-105">引数</span><span class="sxs-lookup"><span data-stu-id="f368e-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="f368e-106">任意。</span><span class="sxs-lookup"><span data-stu-id="f368e-106">Optional.</span></span> <span data-ttu-id="f368e-107">検索を開始するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="f368e-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="f368e-108">指定しない場合は、プロジェクトディレクトリから検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="f368e-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="f368e-109">必須。</span><span class="sxs-lookup"><span data-stu-id="f368e-109">Required.</span></span> <span data-ttu-id="f368e-110">検索するファイル。</span><span class="sxs-lookup"><span data-stu-id="f368e-110">The file(s) to search for.</span></span> <span data-ttu-id="f368e-111">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f368e-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f368e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="f368e-112">Remarks</span></span>  
 <span data-ttu-id="f368e-113">`-recurse` を使用せずにプロジェクト ディレクトリ内の一致するすべてのファイルをコンパイルするには、ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f368e-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="f368e-114">出力ファイル名が指定されない場合、コンパイラは処理する最初の入力ファイルに基づいて出力ファイル名を決定します。</span><span class="sxs-lookup"><span data-stu-id="f368e-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="f368e-115">これは一般に、コンパイルされるファイルの一覧をアルファベット順に表示したときの先頭のファイルです。</span><span class="sxs-lookup"><span data-stu-id="f368e-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="f368e-116">この理由から、出力ファイルは `-out` オプションを使用して指定するのが最善です。</span><span class="sxs-lookup"><span data-stu-id="f368e-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f368e-117">この`-recurse`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f368e-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f368e-118">例</span><span class="sxs-lookup"><span data-stu-id="f368e-118">Example</span></span>  
 <span data-ttu-id="f368e-119">次のコマンドは、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f368e-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="f368e-120">次のコマンドは、 `Test\ABC`ディレクトリ内のすべての Visual Basic ファイルとその下のすべてのディレクトリをコンパイルし、を生成`Test.ABC.dll`します。</span><span class="sxs-lookup"><span data-stu-id="f368e-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f368e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f368e-121">See also</span></span>

- [<span data-ttu-id="f368e-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="f368e-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f368e-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f368e-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="f368e-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="f368e-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

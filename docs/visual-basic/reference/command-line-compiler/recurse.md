---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095423"
---
# <a name="-recurse"></a><span data-ttu-id="a54af-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="a54af-102">-recurse</span></span>

<span data-ttu-id="a54af-103">指定したディレクトリまたはプロジェクト ディレクトリのすべての子ディレクトリ内のソース コード ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a54af-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54af-104">構文</span><span class="sxs-lookup"><span data-stu-id="a54af-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a54af-105">引数</span><span class="sxs-lookup"><span data-stu-id="a54af-105">Arguments</span></span>  

 `dir`  
 <span data-ttu-id="a54af-106">任意。</span><span class="sxs-lookup"><span data-stu-id="a54af-106">Optional.</span></span> <span data-ttu-id="a54af-107">検索を開始するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a54af-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="a54af-108">指定しない場合は、プロジェクト ディレクトリから検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="a54af-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="a54af-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="a54af-109">Required.</span></span> <span data-ttu-id="a54af-110">検索するファイル。</span><span class="sxs-lookup"><span data-stu-id="a54af-110">The file(s) to search for.</span></span> <span data-ttu-id="a54af-111">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a54af-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a54af-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="a54af-112">Remarks</span></span>  

 <span data-ttu-id="a54af-113">`-recurse` を使わなくても、ファイル名にワイルドカードを使用することで、プロジェクト ディレクトリ内の一致するすべてのファイルをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="a54af-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="a54af-114">出力ファイル名が指定されていない場合、コンパイラで最初に処理される入力ファイルに基づいて、出力ファイル名が決定されます。</span><span class="sxs-lookup"><span data-stu-id="a54af-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="a54af-115">これは通常、コンパイルされるファイルの一覧をアルファベット順に表示したときの先頭のファイルです。</span><span class="sxs-lookup"><span data-stu-id="a54af-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="a54af-116">このため、出力ファイルは `-out` オプションを使用して指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a54af-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a54af-117">`-recurse` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a54af-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a54af-118">例</span><span class="sxs-lookup"><span data-stu-id="a54af-118">Example</span></span>  

 <span data-ttu-id="a54af-119">次のコマンドでは、現在のディレクトリにあるすべての Visual Basic ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a54af-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="a54af-120">次のコマンドでは、`Test\ABC` ディレクトリとそれより下にあるすべてのディレクトリ内のすべての Visual Basic ファイルをコンパイルし、`Test.ABC.dll` を生成します。</span><span class="sxs-lookup"><span data-stu-id="a54af-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a54af-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a54af-121">See also</span></span>

- [<span data-ttu-id="a54af-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a54af-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a54af-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a54af-123">-out (Visual Basic)</span></span>](out.md)
- [<span data-ttu-id="a54af-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a54af-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

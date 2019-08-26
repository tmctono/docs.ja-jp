---
title: -recurse (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: c82e3019e1a1e3ba45a7000312b54b9d7f64a2db
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606743"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="bbe88-102">-recurse (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="bbe88-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="bbe88-103">-recurse オプションを使用すると、指定のディレクトリ (dir) またはプロジェクト ディレクトリのすべての子ディレクトリ内のソース コード ファイルをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="bbe88-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe88-104">構文</span><span class="sxs-lookup"><span data-stu-id="bbe88-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="bbe88-105">引数</span><span class="sxs-lookup"><span data-stu-id="bbe88-105">Arguments</span></span>  
 <span data-ttu-id="bbe88-106">`dir` (省略可能)</span><span class="sxs-lookup"><span data-stu-id="bbe88-106">`dir` (optional)</span></span>  
 <span data-ttu-id="bbe88-107">検索を開始するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="bbe88-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="bbe88-108">指定しない場合は、プロジェクト ディレクトリから検索されます。</span><span class="sxs-lookup"><span data-stu-id="bbe88-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="bbe88-109">検索するファイル。</span><span class="sxs-lookup"><span data-stu-id="bbe88-109">The file(s) to search for.</span></span> <span data-ttu-id="bbe88-110">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbe88-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe88-111">解説</span><span class="sxs-lookup"><span data-stu-id="bbe88-111">Remarks</span></span>  
 <span data-ttu-id="bbe88-112">**-recurse** オプションを使用すると、指定のディレクトリ (`dir`) またはプロジェクト ディレクトリのすべての子ディレクトリ内のソース コード ファイルをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="bbe88-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="bbe88-113">**-recurse** を使用しなくても、ファイル名にワイルドカードを使用すると、プロジェクト ディレクトリ内で一致するすべてのファイルをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="bbe88-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="bbe88-114">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe88-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe88-115">例</span><span class="sxs-lookup"><span data-stu-id="bbe88-115">Example</span></span>  
 <span data-ttu-id="bbe88-116">現在のディレクトリ内のすべての C# ファイルをコンパイルするには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe88-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="bbe88-117">dir1\dir2 ディレクトリおよびそのディレクトリの下の全ディレクトリ内の C# ファイルすべてをコンパイルし、dir2.dll を生成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe88-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbe88-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbe88-118">See also</span></span>

- [<span data-ttu-id="bbe88-119">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="bbe88-119">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="bbe88-120">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="bbe88-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

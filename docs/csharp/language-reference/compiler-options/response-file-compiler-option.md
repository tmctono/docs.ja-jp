---
title: '@ (C# コンパイラ オプション)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: d8e5c0ec148754c3e4cebfa32ad9f44a0bb0119e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "70202914"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="469e7-102">@ (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="469e7-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="469e7-103">@ オプションを使用すると、コンパイラ オプションおよびコンパイルするソース コード ファイルを含むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="469e7-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="469e7-104">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="469e7-105">引数</span><span class="sxs-lookup"><span data-stu-id="469e7-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="469e7-106">コンパイラ オプションやコンパイルするソース コード ファイルの一覧を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="469e7-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="469e7-107">解説</span><span class="sxs-lookup"><span data-stu-id="469e7-107">Remarks</span></span>  
 <span data-ttu-id="469e7-108">コンパイラ オプションとソース コード ファイルは、コマンド ラインで指定した場合と同じように、コンパイラによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="469e7-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="469e7-109">コンパイル時に複数の応答ファイルを指定するには、複数の応答ファイル オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="469e7-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="469e7-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="469e7-110">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="469e7-111">応答ファイルでは、複数のコンパイラ オプションとソース コード ファイルを 1 行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="469e7-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="469e7-112">1 つのコンパイラ オプションは 1 行に指定する必要があり、複数行にわたって指定できません。</span><span class="sxs-lookup"><span data-stu-id="469e7-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="469e7-113">応答ファイルには、シャープ記号 (#) で始まるコメントを記述できます。</span><span class="sxs-lookup"><span data-stu-id="469e7-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="469e7-114">応答ファイルでのコンパイラ オプションの指定方法は、コマンド ラインでのコンパイラ オプションの指定方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="469e7-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="469e7-115">詳細については、[コマンド ラインからのビルド](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="469e7-115">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="469e7-116">コンパイラは、検出した順にコマンド オプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="469e7-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="469e7-117">このため、コマンド ライン引数によって、応答ファイルで先に指定したオプションをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="469e7-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="469e7-118">逆に、応答ファイルのオプションが、コマンド ラインや他の応答ファイルで先に指定したオプションをオーバーライドすることもあります。</span><span class="sxs-lookup"><span data-stu-id="469e7-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="469e7-119">C# では、csc.exe ファイルと同じディレクトリに csc.rsp ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="469e7-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="469e7-120">csc.rsp の詳細については、「[-noconfig](./noconfig-compiler-option.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="469e7-120">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="469e7-121">このコンパイラ オプションは、Visual Studio 開発環境で設定することはできません。また、プログラムで変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="469e7-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="469e7-122">例</span><span class="sxs-lookup"><span data-stu-id="469e7-122">Example</span></span>  
 <span data-ttu-id="469e7-123">サンプルの応答ファイルの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="469e7-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="469e7-124">参照</span><span class="sxs-lookup"><span data-stu-id="469e7-124">See also</span></span>

- [<span data-ttu-id="469e7-125">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="469e7-125">C# Compiler Options</span></span>](./index.md)

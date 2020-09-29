---
description: '@ (C# コンパイラ オプション)'
title: '@ (C# コンパイラ オプション)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: 8f7e222e194fc4ba96159ecd792765f64b4d1c57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193754"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="6c843-103">@ (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6c843-103">@ (C# Compiler Options)</span></span>

<span data-ttu-id="6c843-104">@ オプションを使用すると、コンパイラ オプションおよびコンパイルするソース コード ファイルを含むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c843-104">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c843-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c843-105">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c843-106">引数</span><span class="sxs-lookup"><span data-stu-id="6c843-106">Arguments</span></span>  

 `response_file`  
 <span data-ttu-id="6c843-107">コンパイラ オプションやコンパイルするソース コード ファイルの一覧を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="6c843-107">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c843-108">注釈</span><span class="sxs-lookup"><span data-stu-id="6c843-108">Remarks</span></span>  

 <span data-ttu-id="6c843-109">コンパイラ オプションとソース コード ファイルは、コマンド ラインで指定した場合と同じように、コンパイラによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="6c843-109">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="6c843-110">コンパイル時に複数の応答ファイルを指定するには、複数の応答ファイル オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c843-110">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="6c843-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6c843-111">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="6c843-112">応答ファイルでは、複数のコンパイラ オプションとソース コード ファイルを 1 行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="6c843-112">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="6c843-113">1 つのコンパイラ オプションは 1 行に指定する必要があり、複数行にわたって指定できません。</span><span class="sxs-lookup"><span data-stu-id="6c843-113">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="6c843-114">応答ファイルには、シャープ記号 (#) で始まるコメントを記述できます。</span><span class="sxs-lookup"><span data-stu-id="6c843-114">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="6c843-115">応答ファイルでのコンパイラ オプションの指定方法は、コマンド ラインでのコンパイラ オプションの指定方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="6c843-115">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="6c843-116">詳細については、[コマンド ラインからのビルド](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) に関するページを参照してください。
</span><span class="sxs-lookup"><span data-stu-id="6c843-116">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="6c843-117">コンパイラは、検出した順にコマンド オプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="6c843-117">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="6c843-118">このため、コマンド ライン引数によって、応答ファイルで先に指定したオプションをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="6c843-118">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="6c843-119">逆に、応答ファイルのオプションが、コマンド ラインや他の応答ファイルで先に指定したオプションをオーバーライドすることもあります。</span><span class="sxs-lookup"><span data-stu-id="6c843-119">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="6c843-120">C# では、csc.exe ファイルと同じディレクトリに csc.rsp ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="6c843-120">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="6c843-121">csc.rsp の詳細については、「[-noconfig](./noconfig-compiler-option.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c843-121">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="6c843-122">このコンパイラ オプションは、Visual Studio 開発環境で設定することはできません。また、プログラムで変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="6c843-122">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c843-123">例</span><span class="sxs-lookup"><span data-stu-id="6c843-123">Example</span></span>  

 <span data-ttu-id="6c843-124">サンプルの応答ファイルの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c843-124">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c843-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c843-125">See also</span></span>

- [<span data-ttu-id="6c843-126">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="6c843-126">C# Compiler Options</span></span>](./index.md)

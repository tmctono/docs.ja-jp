---
title: '@ (応答ファイルの指定) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: deab111cc669941a1cd7dc143dd699b6521221bb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004991"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="e2446-102">@ (応答ファイルの指定) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2446-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="e2446-103">コンパイルするコンパイラオプションとソースコードファイルを含むファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2446-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2446-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2446-104">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2446-105">引数</span><span class="sxs-lookup"><span data-stu-id="e2446-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="e2446-106">必須。</span><span class="sxs-lookup"><span data-stu-id="e2446-106">Required.</span></span> <span data-ttu-id="e2446-107">コンパイルするコンパイラオプションまたはソースコードファイルの一覧を示すファイル。</span><span class="sxs-lookup"><span data-stu-id="e2446-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="e2446-108">ファイル名にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e2446-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2446-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e2446-109">Remarks</span></span>  
 <span data-ttu-id="e2446-110">コンパイラは、応答ファイルで指定されたコンパイラオプションとソースコードファイルを、コマンドラインで指定されているかのように処理します。</span><span class="sxs-lookup"><span data-stu-id="e2446-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="e2446-111">1つのコンパイルで複数の応答ファイルを指定するには、次のような複数の応答ファイルオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2446-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="e2446-112">応答ファイルでは、複数のコンパイラオプションとソースコードファイルを1行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="e2446-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="e2446-113">1つのコンパイラオプションの指定は、1行に記述する必要があります (複数行にまたがることはできません)。</span><span class="sxs-lookup"><span data-stu-id="e2446-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="e2446-114">応答ファイルには、@no__t 0 記号で始まるコメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e2446-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="e2446-115">コマンドラインで指定されたオプションを1つ以上の応答ファイルで指定されたオプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e2446-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="e2446-116">コンパイラは、コマンドオプションが検出されたときにそのオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="e2446-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="e2446-117">したがって、コマンドライン引数を使用すると、応答ファイルの以前に一覧表示されたオプションをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e2446-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="e2446-118">反対に、応答ファイルのオプションは、コマンドラインまたは他の応答ファイルで前述したオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e2446-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="e2446-119">Visual Basic には、Vbc.exe ファイルと同じディレクトリにある Vbc.exe ファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e2446-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="e2446-120">@No__t-0 オプションを使用しない限り、Vbc.exe ファイルは既定で含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2446-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="e2446-121">詳細については、「 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2446-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2446-122">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2446-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2446-123">例</span><span class="sxs-lookup"><span data-stu-id="e2446-123">Example</span></span>  
 <span data-ttu-id="e2446-124">次の行は、応答ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="e2446-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="e2446-125">例</span><span class="sxs-lookup"><span data-stu-id="e2446-125">Example</span></span>  
 <span data-ttu-id="e2446-126">次の例では、`@` オプションを `File1.rsp` という名前の応答ファイルと共に使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e2446-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2446-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2446-127">See also</span></span>

- [<span data-ttu-id="e2446-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="e2446-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e2446-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="e2446-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="e2446-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="e2446-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

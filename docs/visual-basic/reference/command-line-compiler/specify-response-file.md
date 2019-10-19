---
title: '@ (応答ファイルの指定) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 60206b6e42d329776948e8a0ef3c2e8e7e7d58bc
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583314"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="fc5f9-102">@ (応答ファイルの指定) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc5f9-102">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="fc5f9-103">コンパイルするコンパイラオプションとソースコードファイルを含むファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc5f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc5f9-104">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="fc5f9-105">引数</span><span class="sxs-lookup"><span data-stu-id="fc5f9-105">Arguments</span></span>

`response_file`  
<span data-ttu-id="fc5f9-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-106">Required.</span></span> <span data-ttu-id="fc5f9-107">コンパイルするコンパイラオプションまたはソースコードファイルの一覧を示すファイル。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="fc5f9-108">ファイル名にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc5f9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc5f9-109">Remarks</span></span>

<span data-ttu-id="fc5f9-110">コンパイラは、応答ファイルで指定されたコンパイラオプションとソースコードファイルを、コマンドラインで指定されているかのように処理します。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="fc5f9-111">1つのコンパイルで複数の応答ファイルを指定するには、次のような複数の応答ファイルオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="fc5f9-112">応答ファイルでは、複数のコンパイラオプションとソースコードファイルを1行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="fc5f9-113">1つのコンパイラオプションの指定は、1行に記述する必要があります (複数行にまたがることはできません)。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="fc5f9-114">応答ファイルには、`#` 記号で始まるコメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-114">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="fc5f9-115">コマンドラインで指定されたオプションを1つ以上の応答ファイルで指定されたオプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="fc5f9-116">コンパイラは、コマンドオプションが検出されたときにそのオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="fc5f9-117">したがって、コマンドライン引数を使用すると、応答ファイルの以前に一覧表示されたオプションをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="fc5f9-118">反対に、応答ファイルのオプションは、コマンドラインまたは他の応答ファイルで前述したオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="fc5f9-119">Visual Basic には、Vbc.exe ファイルと同じディレクトリにある Vbc.exe ファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="fc5f9-120">@No__t_0 オプションを使用しない限り、Vbc.exe ファイルは既定で含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="fc5f9-121">詳細については、「 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fc5f9-122">@No__t_0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="fc5f9-123">例</span><span class="sxs-lookup"><span data-stu-id="fc5f9-123">Example</span></span>

<span data-ttu-id="fc5f9-124">次の行は、応答ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-124">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="fc5f9-125">例</span><span class="sxs-lookup"><span data-stu-id="fc5f9-125">Example</span></span>

<span data-ttu-id="fc5f9-126">次の例では、`@` オプションを `File1.rsp` という名前の応答ファイルと共に使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fc5f9-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="fc5f9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc5f9-127">See also</span></span>

- [<span data-ttu-id="fc5f9-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="fc5f9-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fc5f9-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="fc5f9-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="fc5f9-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="fc5f9-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

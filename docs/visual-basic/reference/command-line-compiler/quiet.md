---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005283"
---
# <a name="-quiet"></a><span data-ttu-id="e4577-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="e4577-102">-quiet</span></span>

<span data-ttu-id="e4577-103">コンパイラで構文関連のエラーと警告のコードが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="e4577-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4577-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4577-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="e4577-105">コメント</span><span class="sxs-lookup"><span data-stu-id="e4577-105">Remarks</span></span>

<span data-ttu-id="e4577-106">既定では、`-quiet` は無効です。</span><span class="sxs-lookup"><span data-stu-id="e4577-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="e4577-107">コンパイラは、構文に関連するエラーまたは警告を報告するときに、ソースコードから行を出力します。</span><span class="sxs-lookup"><span data-stu-id="e4577-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="e4577-108">コンパイラの出力を解析するアプリケーションでは、コンパイラが診断のテキストのみを出力する方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4577-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="e4577-109">次の例では、`Module1` は、`-quiet` を指定せずにコンパイルされた場合にソースコードを含むエラーを出力します。</span><span class="sxs-lookup"><span data-stu-id="e4577-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="e4577-110">Output:</span><span class="sxs-lookup"><span data-stu-id="e4577-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="e4577-111">@No__t-0 を使用してコンパイルされた場合、コンパイラは次のものだけを出力します。</span><span class="sxs-lookup"><span data-stu-id="e4577-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="e4577-112">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4577-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="e4577-113">例</span><span class="sxs-lookup"><span data-stu-id="e4577-113">Example</span></span>

<span data-ttu-id="e4577-114">次のコードは `T2.vb` をコンパイルし、構文に関連するコンパイラ診断のコードを表示しません。</span><span class="sxs-lookup"><span data-stu-id="e4577-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="e4577-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4577-115">See also</span></span>

- [<span data-ttu-id="e4577-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="e4577-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e4577-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="e4577-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

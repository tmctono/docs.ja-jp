---
title: ソース行、ファイル、およびパスの識別子
description: 組み込み F# 識別子の値を使用するソース行番号、ディレクトリ、およびファイル名をコードにアクセスできるようにする方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 4b145fe1fe20e3d7f868558e33bab26204fb0125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663623"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="3cee6-103">ソース行、ファイル、およびパスの識別子</span><span class="sxs-lookup"><span data-stu-id="3cee6-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="3cee6-104">識別子`__LINE__`、`__SOURCE_DIRECTORY__`と`__SOURCE_FILE__`は、コードのソース行番号、ディレクトリおよびファイル名にアクセスするための組み込みの値です。</span><span class="sxs-lookup"><span data-stu-id="3cee6-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cee6-105">構文</span><span class="sxs-lookup"><span data-stu-id="3cee6-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="3cee6-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cee6-106">Remarks</span></span>

<span data-ttu-id="3cee6-107">これらの値の各種類には`string`します。</span><span class="sxs-lookup"><span data-stu-id="3cee6-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="3cee6-108">次の表は、ソース行、ファイル、および F# で使用できるパスの識別子を示します。</span><span class="sxs-lookup"><span data-stu-id="3cee6-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="3cee6-109">これらの識別子でないプリプロセッサ マクロこれらは、コンパイラによって認識される組み込みの値です。</span><span class="sxs-lookup"><span data-stu-id="3cee6-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="3cee6-110">事前定義の識別子</span><span class="sxs-lookup"><span data-stu-id="3cee6-110">Predefined identifier</span></span>|<span data-ttu-id="3cee6-111">説明</span><span class="sxs-lookup"><span data-stu-id="3cee6-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="3cee6-112">現在の行番号に評価を検討して`#line`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="3cee6-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="3cee6-113">ソース ディレクトリの現在の完全なパスに評価を検討して`#line`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="3cee6-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="3cee6-114">現在のソース ファイル名と、そのパスに評価を検討して`#line`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="3cee6-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|

<span data-ttu-id="3cee6-115">詳細については、`#line`ディレクティブを参照してください[コンパイラ ディレクティブ](compiler-directives.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cee6-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="3cee6-116">例</span><span class="sxs-lookup"><span data-stu-id="3cee6-116">Example</span></span>

<span data-ttu-id="3cee6-117">次のコード例では、これらの値の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="3cee6-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="3cee6-118">Output:</span><span class="sxs-lookup"><span data-stu-id="3cee6-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="3cee6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cee6-119">See also</span></span>

- [<span data-ttu-id="3cee6-120">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3cee6-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="3cee6-121">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="3cee6-121">F# Language Reference</span></span>](index.md)

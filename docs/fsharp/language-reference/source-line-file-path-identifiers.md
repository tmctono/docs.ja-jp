---
title: ソース行、ファイル、およびパスの識別子
description: 組み込みのF#識別子値を使用して、コード内のソース行番号、ディレクトリ、およびファイル名にアクセスできるようにする方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216751"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="64e12-103">ソース行、ファイル、およびパスの識別子</span><span class="sxs-lookup"><span data-stu-id="64e12-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="64e12-104">識別子`__LINE__` `__SOURCE_DIRECTORY__`とは、コード内のソース行番号、ディレクトリ、およびファイル名にアクセスできるようにする組み込みの値です。`__SOURCE_FILE__`</span><span class="sxs-lookup"><span data-stu-id="64e12-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="64e12-105">構文</span><span class="sxs-lookup"><span data-stu-id="64e12-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="64e12-106">コメント</span><span class="sxs-lookup"><span data-stu-id="64e12-106">Remarks</span></span>

<span data-ttu-id="64e12-107">これらの各値には`string`型があります。</span><span class="sxs-lookup"><span data-stu-id="64e12-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="64e12-108">次の表は、でF#使用できるソース行、ファイル、およびパスの識別子をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="64e12-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="64e12-109">これらの識別子はプリプロセッサマクロではありません。これらは、コンパイラによって認識される組み込みの値です。</span><span class="sxs-lookup"><span data-stu-id="64e12-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="64e12-110">定義済み識別子</span><span class="sxs-lookup"><span data-stu-id="64e12-110">Predefined identifier</span></span>|<span data-ttu-id="64e12-111">説明</span><span class="sxs-lookup"><span data-stu-id="64e12-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="64e12-112">ディレクティブを考慮`#line`して、現在の行番号に評価されます。</span><span class="sxs-lookup"><span data-stu-id="64e12-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="64e12-113">ディレクティブを考慮`#line`して、ソースディレクトリの現在の完全パスに評価されます。</span><span class="sxs-lookup"><span data-stu-id="64e12-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="64e12-114">ディレクティブを考慮`#line`して、パスを除いた現在のソースファイル名に評価されます。</span><span class="sxs-lookup"><span data-stu-id="64e12-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="64e12-115">ディレクティブの`#line`詳細については、「[コンパイラディレクティブ](compiler-directives.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64e12-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="64e12-116">例</span><span class="sxs-lookup"><span data-stu-id="64e12-116">Example</span></span>

<span data-ttu-id="64e12-117">これらの値の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="64e12-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="64e12-118">Output:</span><span class="sxs-lookup"><span data-stu-id="64e12-118">Output:</span></span>

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="64e12-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="64e12-119">See also</span></span>

- [<span data-ttu-id="64e12-120">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="64e12-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="64e12-121">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="64e12-121">F# Language Reference</span></span>](index.md)

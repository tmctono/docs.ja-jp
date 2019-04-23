---
title: C# プリプロセッサ ディレクティブ
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 54067777ed2e92eea263b17cce0d4cdf13ed731d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689321"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="ba73b-102">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ba73b-102">C# preprocessor directives</span></span>
<span data-ttu-id="ba73b-103">このセクションでは、次の C# プリプロセッサ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba73b-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="ba73b-104">#if</span><span class="sxs-lookup"><span data-stu-id="ba73b-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="ba73b-105">#else</span><span class="sxs-lookup"><span data-stu-id="ba73b-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="ba73b-106">#elif</span><span class="sxs-lookup"><span data-stu-id="ba73b-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="ba73b-107">#endif</span><span class="sxs-lookup"><span data-stu-id="ba73b-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="ba73b-108">#define</span><span class="sxs-lookup"><span data-stu-id="ba73b-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="ba73b-109">#undef</span><span class="sxs-lookup"><span data-stu-id="ba73b-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="ba73b-110">#warning</span><span class="sxs-lookup"><span data-stu-id="ba73b-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="ba73b-111">#error</span><span class="sxs-lookup"><span data-stu-id="ba73b-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="ba73b-112">#line</span><span class="sxs-lookup"><span data-stu-id="ba73b-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="ba73b-113">#region</span><span class="sxs-lookup"><span data-stu-id="ba73b-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="ba73b-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="ba73b-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="ba73b-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="ba73b-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="ba73b-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="ba73b-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="ba73b-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="ba73b-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="ba73b-118">詳細および例については、個々のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba73b-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="ba73b-119">コンパイラに個別のプリプロセッサはありませんが、このセクションに示すディレクティブは、ある場合と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="ba73b-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="ba73b-120">これらは条件付きコンパイルに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba73b-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="ba73b-121">C や C++ のディレクティブとは異なり、マクロを作成するのにこれらのディレクティブを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ba73b-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="ba73b-122">プリプロセッサ ディレクティブは、行の唯一の命令である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba73b-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba73b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba73b-123">See also</span></span>

- [<span data-ttu-id="ba73b-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ba73b-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="ba73b-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ba73b-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

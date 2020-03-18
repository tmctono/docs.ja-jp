---
title: C# プリプロセッサ ディレクティブ
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "69608601"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="661d2-102">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="661d2-102">C# preprocessor directives</span></span>
<span data-ttu-id="661d2-103">このセクションでは、次の C# プリプロセッサ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="661d2-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="661d2-104">#if</span><span class="sxs-lookup"><span data-stu-id="661d2-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="661d2-105">#else</span><span class="sxs-lookup"><span data-stu-id="661d2-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="661d2-106">#elif</span><span class="sxs-lookup"><span data-stu-id="661d2-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="661d2-107">#endif</span><span class="sxs-lookup"><span data-stu-id="661d2-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="661d2-108">#define</span><span class="sxs-lookup"><span data-stu-id="661d2-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="661d2-109">#undef</span><span class="sxs-lookup"><span data-stu-id="661d2-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="661d2-110">#warning</span><span class="sxs-lookup"><span data-stu-id="661d2-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="661d2-111">#error</span><span class="sxs-lookup"><span data-stu-id="661d2-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="661d2-112">#line</span><span class="sxs-lookup"><span data-stu-id="661d2-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="661d2-113">#region</span><span class="sxs-lookup"><span data-stu-id="661d2-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="661d2-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="661d2-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="661d2-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="661d2-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="661d2-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="661d2-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="661d2-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="661d2-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="661d2-118">詳細および例については、個々のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="661d2-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="661d2-119">コンパイラに個別のプリプロセッサはありませんが、このセクションに示すディレクティブは、ある場合と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="661d2-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="661d2-120">これらは条件付きコンパイルに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="661d2-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="661d2-121">C や C++ のディレクティブとは異なり、マクロを作成するのにこれらのディレクティブを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="661d2-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="661d2-122">プリプロセッサ ディレクティブは、行の唯一の命令である必要があります。</span><span class="sxs-lookup"><span data-stu-id="661d2-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="661d2-123">参照</span><span class="sxs-lookup"><span data-stu-id="661d2-123">See also</span></span>

- [<span data-ttu-id="661d2-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="661d2-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="661d2-125">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="661d2-125">C# Programming Guide</span></span>](../../programming-guide/index.md)

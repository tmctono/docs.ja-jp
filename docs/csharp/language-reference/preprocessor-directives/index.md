---
description: C# プリプロセッサ ディレクティブ
title: C# プリプロセッサ ディレクティブ
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: a7ffca8b39f1bd9f05193bccbb6d90e67fa262c9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132366"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="1d9f4-103">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="1d9f4-103">C# preprocessor directives</span></span>
<span data-ttu-id="1d9f4-104">このセクションでは、次の C# プリプロセッサ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="1d9f4-105">#if</span><span class="sxs-lookup"><span data-stu-id="1d9f4-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="1d9f4-106">#else</span><span class="sxs-lookup"><span data-stu-id="1d9f4-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="1d9f4-107">#elif</span><span class="sxs-lookup"><span data-stu-id="1d9f4-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="1d9f4-108">#endif</span><span class="sxs-lookup"><span data-stu-id="1d9f4-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="1d9f4-109">#define</span><span class="sxs-lookup"><span data-stu-id="1d9f4-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="1d9f4-110">#undef</span><span class="sxs-lookup"><span data-stu-id="1d9f4-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="1d9f4-111">#warning</span><span class="sxs-lookup"><span data-stu-id="1d9f4-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="1d9f4-112">#error</span><span class="sxs-lookup"><span data-stu-id="1d9f4-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="1d9f4-113">#line</span><span class="sxs-lookup"><span data-stu-id="1d9f4-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="1d9f4-114">#region</span><span class="sxs-lookup"><span data-stu-id="1d9f4-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="1d9f4-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="1d9f4-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="1d9f4-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="1d9f4-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="1d9f4-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="1d9f4-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="1d9f4-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="1d9f4-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="1d9f4-119">詳細および例については、個々のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="1d9f4-120">コンパイラに個別のプリプロセッサはありませんが、このセクションに示すディレクティブは、ある場合と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="1d9f4-121">これらは条件付きコンパイルに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="1d9f4-122">C や C++ のディレクティブとは異なり、マクロを作成するのにこれらのディレクティブを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="1d9f4-123">プリプロセッサ ディレクティブは、行の唯一の命令である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d9f4-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d9f4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d9f4-124">See also</span></span>

- [<span data-ttu-id="1d9f4-125">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1d9f4-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1d9f4-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1d9f4-126">C# Programming Guide</span></span>](../../programming-guide/index.md)

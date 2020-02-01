---
title: コンパイラのエラーと警告
description: F#コンパイラによって生成されるエラーと警告の説明と解決策
ms.date: 12/21/2019
ms.openlocfilehash: 52d94475e8b0195281d6244230c50c8f64230aeb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76929655"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="5a7aa-103">F#コンパイラメッセージ</span><span class="sxs-lookup"><span data-stu-id="5a7aa-103">F# compiler messages</span></span>

<span data-ttu-id="5a7aa-104">このセクションでは、コンパイラが特定のF#構成要素に対して生成するコンパイラのエラーと警告について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="5a7aa-105">既定のエラーセットは、次の方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="5a7aa-106">`-warnaserror+` コンパイラオプションを使用して、特定の警告をエラーとして扱います。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="5a7aa-107">`-nowarn` コンパイラオプションを使用して特定の警告を無視する</span><span class="sxs-lookup"><span data-stu-id="5a7aa-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="5a7aa-108">このセクションに特定の警告またはエラーがまだ記録されていない場合は、このページの最後に移動して、エラーの数またはテキストが記載されたフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-108">If a particular warning or error is not yet recorded in this section, go to the end of this page and send feedback that includes the number or text of the error.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a7aa-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a7aa-109">See also</span></span>

- [<span data-ttu-id="5a7aa-110">F#コンパイラオプション</span><span class="sxs-lookup"><span data-stu-id="5a7aa-110">F# Compiler Options</span></span>](../compiler-options.md)

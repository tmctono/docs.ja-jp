---
title: partial メソッド - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 62efd8b47fb565316b417a65e1b0fe37e40786c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713223"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="47913-102">partial (メソッド) (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="47913-102">partial method (C# Reference)</span></span>

<span data-ttu-id="47913-103">部分メソッドには、部分型の一部に定義されたシグネチャ、および部分型の別の部分に定義された実装があります。</span><span class="sxs-lookup"><span data-stu-id="47913-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="47913-104">部分メソッドを使用すると、イベント ハンドラーと同じように、開発者が実装するかどうかを決定できるメソッド フックをクラス デザイナーで提供できます。</span><span class="sxs-lookup"><span data-stu-id="47913-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="47913-105">開発者が実装を指定しない場合、コンパイラはコンパイル時にシグネチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="47913-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="47913-106">部分メソッドには次の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="47913-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="47913-107">部分型の両方の部分のシグネチャが一致する必要がある。</span><span class="sxs-lookup"><span data-stu-id="47913-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="47913-108">メソッドが void を返す必要がある。</span><span class="sxs-lookup"><span data-stu-id="47913-108">The method must return void.</span></span>

- <span data-ttu-id="47913-109">アクセス修飾子はできない。</span><span class="sxs-lookup"><span data-stu-id="47913-109">No access modifiers are allowed.</span></span> <span data-ttu-id="47913-110">部分メソッドは暗黙的にプライベート メソッドになる。</span><span class="sxs-lookup"><span data-stu-id="47913-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="47913-111">部分クラスの 2 つの部分に定義された部分メソッドを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="47913-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="47913-112">詳細については、「[部分クラスと部分メソッド](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47913-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47913-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="47913-113">See also</span></span>

- [<span data-ttu-id="47913-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="47913-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47913-115">partial 型</span><span class="sxs-lookup"><span data-stu-id="47913-115">partial type</span></span>](partial-type.md)

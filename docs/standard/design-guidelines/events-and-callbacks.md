---
title: イベントとコールバック
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741657"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="a435d-102">イベントとコールバック</span><span class="sxs-lookup"><span data-stu-id="a435d-102">Events and Callbacks</span></span>
<span data-ttu-id="a435d-103">コールバックは、フレームワークがデリゲートを通じてユーザーコードにコールバックすることを可能にする拡張ポイントです。</span><span class="sxs-lookup"><span data-stu-id="a435d-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="a435d-104">これらのデリゲートは、通常、メソッドのパラメーターを使用してフレームワークに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a435d-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="a435d-105">イベントは、デリゲート (イベントハンドラー) を提供するための便利で一貫性のある構文をサポートする、特殊なコールバックのケースです。</span><span class="sxs-lookup"><span data-stu-id="a435d-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="a435d-106">さらに、Visual Studio のステートメント入力候補とデザイナーは、イベントベースの Api の使用に関するヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="a435d-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="a435d-107">(「[イベントの設計](../../../docs/standard/design-guidelines/event.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a435d-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>

 <span data-ttu-id="a435d-108">✔️コールバックを使用して、ユーザーがフレームワークによって実行されるカスタムコードを提供できるようにすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a435d-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="a435d-109">✔️イベントを使用して、ユーザーがオブジェクト指向設計を理解しなくても、フレームワークの動作をカスタマイズできるようにすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a435d-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="a435d-110">✔️は、より幅広い開発者を対象とし、Visual Studio のステートメント入力候補と統合されるため、プレーンコールバックでイベントを優先します。</span><span class="sxs-lookup"><span data-stu-id="a435d-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="a435d-111">パフォーマンスを重視する Api では、コールバックを使用しないように ❌ します。</span><span class="sxs-lookup"><span data-stu-id="a435d-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="a435d-112">コールバックを使用して Api を定義するときは、カスタムデリゲートではなく、新しい `Func<...>`、`Action<...>`、または `Expression<...>` 型を使用✔️ます。</span><span class="sxs-lookup"><span data-stu-id="a435d-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="a435d-113">`Func<...>` と `Action<...>` は汎用デリゲートを表します。</span><span class="sxs-lookup"><span data-stu-id="a435d-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="a435d-114">`Expression<...>` は、コンパイル後に実行時に呼び出すことができる関数定義を表しますが、シリアル化してリモートプロセスに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a435d-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="a435d-115">✔️は、`Func<...>` と `Action<...>` デリゲートを使用する代わりに、`Expression<...>`を使用した場合のパフォーマンスへの影響を測定して理解します。</span><span class="sxs-lookup"><span data-stu-id="a435d-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="a435d-116">`Expression<...>` 型は、ほとんどの場合、`Func<...>` と `Action<...>` デリゲートと論理的に等価です。</span><span class="sxs-lookup"><span data-stu-id="a435d-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="a435d-117">これらの主な違いは、デリゲートはローカルプロセスシナリオで使用することを意図していることです。式は、リモートのプロセスまたはコンピューターで式を評価することが有益であるケースを対象としています。</span><span class="sxs-lookup"><span data-stu-id="a435d-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="a435d-118">デリゲートを呼び出すことによって、任意のコードを実行し、セキュリティ、正確性、および互換性の影響を与える可能性があることを✔️理解することができます。</span><span class="sxs-lookup"><span data-stu-id="a435d-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="a435d-119">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a435d-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a435d-120">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a435d-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a435d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a435d-121">See also</span></span>

- [<span data-ttu-id="a435d-122">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="a435d-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="a435d-123">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a435d-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

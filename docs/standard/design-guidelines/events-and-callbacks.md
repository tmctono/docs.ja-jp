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
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709414"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="9fa4c-102">イベントとコールバック</span><span class="sxs-lookup"><span data-stu-id="9fa4c-102">Events and Callbacks</span></span>
<span data-ttu-id="9fa4c-103">コールバックは、フレームワークがデリゲートを通じてユーザーコードにコールバックすることを可能にする拡張ポイントです。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="9fa4c-104">これらのデリゲートは、通常、メソッドのパラメーターを使用してフレームワークに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="9fa4c-105">イベントは、デリゲート (イベントハンドラー) を提供するための便利で一貫性のある構文をサポートする、特殊なコールバックのケースです。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="9fa4c-106">さらに、Visual Studio のステートメント入力候補とデザイナーは、イベントベースの Api の使用に関するヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="9fa4c-107">(「[イベントの設計](../../../docs/standard/design-guidelines/event.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="9fa4c-108">**✓ CONSIDER** コールバックを使用して、フレームワークによって実行されるカスタム コードを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="9fa4c-109">**✓ CONSIDER** イベントを使用したオブジェクト指向設計を理解することがなくてもフレームワークの動作をカスタマイズできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="9fa4c-110">**✓ DO** 幅広い開発者になじみのあるは、ステートメント入力候補の Visual Studio と統合されたために、イベントを単純なコールバックよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="9fa4c-111">**X AVOID** パフォーマンス重視の Api でのコールバックを使用します。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="9fa4c-112">**✓ DO** 新しい`Func<...>`、 `Action<...>`、または`Expression<...>`コールバックで Api を定義するときに、カスタム デリゲートではなく型です。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="9fa4c-113">`Func<...>` と `Action<...>` は汎用デリゲートを表します。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="9fa4c-114">`Expression<...>` は、コンパイル後に実行時に呼び出すことができる関数定義を表しますが、シリアル化してリモートプロセスに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="9fa4c-115">**✓ DO** を測定しを使用するパフォーマンスの影響について理解する`Expression<...>`、使用する代わりに`Func<...>`と`Action<...>`デリゲート。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="9fa4c-116">`Expression<...>` 型は、ほとんどの場合、`Func<...>` と `Action<...>` デリゲートと論理的に等価です。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="9fa4c-117">これらの主な違いは、デリゲートはローカルプロセスシナリオで使用することを意図していることです。式は、リモートのプロセスまたはコンピューターで式を評価することが有益であるケースを対象としています。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="9fa4c-118">**✓ DO** するデリゲートを呼び出すことによって実行している任意のコードを理解し、セキュリティ、正確性、および互換性への影響を与える可能性です。</span><span class="sxs-lookup"><span data-stu-id="9fa4c-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="9fa4c-119">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="9fa4c-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9fa4c-120">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="9fa4c-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa4c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fa4c-121">See also</span></span>

- [<span data-ttu-id="9fa4c-122">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="9fa4c-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="9fa4c-123">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9fa4c-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

---
title: シールされていないクラス
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: d7174de7ddf062b829672e04952c1010fcb74058
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778795"
---
# <a name="unsealed-classes"></a><span data-ttu-id="8bfa3-102">シールされていないクラス</span><span class="sxs-lookup"><span data-stu-id="8bfa3-102">Unsealed Classes</span></span>
<span data-ttu-id="8bfa3-103">シール クラスから継承することはできませんし、機能拡張は、します。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="8bfa3-104">これに対し、封印されていないクラスから継承できるクラスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="8bfa3-105">**✓ CONSIDER** 安価なを提供するのにまだ高く評価されたフレームワークを拡張機能として、仮想またはプロテクト メンバーを追加なしで封印されていないクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="8bfa3-106">多くの場合、開発者はカスタム コンス トラクター、新しいメソッドは、メソッドのオーバー ロードなどの便利なメンバーを追加するための封印されていないクラスから継承したいと考えているとします。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="8bfa3-107">たとえば、`System.Messaging.MessageQueue`が封印されていないと、できるので、ユーザーがその既定値を特定のキューのパスにカスタムのキューを作成する特定のシナリオ用の API を簡略化するカスタム メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="8bfa3-108">既定ではほとんどのプログラミング言語でクラスが封印されていないし、これは、推奨された既定のフレームワークのほとんどのクラスにもします。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="8bfa3-109">封印されていない型によって提供される拡張機能は、フレームワークのユーザーによって非常にありがたいと封印されていない型に関連付けられている相対的に低いテスト コストのために提供する非常に低コストです。</span><span class="sxs-lookup"><span data-stu-id="8bfa3-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="8bfa3-110">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="8bfa3-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8bfa3-111">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="8bfa3-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bfa3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfa3-112">See also</span></span>

- [<span data-ttu-id="8bfa3-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="8bfa3-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="8bfa3-114">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="8bfa3-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="8bfa3-115">シール</span><span class="sxs-lookup"><span data-stu-id="8bfa3-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)

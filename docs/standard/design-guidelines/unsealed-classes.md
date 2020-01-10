---
title: シールされていないクラス
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8a5f1142674f83b5ef77f9f7e7e3518afd475e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709011"
---
# <a name="unsealed-classes"></a><span data-ttu-id="4d959-102">シールされていないクラス</span><span class="sxs-lookup"><span data-stu-id="4d959-102">Unsealed Classes</span></span>
<span data-ttu-id="4d959-103">シールされたクラスはから継承できません。また、拡張を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="4d959-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="4d959-104">これに対し、から継承できるクラスは、シールされていないクラスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4d959-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="4d959-105">**✓ CONSIDER** 安価なを提供するのにまだ高く評価されたフレームワークを拡張機能として、仮想またはプロテクト メンバーを追加なしで封印されていないクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d959-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="4d959-106">開発者は、カスタムコンストラクター、新しいメソッド、メソッドオーバーロードなどの便利なメンバーを追加するために、シールされていないクラスから継承することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4d959-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="4d959-107">たとえば、`System.Messaging.MessageQueue` が封印されていないため、ユーザーは特定のキューのパスを既定とするカスタムキューを作成したり、特定のシナリオで API を簡略化するカスタムメソッドを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="4d959-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="4d959-108">ほとんどのプログラミング言語では、クラスは既定で封印されていません。これは、フレームワークのほとんどのクラスで既定でも推奨されます。</span><span class="sxs-lookup"><span data-stu-id="4d959-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="4d959-109">封印されていない型によって実現される機能拡張は、フレームワークユーザーにとって非常に歓迎されており、封印されていない型に関連するテストコストが比較的低いため、非常に安価です</span><span class="sxs-lookup"><span data-stu-id="4d959-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="4d959-110">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="4d959-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4d959-111">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="4d959-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d959-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d959-112">See also</span></span>

- [<span data-ttu-id="4d959-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="4d959-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4d959-114">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="4d959-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="4d959-115">シール</span><span class="sxs-lookup"><span data-stu-id="4d959-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)

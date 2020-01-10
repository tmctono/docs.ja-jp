---
title: メンバーのデザインのガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709271"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="1c36b-102">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1c36b-102">Member Design Guidelines</span></span>
<span data-ttu-id="1c36b-103">メソッド、プロパティ、イベント、コンストラクター、およびフィールドは、総称してメンバーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1c36b-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="1c36b-104">フレームワークのエンドユーザーに公開されるフレームワークの機能は、最終的にメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="1c36b-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="1c36b-105">メンバーは、仮想または非仮想、具象または抽象、静的、またはインスタンスにすることができ、アクセシビリティの複数の異なるスコープを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1c36b-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="1c36b-106">これらはすべて、非常に優れた表現力を提供しますが、同時にフレームワークデザイナーの一部に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c36b-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="1c36b-107">この章では、任意の型のメンバーを設計する際に従う必要がある基本的なガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1c36b-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c36b-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1c36b-108">In This Section</span></span>  
 [<span data-ttu-id="1c36b-109">メンバーのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="1c36b-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="1c36b-110">プロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="1c36b-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="1c36b-111">コンストラクターのデザイン</span><span class="sxs-lookup"><span data-stu-id="1c36b-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="1c36b-112">イベントのデザイン</span><span class="sxs-lookup"><span data-stu-id="1c36b-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="1c36b-113">フィールドのデザイン</span><span class="sxs-lookup"><span data-stu-id="1c36b-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="1c36b-114">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="1c36b-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="1c36b-115">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="1c36b-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="1c36b-116">パラメーターのデザイン</span><span class="sxs-lookup"><span data-stu-id="1c36b-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="1c36b-117">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="1c36b-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1c36b-118">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="1c36b-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c36b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c36b-119">See also</span></span>

- [<span data-ttu-id="1c36b-120">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1c36b-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

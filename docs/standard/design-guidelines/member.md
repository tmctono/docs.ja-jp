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
ms.openlocfilehash: c323e7edd752a1f003bd3f5d81689aca0eaefd20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288993"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="cf493-102">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cf493-102">Member Design Guidelines</span></span>
<span data-ttu-id="cf493-103">メソッド、プロパティ、イベント、コンストラクター、およびフィールドは、総称してメンバーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cf493-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="cf493-104">フレームワークのエンドユーザーに公開されるフレームワークの機能は、最終的にメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="cf493-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="cf493-105">メンバーは、仮想または非仮想、具象または抽象、静的、またはインスタンスにすることができ、アクセシビリティの複数の異なるスコープを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="cf493-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="cf493-106">これらはすべて、非常に優れた表現力を提供しますが、同時にフレームワークデザイナーの一部に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf493-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="cf493-107">この章では、任意の型のメンバーを設計する際に従う必要がある基本的なガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf493-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf493-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cf493-108">In This Section</span></span>  
 [<span data-ttu-id="cf493-109">メンバーのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="cf493-109">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="cf493-110">プロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="cf493-110">Property Design</span></span>](property.md)  
 [<span data-ttu-id="cf493-111">コンストラクターのデザイン</span><span class="sxs-lookup"><span data-stu-id="cf493-111">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="cf493-112">イベントのデザイン</span><span class="sxs-lookup"><span data-stu-id="cf493-112">Event Design</span></span>](event.md)  
 [<span data-ttu-id="cf493-113">フィールドのデザイン</span><span class="sxs-lookup"><span data-stu-id="cf493-113">Field Design</span></span>](field.md)  
 [<span data-ttu-id="cf493-114">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="cf493-114">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="cf493-115">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="cf493-115">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="cf493-116">パラメーターのデザイン</span><span class="sxs-lookup"><span data-stu-id="cf493-116">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="cf493-117">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="cf493-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cf493-118">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="cf493-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf493-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf493-119">See also</span></span>

- [<span data-ttu-id="cf493-120">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cf493-120">Framework Design Guidelines</span></span>](index.md)

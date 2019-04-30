---
title: フィールドのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 3ab8fe279605c4795bb3a26557d0241b186b273a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026407"
---
# <a name="field-design"></a><span data-ttu-id="1ad2b-102">フィールドのデザイン</span><span class="sxs-lookup"><span data-stu-id="1ad2b-102">Field Design</span></span>
<span data-ttu-id="1ad2b-103">カプセル化の原理は、最も重要な概念の 1 つをオブジェクト指向設計にです。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="1ad2b-104">この原則は、データ オブジェクト内に格納されますが、そのオブジェクトのみがアクセスできるがあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="1ad2b-105">原則を解釈する便利な方法は、型のメンバー以外のコードを損なうことがなくその型 (名前または種類の変更) のフィールドに変更ができるように、型を設計する必要がありますには。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="1ad2b-106">この解釈は、すぐに、すべてのフィールドがプライベートでなければならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="1ad2b-107">定数と静的な読み取り専用フィールドは、このようなフィールドの定義によってほぼ必要はまったくありませんを変更するために、この厳密な制限から除外します。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="1ad2b-108">**X DO NOT** パブリックまたは保護されたインスタンス フィールドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="1ad2b-109">Public または protected にする代わりにフィールドへのアクセスのプロパティを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="1ad2b-110">**✓ DO** は決して変化しない定数の定数フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="1ad2b-111">コンパイラは、const フィールドの値を直接コードを呼び出すに焼き付けます。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="1ad2b-112">そのため、const 値は、決して互換性の問題のリスクを負うことがなく変更できます。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="1ad2b-113">**✓ DO** のパブリック静的を使用して`readonly`フィールドの定義済みのオブジェクト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="1ad2b-114">型の定義済みのインスタンスがある場合により読み取り専用で、型自体の静的フィールドをパブリックとしてと宣言します。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="1ad2b-115">**X DO NOT** への変更可能な型のインスタンスを割り当てる`readonly`フィールドです。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="1ad2b-116">変更可能な型は、インスタンス化した後で変更することができますのインスタンスの型です。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="1ad2b-117">たとえば、配列、ほとんどのコレクション、およびストリームは変更可能な型が<xref:System.Int32?displayProperty=nameWithType>、 <xref:System.Uri?displayProperty=nameWithType>、および<xref:System.String?displayProperty=nameWithType>はすべて不変です。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="1ad2b-118">参照型のフィールドに対する読み取り専用修飾子には、置き換えられるのフィールドに格納されているインスタンスができなくなりますが、フィールドのインスタンスのデータのインスタンスを変更するメンバーを呼び出すことによって変更を妨げることはできません。</span><span class="sxs-lookup"><span data-stu-id="1ad2b-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="1ad2b-119">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="1ad2b-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1ad2b-120">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="1ad2b-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad2b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ad2b-121">See also</span></span>

- [<span data-ttu-id="1ad2b-122">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1ad2b-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="1ad2b-123">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1ad2b-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

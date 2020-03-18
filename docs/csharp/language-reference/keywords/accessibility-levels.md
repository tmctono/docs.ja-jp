---
title: アクセシビリティ レベル - C# リファレンス
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713825"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="a4bf6-102">アクセシビリティ レベル (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a4bf6-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="a4bf6-103">以下に示したのは、メンバーに適用されるアクセシビリティ レベルの宣言です。`public`、`protected`、`internal`、`private` の各アクセス修飾子を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="a4bf6-104">アクセシビリティの宣言</span><span class="sxs-lookup"><span data-stu-id="a4bf6-104">Declared accessibility</span></span>|<span data-ttu-id="a4bf6-105">意味</span><span class="sxs-lookup"><span data-stu-id="a4bf6-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="a4bf6-106">アクセスは無制限です。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="a4bf6-107">コンテナーであるクラスまたはそこから派生した型にアクセスが限定されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="a4bf6-108">アクセスは現在のアセンブリに限定されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="a4bf6-109">現在のアセンブリ、または包含クラスから派生した型にアクセスが限定されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="a4bf6-110">コンテナーである型にアクセスが限定されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="a4bf6-111">包含クラス、または包含クラスから派生した型にアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="a4bf6-112">C# 7.2 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="a4bf6-113">`protected internal` または `private protected` の組み合わせを使う場合を除き、1 つのメンバーまたは 1 つの型に指定できるアクセス修飾子は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="a4bf6-114">アクセス修飾子を名前空間に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="a4bf6-115">名前空間には、アクセス制限がありません。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="a4bf6-116">メンバーが宣言されているコンテキストによっては、決まったアクセシビリティしか宣言できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="a4bf6-117">メンバーの宣言にアクセス修飾子が指定されていない場合は、既定のアクセシビリティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="a4bf6-118">トップレベルの型 (他の型に対して入れ子にされていない型) に指定できるアクセシビリティは `internal` と `public` だけです。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="a4bf6-119">既定では、そのような型に `internal` のアクセシビリティが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="a4bf6-120">入れ子にされた型 (他の型のメンバーになっている型) には、次の表に示したアクセシビリティを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="a4bf6-121">コンテナー</span><span class="sxs-lookup"><span data-stu-id="a4bf6-121">Members of</span></span>|<span data-ttu-id="a4bf6-122">メンバーの既定のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="a4bf6-122">Default member accessibility</span></span>|<span data-ttu-id="a4bf6-123">メンバーに対して宣言できるアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="a4bf6-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="a4bf6-124">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf6-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="a4bf6-125">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf6-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="a4bf6-126">入れ子にされた型のアクセシビリティは、その型の[アクセシビリティ ドメイン](./accessibility-domain.md)によって決まります。このアクセシビリティ ドメインは、そのメンバーに対して宣言されているアクセシビリティと、そのメンバーの直接のコンテナーである型のアクセシビリティ ドメインの両方によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-126">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="a4bf6-127">ただし、入れ子にされた型のアクセシビリティ ドメインが、その型を含んでいる型のアクセシビリティ ドメインを上回ることはできません。</span><span class="sxs-lookup"><span data-stu-id="a4bf6-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a4bf6-128">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a4bf6-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4bf6-129">参照</span><span class="sxs-lookup"><span data-stu-id="a4bf6-129">See also</span></span>

- [<span data-ttu-id="a4bf6-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a4bf6-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a4bf6-131">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="a4bf6-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a4bf6-132">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="a4bf6-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a4bf6-133">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="a4bf6-133">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="a4bf6-134">アクセシビリティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="a4bf6-134">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="a4bf6-135">アクセシビリティ レベルの使用に関する制限事項</span><span class="sxs-lookup"><span data-stu-id="a4bf6-135">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="a4bf6-136">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="a4bf6-136">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a4bf6-137">public</span><span class="sxs-lookup"><span data-stu-id="a4bf6-137">public</span></span>](./public.md)
- [<span data-ttu-id="a4bf6-138">private</span><span class="sxs-lookup"><span data-stu-id="a4bf6-138">private</span></span>](./private.md)
- [<span data-ttu-id="a4bf6-139">protected</span><span class="sxs-lookup"><span data-stu-id="a4bf6-139">protected</span></span>](./protected.md)
- [<span data-ttu-id="a4bf6-140">internal</span><span class="sxs-lookup"><span data-stu-id="a4bf6-140">internal</span></span>](./internal.md)

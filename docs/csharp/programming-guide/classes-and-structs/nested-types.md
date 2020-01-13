---
title: 入れ子にされた型 - C# プログラミング ガイド
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705497"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="25eb1-102">入れ子にされた型 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="25eb1-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="25eb1-103">[クラス](../../language-reference/keywords/class.md)や[構造体](../../language-reference/keywords/struct.md)の中で定義された型は、入れ子にされた型と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-103">A type defined within a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="25eb1-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25eb1-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
<span data-ttu-id="25eb1-105">外側の型がクラスまたは構造体のいずれであっても、入れ子にされた型は既定で [private](../../language-reference/keywords/private.md) になります。これらにはその包含する型からのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="25eb1-106">前の例では、`Nested` クラスは外部の型にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="25eb1-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="25eb1-107">次のように、[アクセス修飾子](../../language-reference/keywords/access-modifiers.md)を指定して、入れ子にされた型のアクセシビリティを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="25eb1-108">**クラス**の入れ子にされた型は、[public](../../language-reference/keywords/public.md)、[protected](../../language-reference/keywords/protected.md)、[internal](../../language-reference/keywords/internal.md)、[protected internal](../../language-reference/keywords/protected-internal.md)、[private](../../language-reference/keywords/private.md)、[private protected](../../language-reference/keywords/private-protected.md) になります。</span><span class="sxs-lookup"><span data-stu-id="25eb1-108">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="25eb1-109">ただし、[シール クラス](../../language-reference/keywords/sealed.md)内で `protected`、`protected internal`、`private protected` の入れ子にされたクラスを定義すると、コンパイラの警告 [CS0628](../../misc/cs0628.md)、"新規のプロテクト メンバーがシール クラスで宣言されました" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="25eb1-110">**構造体**の入れ子にされた型は、は、[public](../../language-reference/keywords/public.md)、[internal](../../language-reference/keywords/internal.md)、または [private](../../language-reference/keywords/private.md) のいずれかが可能です。</span><span class="sxs-lookup"><span data-stu-id="25eb1-110">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="25eb1-111">次の例では、`Nested` クラスを public にします。</span><span class="sxs-lookup"><span data-stu-id="25eb1-111">The following example makes the `Nested` class public:</span></span>
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 <span data-ttu-id="25eb1-112">入れ子にされた型 (内側の型) は、包含する型 (外側の型) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="25eb1-113">包含する型にアクセスするには、その型を引数として入れ子にされた型のコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="25eb1-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="25eb1-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25eb1-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 <span data-ttu-id="25eb1-115">入れ子にされた型は、包含する型にアクセス可能なすべてのメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="25eb1-116">入れ子にされた型は、継承されたプロテクト メンバーを含む、包含する型のプライベート メンバーとプロテクト メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="25eb1-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="25eb1-117">上記の宣言では、クラス `Nested` の完全名は `Container.Nested` です。</span><span class="sxs-lookup"><span data-stu-id="25eb1-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="25eb1-118">これは、次のように入れ子になったクラスの新しいインスタンスを作成するときに使用される名前です。</span><span class="sxs-lookup"><span data-stu-id="25eb1-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a><span data-ttu-id="25eb1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="25eb1-119">See also</span></span>

- [<span data-ttu-id="25eb1-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="25eb1-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="25eb1-121">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="25eb1-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="25eb1-122">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="25eb1-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="25eb1-123">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="25eb1-123">Constructors</span></span>](./constructors.md)

---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: e13a773f0b585a5c8803a77c7aaad441d90dfe75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053952"
---
# <a name="key-visual-basic"></a><span data-ttu-id="9d846-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d846-102">Key (Visual Basic)</span></span>
<span data-ttu-id="9d846-103">`Key`キーワードでは、匿名型のプロパティの動作を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9d846-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="9d846-104">匿名型のインスタンス、またはハッシュ コード値の計算の間での等価テストでキー プロパティとしてを指定したプロパティのみです。</span><span class="sxs-lookup"><span data-stu-id="9d846-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="9d846-105">キー プロパティの値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="9d846-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="9d846-106">キー プロパティとして、キーワードを配置することで、匿名型のプロパティを指定する`Key`初期化リストでの宣言の前にします。</span><span class="sxs-lookup"><span data-stu-id="9d846-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="9d846-107">次の例では、`Airline`と`FlightNo`キーのプロパティが`Gate`はありません。</span><span class="sxs-lookup"><span data-stu-id="9d846-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="9d846-108">直接継承する新しい匿名型が作成されると、<xref:System.Object>します。</span><span class="sxs-lookup"><span data-stu-id="9d846-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="9d846-109">コンパイラは、次の 3 つの継承されたメンバーをオーバーライドします。 <xref:System.Object.Equals%2A>、 <xref:System.Object.GetHashCode%2A>、および<xref:System.Object.ToString%2A>します。</span><span class="sxs-lookup"><span data-stu-id="9d846-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="9d846-110">生成されたオーバーライド コードは、<xref:System.Object.Equals%2A>と<xref:System.Object.GetHashCode%2A>キー プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="9d846-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="9d846-111">種類でキー プロパティがない場合<xref:System.Object.GetHashCode%2A>と<xref:System.Object.Equals%2A>は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="9d846-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="9d846-112">等価比較</span><span class="sxs-lookup"><span data-stu-id="9d846-112">Equality</span></span>  
 <span data-ttu-id="9d846-113">匿名型の 2 つのインスタンスは、キー プロパティの値が等しい場合、同じ型のインスタンスと等しくなります。</span><span class="sxs-lookup"><span data-stu-id="9d846-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="9d846-114">次の例で`flight2`と等しい`flight1`から前の例では、同じ匿名のインスタンスであるための種類とそれらが一致する、キー プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="9d846-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="9d846-115">ただし、`flight3`が等しくない`flight1`別のキーのプロパティの値があるため、`FlightNo`します。</span><span class="sxs-lookup"><span data-stu-id="9d846-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="9d846-116">インスタンス`flight4`と同じ型でない`flight1`キー プロパティとしてさまざまなプロパティを指定するためです。</span><span class="sxs-lookup"><span data-stu-id="9d846-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="9d846-117">プロパティを持つのみ非キーと同じ名前、種類、順序、および値である 2 つのインスタンスが宣言されている場合は 2 つのインスタンスが等しくないです。</span><span class="sxs-lookup"><span data-stu-id="9d846-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="9d846-118">キー プロパティを持たないインスタンスはのみにします。</span><span class="sxs-lookup"><span data-stu-id="9d846-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="9d846-119">匿名型の 2 つのインスタンスを同じ匿名型のインスタンスである条件の詳細については、次を参照してください。[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d846-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="9d846-120">ハッシュ コードの計算</span><span class="sxs-lookup"><span data-stu-id="9d846-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="9d846-121">ような<xref:System.Object.Equals%2A>、ハッシュ関数で定義されている<xref:System.Object.GetHashCode%2A>匿名型が、型のキー プロパティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="9d846-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="9d846-122">次の例では、コードの値のキー プロパティとハッシュ間のやり取りを示します。</span><span class="sxs-lookup"><span data-stu-id="9d846-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="9d846-123">すべてのキー プロパティの同じ値を持つ匿名型のインスタンスでは、キー以外のプロパティは一致する値を持っていない場合でも、同じハッシュ コード値があります。</span><span class="sxs-lookup"><span data-stu-id="9d846-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="9d846-124">次のステートメントから`True`します。</span><span class="sxs-lookup"><span data-stu-id="9d846-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="9d846-125">1 つまたは複数のキー プロパティの異なる値を持つ匿名型のインスタンスでは、別のハッシュ コード値があります。</span><span class="sxs-lookup"><span data-stu-id="9d846-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="9d846-126">次のステートメントから`False`します。</span><span class="sxs-lookup"><span data-stu-id="9d846-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="9d846-127">キー プロパティとしてさまざまなプロパティを指定する匿名型のインスタンスは、同じ型のインスタンスではありません。</span><span class="sxs-lookup"><span data-stu-id="9d846-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="9d846-128">名前とすべてのプロパティの値が同じ場合でも他のハッシュ コード値があります。</span><span class="sxs-lookup"><span data-stu-id="9d846-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="9d846-129">次のステートメントから`False`します。</span><span class="sxs-lookup"><span data-stu-id="9d846-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="9d846-130">読み取り専用の値</span><span class="sxs-lookup"><span data-stu-id="9d846-130">Read-Only Values</span></span>  
 <span data-ttu-id="9d846-131">キー プロパティの値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="9d846-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="9d846-132">たとえば、`flight1`前の例で、`Airline`と`FlightNo`フィールドは読み取り専用が`Gate`変更できます。</span><span class="sxs-lookup"><span data-stu-id="9d846-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="9d846-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d846-133">See also</span></span>

- [<span data-ttu-id="9d846-134">匿名型の定義</span><span class="sxs-lookup"><span data-stu-id="9d846-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="9d846-135">方法: 匿名型の宣言におけるプロパティ名と型を推論します。</span><span class="sxs-lookup"><span data-stu-id="9d846-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="9d846-136">匿名型</span><span class="sxs-lookup"><span data-stu-id="9d846-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)

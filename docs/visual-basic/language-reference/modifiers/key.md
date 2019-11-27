---
title: Key
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92c8809779d6cab524f67ee47f355b72ab152403
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351518"
---
# <a name="key-visual-basic"></a><span data-ttu-id="83323-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83323-102">Key (Visual Basic)</span></span>
<span data-ttu-id="83323-103">`Key` キーワードを使用すると、匿名型のプロパティの動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="83323-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="83323-104">キープロパティとして指定したプロパティのみが、匿名型インスタンス間の等価性のテスト、またはハッシュコード値の計算に参加します。</span><span class="sxs-lookup"><span data-stu-id="83323-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="83323-105">キープロパティの値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="83323-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="83323-106">匿名型のプロパティをキープロパティとして指定するには、初期化リストの宣言の前にキーワード `Key` を配置します。</span><span class="sxs-lookup"><span data-stu-id="83323-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="83323-107">次の例では、`Airline` と `FlightNo` はキープロパティですが、`Gate` はありません。</span><span class="sxs-lookup"><span data-stu-id="83323-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="83323-108">新しい匿名型を作成すると、<xref:System.Object>から直接継承されます。</span><span class="sxs-lookup"><span data-stu-id="83323-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="83323-109">コンパイラは、継承された3つのメンバー (<xref:System.Object.Equals%2A>、<xref:System.Object.GetHashCode%2A>、および <xref:System.Object.ToString%2A>) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="83323-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="83323-110"><xref:System.Object.Equals%2A> と <xref:System.Object.GetHashCode%2A> に対して生成されるオーバーライドコードは、キープロパティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="83323-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="83323-111">型にキープロパティがない場合、<xref:System.Object.GetHashCode%2A> と <xref:System.Object.Equals%2A> はオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="83323-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="83323-112">等価比較</span><span class="sxs-lookup"><span data-stu-id="83323-112">Equality</span></span>  
 <span data-ttu-id="83323-113">2つの匿名型のインスタンスは、同じ型のインスタンスであり、キープロパティの値が等しい場合に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="83323-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="83323-114">次の例では、`flight2` は、同じ匿名型のインスタンスであり、キープロパティの値が一致しているため、前の例の `flight1` と同じです。</span><span class="sxs-lookup"><span data-stu-id="83323-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="83323-115">ただし、キープロパティの値が異なるため、`flight3` は `flight1` と同じではありません。 `FlightNo`。</span><span class="sxs-lookup"><span data-stu-id="83323-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="83323-116">インスタンス `flight4` が `flight1` と同じ型ではありません。キープロパティとして異なるプロパティが指定されているためです。</span><span class="sxs-lookup"><span data-stu-id="83323-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="83323-117">2つのインスタンスが、名前、型、順序、および値のキー以外のプロパティのみで宣言されている場合、2つのインスタンスが等しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="83323-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="83323-118">キープロパティのないインスタンスは、それ自体と同じです。</span><span class="sxs-lookup"><span data-stu-id="83323-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="83323-119">2つの匿名型インスタンスが同じ匿名型のインスタンスである場合の条件の詳細については、「[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83323-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="83323-120">ハッシュコードの計算</span><span class="sxs-lookup"><span data-stu-id="83323-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="83323-121"><xref:System.Object.Equals%2A>と同様に、匿名型の <xref:System.Object.GetHashCode%2A> で定義されているハッシュ関数は、型のキープロパティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="83323-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="83323-122">次の例は、キープロパティとハッシュコード値の間の相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="83323-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="83323-123">すべてのキープロパティに同じ値を持つ匿名型のインスタンスのハッシュコード値は、キー以外のプロパティに一致する値がない場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="83323-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="83323-124">次のステートメントは `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="83323-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="83323-125">1つまたは複数のキープロパティの値が異なる匿名型のインスタンスには、異なるハッシュコード値があります。</span><span class="sxs-lookup"><span data-stu-id="83323-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="83323-126">次のステートメントは `False`を返します。</span><span class="sxs-lookup"><span data-stu-id="83323-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="83323-127">キープロパティとして異なるプロパティを指定する匿名型のインスタンスは、同じ型のインスタンスではありません。</span><span class="sxs-lookup"><span data-stu-id="83323-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="83323-128">すべてのプロパティの名前と値が同じであっても、ハッシュコードの値は異なります。</span><span class="sxs-lookup"><span data-stu-id="83323-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="83323-129">次のステートメントは `False`を返します。</span><span class="sxs-lookup"><span data-stu-id="83323-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="83323-130">読み取り専用の値</span><span class="sxs-lookup"><span data-stu-id="83323-130">Read-Only Values</span></span>  
 <span data-ttu-id="83323-131">キープロパティの値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="83323-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="83323-132">たとえば、前の例の `flight1` では、`Airline` フィールドと `FlightNo` フィールドは読み取り専用ですが、`Gate` は変更できます。</span><span class="sxs-lookup"><span data-stu-id="83323-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="83323-133">参照</span><span class="sxs-lookup"><span data-stu-id="83323-133">See also</span></span>

- [<span data-ttu-id="83323-134">匿名型の定義</span><span class="sxs-lookup"><span data-stu-id="83323-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="83323-135">方法 : 匿名型の宣言におけるプロパティ名と型を推論する</span><span class="sxs-lookup"><span data-stu-id="83323-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="83323-136">匿名型</span><span class="sxs-lookup"><span data-stu-id="83323-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)

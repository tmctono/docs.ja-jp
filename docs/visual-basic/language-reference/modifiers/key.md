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
ms.openlocfilehash: 582ed5bb67b9c7504e736710aa4649cffb12ef45
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868003"
---
# <a name="key-visual-basic"></a><span data-ttu-id="b4266-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4266-102">Key (Visual Basic)</span></span>

<span data-ttu-id="b4266-103">`Key` キーワードを使用すると、匿名型のプロパティの動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4266-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="b4266-104">キー プロパティとして指定したプロパティのみが、匿名型インスタンス間の等価性のテスト、またはハッシュ コード値の計算に関与します。</span><span class="sxs-lookup"><span data-stu-id="b4266-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="b4266-105">キー プロパティの値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4266-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="b4266-106">匿名型のプロパティをキー プロパティとして指定するには、初期化リストでその宣言の前にキーワード `Key` を配置します。</span><span class="sxs-lookup"><span data-stu-id="b4266-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="b4266-107">次の例では、`Airline` と `FlightNo` はキー プロパティですが、`Gate` は違います。</span><span class="sxs-lookup"><span data-stu-id="b4266-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="b4266-108">新しい匿名型を作成すると、<xref:System.Object> から直接継承されます。</span><span class="sxs-lookup"><span data-stu-id="b4266-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="b4266-109">コンパイラによって、継承された 3 つのメンバー (<xref:System.Object.Equals%2A>、<xref:System.Object.GetHashCode%2A>、および <xref:System.Object.ToString%2A>) がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="b4266-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="b4266-110"><xref:System.Object.Equals%2A> と <xref:System.Object.GetHashCode%2A> に対して生成されるオーバーライド コードは、キー プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="b4266-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="b4266-111">型にキー プロパティがない場合、<xref:System.Object.GetHashCode%2A> と <xref:System.Object.Equals%2A> はオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="b4266-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="b4266-112">等価比較</span><span class="sxs-lookup"><span data-stu-id="b4266-112">Equality</span></span>  

 <span data-ttu-id="b4266-113">2 つの匿名型のインスタンスは、それらが同じ型のインスタンスであり、それらのキー プロパティの値が等しい場合に等しいとされます。</span><span class="sxs-lookup"><span data-stu-id="b4266-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="b4266-114">次の例で、`flight2` は、前の例の `flight1` と等しくなります。それらは同じ匿名型のインスタンスであり、それらのキー プロパティで一致する値を持つためです。</span><span class="sxs-lookup"><span data-stu-id="b4266-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="b4266-115">ただし、`flight3` は、キー プロパティ `FlightNo` の値が異なるため、`flight1` と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="b4266-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="b4266-116">インスタンス `flight4` は `flight1` と同じ型ではありません。それらはキー プロパティと異なるプロパティを指定しているためです。</span><span class="sxs-lookup"><span data-stu-id="b4266-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="b4266-117">2 つのインスタンスが、名前、型、順序、および値が同じで、非キー プロパティのみで宣言されている場合、2 つのインスタンスは等しくありません。</span><span class="sxs-lookup"><span data-stu-id="b4266-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="b4266-118">キー プロパティを持たないインスタンスは、それ自体とのみ等しくなります。</span><span class="sxs-lookup"><span data-stu-id="b4266-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="b4266-119">2 つの匿名型インスタンスが同じ匿名型のインスタンスである条件の詳細については、「[匿名型](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4266-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="b4266-120">ハッシュ コード計算</span><span class="sxs-lookup"><span data-stu-id="b4266-120">Hash Code Calculation</span></span>  

 <span data-ttu-id="b4266-121"><xref:System.Object.Equals%2A> と同様に、匿名型の <xref:System.Object.GetHashCode%2A> に定義されているハッシュ関数は、型のキー プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="b4266-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="b4266-122">次の例に、キー プロパティとハッシュ コード値の間の相互作用を示します。</span><span class="sxs-lookup"><span data-stu-id="b4266-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="b4266-123">すべてのキー プロパティに同じ値を持つ匿名型のインスタンスは、同じハッシュ コード値を持ちます。非キー プロパティに一致する値がない場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="b4266-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="b4266-124">次のステートメントでは、`True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="b4266-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="b4266-125">1 つ以上のキー プロパティで異なる値を持つ匿名型のインスタンスは、異なるハッシュ コード値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b4266-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="b4266-126">次のステートメントでは、`False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="b4266-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="b4266-127">キー プロパティと異なるプロパティを指定する匿名型のインスタンスは、同じ型のインスタンスではありません。</span><span class="sxs-lookup"><span data-stu-id="b4266-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="b4266-128">それらは、すべてのプロパティの名前と値が同じであっても、異なるハッシュ コード値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b4266-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="b4266-129">次のステートメントでは、`False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="b4266-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="b4266-130">読み取り専用の値</span><span class="sxs-lookup"><span data-stu-id="b4266-130">Read-Only Values</span></span>  

 <span data-ttu-id="b4266-131">キー プロパティの値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4266-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="b4266-132">たとえば、前の例の `flight1` では、`Airline` フィールドと `FlightNo` フィールドは読み取り専用ですが、`Gate` は変更できます。</span><span class="sxs-lookup"><span data-stu-id="b4266-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b4266-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4266-133">See also</span></span>

- [<span data-ttu-id="b4266-134">匿名型の定義</span><span class="sxs-lookup"><span data-stu-id="b4266-134">Anonymous Type Definition</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="b4266-135">方法: 匿名型の宣言におけるプロパティ名と型を推論する</span><span class="sxs-lookup"><span data-stu-id="b4266-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="b4266-136">匿名型</span><span class="sxs-lookup"><span data-stu-id="b4266-136">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)

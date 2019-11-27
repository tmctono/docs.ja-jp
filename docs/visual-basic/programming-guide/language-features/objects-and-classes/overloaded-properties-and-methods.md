---
title: オーバーロードされたプロパティとメソッド
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346089"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="ff967-102">オーバーロードされたプロパティとメソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff967-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="ff967-103">オーバーロードとは、同じ名前で引数の型が異なるクラスで、複数のプロシージャ、インスタンスコンストラクター、またはプロパティを作成することです。</span><span class="sxs-lookup"><span data-stu-id="ff967-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="ff967-104">オーバーロードの使用</span><span class="sxs-lookup"><span data-stu-id="ff967-104">Overloading usage</span></span>

<span data-ttu-id="ff967-105">オーバーロードは、さまざまなデータ型を操作するプロシージャに対して、オブジェクトモデルで同じ名前を使用することが指示された場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="ff967-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="ff967-106">たとえば、いくつかの異なるデータ型を表示できるクラスでは、次のような `Display` のプロシージャが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff967-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="ff967-107">オーバーロードを使用しない場合は、次に示すように、プロシージャごとに個別の名前を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff967-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="ff967-108">オーバーロードを使用すると、使用可能なデータ型を選択できるため、プロパティやメソッドの使用が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ff967-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="ff967-109">たとえば、前に説明したオーバーロードされた `Display` メソッドは、次のいずれかのコード行を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ff967-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="ff967-110">実行時に、Visual Basic は、指定したパラメーターのデータ型に基づいて正しいプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ff967-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="ff967-111">オーバーロード (規則を)</span><span class="sxs-lookup"><span data-stu-id="ff967-111">Overloading rules</span></span>

 <span data-ttu-id="ff967-112">クラスのオーバーロードされたメンバーを作成するには、同じ名前を持つ2つ以上のプロパティまたはメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ff967-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="ff967-113">オーバーロードされた派生メンバーを除き、オーバーロードされた各メンバーは異なるパラメーターリストを持つ必要があります。また、プロパティまたはプロシージャをオーバーロードするときに、次の項目を区別機能として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff967-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="ff967-114">メンバーまたはメンバーのパラメーターに適用される、`ByVal` や `ByRef`などの修飾子。</span><span class="sxs-lookup"><span data-stu-id="ff967-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="ff967-115">パラメーターの名前</span><span class="sxs-lookup"><span data-stu-id="ff967-115">Names of parameters</span></span>

- <span data-ttu-id="ff967-116">プロシージャの戻り値の型</span><span class="sxs-lookup"><span data-stu-id="ff967-116">Return types of procedures</span></span>

<span data-ttu-id="ff967-117">`Overloads` キーワードはオーバーロード時には省略可能ですが、オーバーロードされたメンバーが `Overloads` キーワードを使用している場合は、同じ名前の他のすべてのオーバーロードされたメンバーもこのキーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff967-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="ff967-118">派生クラスでは、同じパラメーターとパラメーターの型を持つメンバーを持つ継承されたメンバーをオーバーロードできます。これは、*名前とシグネチャによるシャドウ*処理と呼ばれるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="ff967-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="ff967-119">名前とシグネチャでシャドウするときに `Overloads` キーワードを使用すると、基底クラスの実装ではなく、派生クラスのメンバーの実装が使用され、そのメンバーの他のすべてのオーバーロードが派生クラスのインスタンスで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ff967-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="ff967-120">同じパラメーターとパラメーターの型を持つメンバーを持つ継承されたメンバーをオーバーロードするときに `Overloads` キーワードを省略すると、オーバーロードは*名前によるシャドウ*処理と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ff967-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="ff967-121">名前によるシャドウ処理により、メンバーの継承された実装が置き換えられます。これにより、派生クラスのインスタンスとその他のすべてのオーバーロードが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ff967-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="ff967-122">`Overloads` と `Shadows` の修飾子を同じプロパティまたはメソッドと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff967-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="ff967-123">例</span><span class="sxs-lookup"><span data-stu-id="ff967-123">Example</span></span>

<span data-ttu-id="ff967-124">次の例では、金額の `String` または `Decimal` 表現を受け入れるオーバーロードされたメソッドを作成し、売上税を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="ff967-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="ff967-125">この例を使用して、オーバーロードされたメソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="ff967-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="ff967-126">新しいプロジェクトを開き、`TaxClass`という名前のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="ff967-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="ff967-127">`TaxClass` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ff967-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="ff967-128">次のプロシージャをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="ff967-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="ff967-129">フォームにボタンを追加し、ボタンの `Button1_Click` イベントから `ShowTax` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ff967-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="ff967-130">プロジェクトを実行し、フォームのボタンをクリックして、オーバーロードされた `ShowTax` プロシージャをテストします。</span><span class="sxs-lookup"><span data-stu-id="ff967-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="ff967-131">実行時に、コンパイラは、使用されているパラメーターに一致するオーバーロードされた適切な関数を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff967-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="ff967-132">このボタンをクリックすると、オーバーロードされたメソッドが最初に呼び出されます。このメソッドは、文字列である `Price` パラメーターと "Price は文字列です。</span><span class="sxs-lookup"><span data-stu-id="ff967-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="ff967-133">税 $5.12 "が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff967-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="ff967-134">2回目の `Decimal` 値を使用して `TaxAmount` が呼び出されます。 "Price は Decimal です。</span><span class="sxs-lookup"><span data-stu-id="ff967-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="ff967-135">税 $5.12 "が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff967-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff967-136">参照</span><span class="sxs-lookup"><span data-stu-id="ff967-136">See also</span></span>

- [<span data-ttu-id="ff967-137">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ff967-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="ff967-138">Visual Basic でのシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="ff967-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="ff967-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="ff967-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ff967-140">継承の基本</span><span class="sxs-lookup"><span data-stu-id="ff967-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="ff967-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="ff967-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ff967-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="ff967-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="ff967-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="ff967-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="ff967-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="ff967-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="ff967-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="ff967-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)

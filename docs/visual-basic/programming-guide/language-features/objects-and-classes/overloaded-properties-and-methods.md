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
ms.openlocfilehash: 1672f12773ece012c580253b6dafbf9d0ac8f07c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389153"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="06363-102">オーバーロードされたプロパティとメソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06363-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="06363-103">オーバーロードとは、名前が同じで引数の型が異なる複数のプロシージャ、インスタンスのコンストラクター、またはプロパティをクラスに作成することです。</span><span class="sxs-lookup"><span data-stu-id="06363-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="06363-104">オーバーロードの使用法</span><span class="sxs-lookup"><span data-stu-id="06363-104">Overloading usage</span></span>

<span data-ttu-id="06363-105">オーバーロードは、さまざまなデータ型を操作するプロシージャに同じ名前を使用するようにオブジェクト モデルで指示された場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="06363-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="06363-106">たとえば、各種のデータ型を表示できるクラスには、次のような `Display` プロシージャがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="06363-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="06363-107">オーバーロードを使用しない場合は、実行する処理は同じでも、次に示すようにプロシージャごとに個別の名前を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06363-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="06363-108">オーバーロードを使用すると、使用可能なデータ型を選択できるため、プロパティやメソッドを簡単に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="06363-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="06363-109">たとえば、前に説明したオーバーロードされた `Display` メソッドは、次のいずれかのコード行を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="06363-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="06363-110">実行時に、Visual Basic は、指定されたパラメーターのデータ型に基づいて正しいプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="06363-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="06363-111">オーバーロードのルール</span><span class="sxs-lookup"><span data-stu-id="06363-111">Overloading rules</span></span>

 <span data-ttu-id="06363-112">オーバーロードされたメンバーをクラスに作成するには、同じ名前を持つ 2 つ以上のプロパティまたはメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="06363-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="06363-113">オーバーロードされた派生メンバーを除き、オーバーロードされた各メンバーは異なるパラメーター リストを持つ必要があります。また、プロパティまたはプロシージャをオーバーロードするときに、区別するための特性として次の項目を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="06363-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="06363-114">メンバーまたはメンバーのパラメーターに適用される、`ByVal` や `ByRef` などの修飾子。</span><span class="sxs-lookup"><span data-stu-id="06363-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="06363-115">パラメーターの名前</span><span class="sxs-lookup"><span data-stu-id="06363-115">Names of parameters</span></span>

- <span data-ttu-id="06363-116">プロシージャの戻り値の型</span><span class="sxs-lookup"><span data-stu-id="06363-116">Return types of procedures</span></span>

<span data-ttu-id="06363-117">`Overloads` キーワードはオーバーロード時には省略可能ですが、オーバーロードされたメンバーが `Overloads` キーワードを使用している場合は、同じ名前の他のすべてのオーバーロードされたメンバーにもこのキーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06363-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="06363-118">派生クラスでは、継承されたメンバーを同じパラメーターとパラメーターの型を持つメンバーでオーバーロードすることができます。これは、*名前とシグネチャによるシャドウ*と呼ばれる処理です。</span><span class="sxs-lookup"><span data-stu-id="06363-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="06363-119">名前とシグネチャによるシャドウを行うときに `Overloads` キーワードを使用すると、基底クラスの実装ではなく、派生クラスのメンバーの実装が使用され、そのメンバーの他のすべてのオーバーロードが派生クラスのインスタンスで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="06363-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="06363-120">同じパラメーターとパラメーターの型を持つメンバーで継承されたメンバーをオーバーロードするときに `Overloads` キーワードを省略した場合、そのオーバーロードは*名前によるシャドウ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="06363-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="06363-121">名前によるシャドウでは、メンバーの継承された実装が置き換えられます。これにより、派生クラスとその子孫のインスタンスで他のすべてのオーバーロードが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="06363-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="06363-122">`Overloads` と `Shadows` の両方の修飾子を同じプロパティまたはメソッドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="06363-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="06363-123">例</span><span class="sxs-lookup"><span data-stu-id="06363-123">Example</span></span>

<span data-ttu-id="06363-124">次の例では、`String` または `Decimal` で表現されたドル額を受け取り、売上税を含む文字列を返すオーバーロードされたメソッドを作成しています。</span><span class="sxs-lookup"><span data-stu-id="06363-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="06363-125">この例を使用して、オーバーロードされたメソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="06363-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="06363-126">新しいプロジェクトを開いて、`TaxClass` という名前のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="06363-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="06363-127">`TaxClass` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="06363-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="06363-128">次のプロシージャをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="06363-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="06363-129">フォームにボタンを追加し、ボタンの `Button1_Click` イベントから `ShowTax` プロシージャが呼び出されるようにします。</span><span class="sxs-lookup"><span data-stu-id="06363-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="06363-130">プロジェクトを実行し、フォームのボタンをクリックして、オーバーロードされた `ShowTax` プロシージャをテストします。</span><span class="sxs-lookup"><span data-stu-id="06363-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="06363-131">実行時に、コンパイラは、使用されているパラメーターに一致するオーバーロードされた適切な関数を選択します。</span><span class="sxs-lookup"><span data-stu-id="06363-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="06363-132">このボタンをクリックすると、最初に、文字列である `Price` パラメーターを使用して、オーバーロードされたメソッドが呼び出され、"Price is a String.</span><span class="sxs-lookup"><span data-stu-id="06363-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="06363-133">Tax is $5.12" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06363-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="06363-134">2 回目は、`Decimal` 値を使用して `TaxAmount` が呼び出され、"Price is a Decimal.</span><span class="sxs-lookup"><span data-stu-id="06363-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="06363-135">Tax is $5.12" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06363-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="06363-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="06363-136">See also</span></span>

- [<span data-ttu-id="06363-137">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="06363-137">Objects and Classes</span></span>](index.md)
- [<span data-ttu-id="06363-138">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="06363-138">Shadowing in Visual Basic</span></span>](../declared-elements/shadowing.md)
- [<span data-ttu-id="06363-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="06363-139">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="06363-140">継承の基本</span><span class="sxs-lookup"><span data-stu-id="06363-140">Inheritance Basics</span></span>](inheritance-basics.md)
- [<span data-ttu-id="06363-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="06363-141">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="06363-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="06363-142">ByVal</span></span>](../../../language-reference/modifiers/byval.md)
- [<span data-ttu-id="06363-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="06363-143">ByRef</span></span>](../../../language-reference/modifiers/byref.md)
- [<span data-ttu-id="06363-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="06363-144">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="06363-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="06363-145">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)

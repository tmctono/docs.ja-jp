---
title: オーバー ロードされたプロパティとメソッド (Visual Basic)
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
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864872"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="26086-102">オーバー ロードされたプロパティとメソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26086-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="26086-103">オーバー ロードは、1 つ以上のプロシージャ、インスタンス コンス トラクターで異なる引数の型が同じ名前のクラスのプロパティの作成です。</span><span class="sxs-lookup"><span data-stu-id="26086-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="26086-104">使用率をオーバー ロード</span><span class="sxs-lookup"><span data-stu-id="26086-104">Overloading usage</span></span>

<span data-ttu-id="26086-105">オーバー ロードは、オブジェクト モデルで、別のデータ型を操作する手順については、同じ名前を使用しているときに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="26086-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="26086-106">たとえば、いくつかの異なるデータ型を表示できるクラスがある`Display`手順のようになります。</span><span class="sxs-lookup"><span data-stu-id="26086-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="26086-107">オーバー ロードが可能でない場合でも、次に示すように、同じよう各手順では、個別の名前を作成する必要は。</span><span class="sxs-lookup"><span data-stu-id="26086-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="26086-108">オーバー ロードすると、使用できるデータ型の選択肢を提供するために、プロパティまたはメソッドを使用しやすきます。</span><span class="sxs-lookup"><span data-stu-id="26086-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="26086-109">たとえば、オーバー ロード`Display`説明以前メソッドでは、次のコード行のいずれか。</span><span class="sxs-lookup"><span data-stu-id="26086-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="26086-110">実行時に、Visual Basic は、指定したパラメーターのデータ型に基づいて適切なプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="26086-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="26086-111">オーバー ロードの規則</span><span class="sxs-lookup"><span data-stu-id="26086-111">Overloading rules</span></span>

 <span data-ttu-id="26086-112">クラスのオーバー ロードされたメンバーを作成するには、2 つ以上のプロパティまたは同じ名前のメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="26086-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="26086-113">派生オーバー ロードされたメンバーを除く各オーバー ロードされたメンバーはパラメーター リストが異なっている必要があり、次の項目は、プロパティまたはプロシージャをオーバー ロードとの差別化機能として使用できません。</span><span class="sxs-lookup"><span data-stu-id="26086-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="26086-114">修飾子など`ByVal`または`ByRef`メンバー、またはメンバーのパラメーターに適用されています。</span><span class="sxs-lookup"><span data-stu-id="26086-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="26086-115">パラメーターの名前</span><span class="sxs-lookup"><span data-stu-id="26086-115">Names of parameters</span></span>

- <span data-ttu-id="26086-116">プロシージャの戻り値の型</span><span class="sxs-lookup"><span data-stu-id="26086-116">Return types of procedures</span></span>

<span data-ttu-id="26086-117">`Overloads`オーバー ロード、ときに、キーワードは省略可能ですが、メンバーを使用していずれかのオーバー ロードされた場合、`Overloads`このキーワードはキーワード、その他のすべてのオーバー ロードされたメンバーと同じ名前で指定もする必要があります。</span><span class="sxs-lookup"><span data-stu-id="26086-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="26086-118">派生クラスで継承されたメンバーを同じパラメーターおよびパラメーターの型と呼ばれるプロセスを持つメンバーをオーバー ロードできます*名前とシグネチャによるシャドウ*します。</span><span class="sxs-lookup"><span data-stu-id="26086-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="26086-119">場合、`Overloads`キーワードを使用して名前とシグネチャによるシャドウ、メンバーの派生クラスの実装が、基底クラスの実装ではなく使用され、そのメンバーの他のすべてのオーバー ロードのインスタンスで使用できるときに、派生クラスです。</span><span class="sxs-lookup"><span data-stu-id="26086-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="26086-120">場合、`Overloads`と同じパラメーターおよびパラメーターの型を持つメンバーを持つ継承されたメンバーをオーバー ロード時にキーワードを省略すると、オーバー ロードが呼び出されます*名前によるシャドウ*します。</span><span class="sxs-lookup"><span data-stu-id="26086-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="26086-121">継承されたメンバーの実装を置き換える名前によるシャドウおり、その他のすべてのオーバー ロードに置き換わります、派生クラスのインスタンスを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="26086-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="26086-122">`Overloads`と`Shadows`修飾子両方では使用できません、同じプロパティまたはメソッドです。</span><span class="sxs-lookup"><span data-stu-id="26086-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="26086-123">例</span><span class="sxs-lookup"><span data-stu-id="26086-123">Example</span></span>

<span data-ttu-id="26086-124">次の例は、いずれかを受け取るオーバー ロードされたメソッドを作成、`String`または`Decimal`形式の金額と販売税を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="26086-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="26086-125">この例を使用して、オーバー ロードされたメソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="26086-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="26086-126">新しいプロジェクトを開き、という名前のクラスを追加`TaxClass`します。</span><span class="sxs-lookup"><span data-stu-id="26086-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="26086-127">`TaxClass` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="26086-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="26086-128">フォームに次の手順を追加します。</span><span class="sxs-lookup"><span data-stu-id="26086-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="26086-129">呼び出し、フォームにボタンを追加、`ShowTax`プロシージャから、`Button1_Click`ボタンのイベント。</span><span class="sxs-lookup"><span data-stu-id="26086-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="26086-130">プロジェクトを実行し、テスト、オーバー ロードされたフォーム上のボタンをクリックします。`ShowTax`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="26086-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="26086-131">実行時に、コンパイラは、使用されているパラメーターに一致する適切なオーバー ロードされた関数を選択します。</span><span class="sxs-lookup"><span data-stu-id="26086-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="26086-132">ボタンをクリックすると、オーバー ロードされたメソッドが呼び出された最初、`Price`パラメーターが文字列と、メッセージは、"価格は文字列です。</span><span class="sxs-lookup"><span data-stu-id="26086-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="26086-133">税金が $$5.12"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26086-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="26086-134">`TaxAmount` 呼び出すと、`Decimal`値を 2 回目と、メッセージ、"価格は 10 進数です。</span><span class="sxs-lookup"><span data-stu-id="26086-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="26086-135">税金が $$5.12"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26086-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="26086-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="26086-136">See also</span></span>

- [<span data-ttu-id="26086-137">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="26086-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="26086-138">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="26086-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="26086-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="26086-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="26086-140">継承の基本</span><span class="sxs-lookup"><span data-stu-id="26086-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="26086-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="26086-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="26086-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="26086-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="26086-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="26086-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="26086-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="26086-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="26086-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="26086-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)

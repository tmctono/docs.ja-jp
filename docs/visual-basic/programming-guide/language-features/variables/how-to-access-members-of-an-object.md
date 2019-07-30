---
title: '方法: オブジェクトのメンバーにアクセスする (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 882046b829ade2da7c10b3db4c0d6c9ca9f3d579
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630835"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="835bc-102">方法: オブジェクトのメンバーにアクセスする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="835bc-102">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="835bc-103">オブジェクトを参照するオブジェクト変数がある場合は、そのオブジェクトのメソッド、プロパティ、フィールド、イベントなどのメンバーを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="835bc-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="835bc-104">たとえば、新しい<xref:System.Windows.Forms.Form>オブジェクトを作成した後で、その<xref:System.Windows.Forms.Control.Text%2A>オブジェクトのプロパティを設定したり、 <xref:System.Windows.Forms.Control.Focus%2A>メソッドを呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="835bc-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="835bc-105">メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="835bc-105">Accessing Members</span></span>

<span data-ttu-id="835bc-106">オブジェクトのメンバーにアクセスするには、それを参照する変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="835bc-106">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="835bc-107">オブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="835bc-107">To access members of an object</span></span>

- <span data-ttu-id="835bc-108">オブジェクト変数名とメンバー名の`.`間には、メンバーアクセス演算子 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="835bc-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="835bc-109">メンバーが[共有](../../../../visual-basic/language-reference/modifiers/shared.md)されている場合は、そのメンバーにアクセスするための変数は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="835bc-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="835bc-110">既知の型のオブジェクトのメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="835bc-110">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="835bc-111">コンパイル時にオブジェクトの型がわかっている場合は、それを参照する変数に*事前バインディング*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="835bc-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="835bc-112">コンパイル時に型がわかっているオブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="835bc-112">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="835bc-113">変数に割り当てるオブジェクトの型として、オブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="835bc-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="835bc-114">で`Option Strict On`は、オブジェクト (また<xref:System.Windows.Forms.Form>はから<xref:System.Windows.Forms.Form>派生した型のオブジェクト) のみを`extraForm`に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="835bc-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="835bc-115">へ`CType` `extraForm`の拡大変換でクラスまたは構造体を定義している場合は、そのクラスまたは構造体をに割り当てることもできます。 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="835bc-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="835bc-116">オブジェクト変数名とメンバー名の`.`間には、メンバーアクセス演算子 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="835bc-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="835bc-117">設定`Option Strict`がどのようなものであっても、 <xref:System.Windows.Forms.Form>クラスに固有のすべてのメソッドとプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835bc-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="835bc-118">不明な型のオブジェクトのメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="835bc-118">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="835bc-119">コンパイル時にオブジェクトの型がわからない場合は、そのオブジェクトを参照する任意の変数に対して*遅延バインディング*を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="835bc-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="835bc-120">コンパイル時に型がわからないオブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="835bc-120">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="835bc-121">オブジェクトの[データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)であるオブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="835bc-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="835bc-122">(変数をと`Object`して宣言することは、と<xref:System.Object?displayProperty=nameWithType>して宣言するのと同じです)。</span><span class="sxs-lookup"><span data-stu-id="835bc-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="835bc-123">で`Option Strict On`は、 <xref:System.Object>クラスで定義されているメンバーのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835bc-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="835bc-124">オブジェクト変数名とメンバー名の`.`間には、メンバーアクセス演算子 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="835bc-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="835bc-125">オブジェクト変数に割り当てるオブジェクトのメンバーにアクセスできるようにするには、を設定`Option Strict Off`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="835bc-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="835bc-126">この場合、コンパイラは、変数に割り当てたオブジェクトによって、特定のメンバーが公開されることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="835bc-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="835bc-127">アクセスしようとしたメンバーがオブジェクトによって公開され<xref:System.MemberAccessException>ていない場合は、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="835bc-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="835bc-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="835bc-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="835bc-129">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="835bc-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="835bc-130">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="835bc-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="835bc-131">Object 型</span><span class="sxs-lookup"><span data-stu-id="835bc-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="835bc-132">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="835bc-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

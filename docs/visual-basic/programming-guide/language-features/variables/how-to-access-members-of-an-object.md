---
title: '方法 : オブジェクトのメンバーにアクセスする'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: d44b538e8413eb1412e937375e9bca77600a29b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348666"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="5c08c-102">方法: オブジェクトのメンバーにアクセスする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c08c-102">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="5c08c-103">オブジェクトを参照するオブジェクト変数がある場合は、そのオブジェクトのメソッド、プロパティ、フィールド、イベントなどのメンバーを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="5c08c-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="5c08c-104">たとえば、新しい <xref:System.Windows.Forms.Form> オブジェクトを作成したら、そのオブジェクトの <xref:System.Windows.Forms.Control.Text%2A> プロパティを設定するか、その <xref:System.Windows.Forms.Control.Focus%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="5c08c-105">メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5c08c-105">Accessing Members</span></span>

<span data-ttu-id="5c08c-106">オブジェクトのメンバーにアクセスするには、それを参照する変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-106">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="5c08c-107">オブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="5c08c-107">To access members of an object</span></span>

- <span data-ttu-id="5c08c-108">オブジェクト変数名とメンバー名の間には、メンバーアクセス演算子 (`.`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="5c08c-109">メンバーが[共有](../../../../visual-basic/language-reference/modifiers/shared.md)されている場合は、そのメンバーにアクセスするための変数は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5c08c-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="5c08c-110">既知の型のオブジェクトのメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5c08c-110">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="5c08c-111">コンパイル時にオブジェクトの型がわかっている場合は、それを参照する変数に*事前バインディング*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="5c08c-112">コンパイル時に型がわかっているオブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="5c08c-112">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="5c08c-113">変数に割り当てるオブジェクトの型として、オブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="5c08c-114">`Option Strict On`では、<xref:System.Windows.Forms.Form> オブジェクト (または <xref:System.Windows.Forms.Form>から派生した型のオブジェクト) のみを `extraForm`に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="5c08c-115"><xref:System.Windows.Forms.Form>への拡大 `CType` 変換を使用してクラスまたは構造体を定義した場合は、そのクラスまたは構造体を `extraForm`に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="5c08c-116">オブジェクト変数名とメンバー名の間には、メンバーアクセス演算子 (`.`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="5c08c-117">`Option Strict` の設定に関係なく、<xref:System.Windows.Forms.Form> クラスに固有のすべてのメソッドとプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="5c08c-118">不明な型のオブジェクトのメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5c08c-118">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="5c08c-119">コンパイル時にオブジェクトの型がわからない場合は、そのオブジェクトを参照する任意の変数に対して*遅延バインディング*を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c08c-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="5c08c-120">コンパイル時に型がわからないオブジェクトのメンバーにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="5c08c-120">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="5c08c-121">[Object データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)であるオブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="5c08c-122">(変数を `Object` として宣言することは <xref:System.Object?displayProperty=nameWithType>として宣言することと同じです)。</span><span class="sxs-lookup"><span data-stu-id="5c08c-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="5c08c-123">`Option Strict On`では、<xref:System.Object> クラスで定義されているメンバーのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c08c-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="5c08c-124">オブジェクト変数名とメンバー名の間には、メンバーアクセス演算子 (`.`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="5c08c-125">オブジェクト変数に割り当てるオブジェクトのメンバーにアクセスできるようにするには、`Option Strict Off`を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c08c-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="5c08c-126">この場合、コンパイラは、変数に割り当てたオブジェクトによって、特定のメンバーが公開されることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="5c08c-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="5c08c-127">アクセスしようとしたメンバーがオブジェクトによって公開されていない場合、<xref:System.MemberAccessException> 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="5c08c-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c08c-128">参照</span><span class="sxs-lookup"><span data-stu-id="5c08c-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="5c08c-129">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="5c08c-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="5c08c-130">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="5c08c-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="5c08c-131">Object データ型</span><span class="sxs-lookup"><span data-stu-id="5c08c-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="5c08c-132">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="5c08c-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

---
title: MustInherit
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351496"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="01b33-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01b33-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="01b33-103">クラスを基底クラスとしてのみ使用でき、そこからオブジェクトを直接作成することはできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="01b33-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01b33-104">コメント</span><span class="sxs-lookup"><span data-stu-id="01b33-104">Remarks</span></span>  
 <span data-ttu-id="01b33-105">*基底クラス*(*抽象クラス*とも呼ばれます) の目的は、このクラスから派生したすべてのクラスに共通の機能を定義することです。</span><span class="sxs-lookup"><span data-stu-id="01b33-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="01b33-106">これにより、派生クラスで共通の要素を再定義する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="01b33-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="01b33-107">場合によっては、この共通機能は使用可能なオブジェクトを作成するのに十分ではないため、各派生クラスは不足している機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="01b33-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="01b33-108">このような場合は、コンシューマー側のコードで派生クラスからのみオブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b33-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="01b33-109">これを適用するには、基本クラスで `MustInherit` を使用します。</span><span class="sxs-lookup"><span data-stu-id="01b33-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="01b33-110">`MustInherit` クラスのもう1つの用途は、変数を関連クラスのセットに制限することです。</span><span class="sxs-lookup"><span data-stu-id="01b33-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="01b33-111">基本クラスを定義し、そこからすべての関連クラスを派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="01b33-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="01b33-112">基底クラスは、すべての派生クラスに共通する機能を提供する必要はありませんが、変数に値を代入するためのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b33-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="01b33-113">コンシューマーコードが基底クラスとして変数を宣言している場合、Visual Basic によって、派生クラスのいずれかからその変数にオブジェクトのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01b33-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="01b33-114">.NET Framework は、<xref:System.Array>、<xref:System.Enum>、<xref:System.ValueType>の複数の `MustInherit` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="01b33-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="01b33-115"><xref:System.ValueType> は、変数を制限する基底クラスの例です。</span><span class="sxs-lookup"><span data-stu-id="01b33-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="01b33-116">すべての値型は <xref:System.ValueType>から派生します。</span><span class="sxs-lookup"><span data-stu-id="01b33-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="01b33-117">変数を <xref:System.ValueType>として宣言する場合は、その変数に値型のみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01b33-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="01b33-118">ルール</span><span class="sxs-lookup"><span data-stu-id="01b33-118">Rules</span></span>  
  
- <span data-ttu-id="01b33-119">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="01b33-119">**Declaration Context.**</span></span> <span data-ttu-id="01b33-120">`MustInherit` は、`Class` ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b33-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="01b33-121">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="01b33-121">**Combined Modifiers.**</span></span> <span data-ttu-id="01b33-122">同じ宣言内の `NotInheritable` と共に `MustInherit` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="01b33-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b33-123">例</span><span class="sxs-lookup"><span data-stu-id="01b33-123">Example</span></span>  
 <span data-ttu-id="01b33-124">強制継承と強制オーバーライドの両方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="01b33-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="01b33-125">基本クラス `shape` は `acrossLine`変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="01b33-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="01b33-126">クラス `circle` および `square` は `shape`から派生します。</span><span class="sxs-lookup"><span data-stu-id="01b33-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="01b33-127">`acrossLine`の定義を継承しますが、その計算は図形の種類によって異なるため、関数 `area` を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b33-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="01b33-128">`shape1` を宣言して `shape`型で `shape2` することができます。</span><span class="sxs-lookup"><span data-stu-id="01b33-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="01b33-129">ただし、`shape` からオブジェクトを作成することはできません。これは、関数 `area` の機能がなく、`MustInherit`としてマークされているためです。</span><span class="sxs-lookup"><span data-stu-id="01b33-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="01b33-130">これらは `shape`として宣言されているため、`shape1` と `shape2` の変数は、派生クラス `circle` および `square`のオブジェクトに限定されます。</span><span class="sxs-lookup"><span data-stu-id="01b33-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="01b33-131">Visual Basic では、これらの変数に他のオブジェクトを割り当てることはできません。これにより、高いレベルのタイプセーフが得られます。</span><span class="sxs-lookup"><span data-stu-id="01b33-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="01b33-132">使用法</span><span class="sxs-lookup"><span data-stu-id="01b33-132">Usage</span></span>  
 <span data-ttu-id="01b33-133">このコンテキストでは、`MustInherit` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b33-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="01b33-134">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="01b33-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="01b33-135">参照</span><span class="sxs-lookup"><span data-stu-id="01b33-135">See also</span></span>

- [<span data-ttu-id="01b33-136">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="01b33-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="01b33-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="01b33-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="01b33-138">キーワード</span><span class="sxs-lookup"><span data-stu-id="01b33-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="01b33-139">継承の基本</span><span class="sxs-lookup"><span data-stu-id="01b33-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

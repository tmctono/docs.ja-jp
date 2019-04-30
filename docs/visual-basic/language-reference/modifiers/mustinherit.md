---
title: MustInherit (Visual Basic)
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
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053939"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="ee94f-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee94f-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="ee94f-103">クラスを基底クラスとしてのみ使用できることと、オブジェクトを直接作成できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee94f-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee94f-104">Remarks</span></span>  
 <span data-ttu-id="ee94f-105">目的を*基本クラス*(とも呼ばれます、*抽象クラス*) それから派生したすべてのクラスに共通した機能を定義することです。</span><span class="sxs-lookup"><span data-stu-id="ee94f-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="ee94f-106">これにより、派生クラスが共通の要素を再定義する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ee94f-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="ee94f-107">場合によっては、この共通の機能が、使用可能なオブジェクトを作成するのに十分な完了していませんし、各派生クラスが不足している機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="ee94f-108">このような場合は、派生クラスからのみオブジェクトを作成、使用側コードをします。</span><span class="sxs-lookup"><span data-stu-id="ee94f-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="ee94f-109">使用する`MustInherit`でこれを強制する基本クラス。</span><span class="sxs-lookup"><span data-stu-id="ee94f-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="ee94f-110">別の用途を`MustInherit`クラスは、関連するクラスのセットに変数を制限します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="ee94f-111">基本クラスを定義し、そこからこれらのすべての関連するクラスを派生できます。</span><span class="sxs-lookup"><span data-stu-id="ee94f-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="ee94f-112">基本クラスは、すべての派生クラスに共通の機能を提供する必要はありませんが、その変数に値を割り当てるためのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee94f-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="ee94f-113">使用側コードでは、基底クラスとしての変数を宣言する場合に、Visual Basic を使用すると、派生クラスの 1 つのオブジェクトのみをその変数に代入できます。</span><span class="sxs-lookup"><span data-stu-id="ee94f-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="ee94f-114">.NET Framework では、いくつかを定義します`MustInherit`クラスは、それらの間で<xref:System.Array>、 <xref:System.Enum>、および<xref:System.ValueType>します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="ee94f-115"><xref:System.ValueType> 変数を制限する基底クラスの例に示します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="ee94f-116">すべての値の型から派生<xref:System.ValueType>します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="ee94f-117">として変数を宣言する場合<xref:System.ValueType>、その変数に値型のみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ee94f-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ee94f-118">ルール</span><span class="sxs-lookup"><span data-stu-id="ee94f-118">Rules</span></span>  
  
- <span data-ttu-id="ee94f-119">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="ee94f-119">**Declaration Context.**</span></span> <span data-ttu-id="ee94f-120">使用することができます`MustInherit`でのみ、`Class`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="ee94f-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="ee94f-121">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="ee94f-121">**Combined Modifiers.**</span></span> <span data-ttu-id="ee94f-122">指定することはできません`MustInherit`と共に`NotInheritable`同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="ee94f-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee94f-123">例</span><span class="sxs-lookup"><span data-stu-id="ee94f-123">Example</span></span>  
 <span data-ttu-id="ee94f-124">次の例は、強制的な継承と強制的なオーバーライドを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee94f-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="ee94f-125">基本クラス`shape`変数を定義します`acrossLine`します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="ee94f-126">クラスは、`circle`と`square`から派生`shape`します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="ee94f-127">定義を継承`acrossLine`、関数を定義する必要がありますが、`area`計算は図形の種類ごとに異なるためです。</span><span class="sxs-lookup"><span data-stu-id="ee94f-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="ee94f-128">宣言できます`shape1`と`shape2`型`shape`します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="ee94f-129">オブジェクトを作成することはできませんただし、`shape`関数の機能がないため`area`がマークされていると`MustInherit`します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="ee94f-130">として宣言されているため、 `shape`、変数`shape1`と`shape2`派生クラスからオブジェクトに制限される`circle`と`square`します。</span><span class="sxs-lookup"><span data-stu-id="ee94f-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="ee94f-131">Visual Basic はできません、他のオブジェクトをこれらの変数に割り当てることにより、タイプ セーフの高レベル。</span><span class="sxs-lookup"><span data-stu-id="ee94f-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="ee94f-132">使用法</span><span class="sxs-lookup"><span data-stu-id="ee94f-132">Usage</span></span>  
 <span data-ttu-id="ee94f-133">`MustInherit`修飾子は、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee94f-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ee94f-134">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee94f-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee94f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee94f-135">See also</span></span>

- [<span data-ttu-id="ee94f-136">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee94f-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="ee94f-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="ee94f-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="ee94f-138">キーワード</span><span class="sxs-lookup"><span data-stu-id="ee94f-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ee94f-139">継承の基本</span><span class="sxs-lookup"><span data-stu-id="ee94f-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

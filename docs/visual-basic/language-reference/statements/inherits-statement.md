---
title: Inherits ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: c39272d53fea136c83a5a09444b65a594fe3b7a7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625512"
---
# <a name="inherits-statement"></a><span data-ttu-id="ce12e-102">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="ce12e-102">Inherits Statement</span></span>
<span data-ttu-id="ce12e-103">現在のクラスまたは属性、変数、プロパティ、プロシージャ、およびイベントを別のクラスまたはインターフェイスのセットから継承するインターフェイスとします。</span><span class="sxs-lookup"><span data-stu-id="ce12e-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce12e-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce12e-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="ce12e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ce12e-105">Parts</span></span>  
  
|<span data-ttu-id="ce12e-106">用語</span><span class="sxs-lookup"><span data-stu-id="ce12e-106">Term</span></span>|<span data-ttu-id="ce12e-107">定義</span><span class="sxs-lookup"><span data-stu-id="ce12e-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="ce12e-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ce12e-108">Required.</span></span> <span data-ttu-id="ce12e-109">このクラスの派生元クラスの名前。</span><span class="sxs-lookup"><span data-stu-id="ce12e-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="ce12e-110">- または -</span><span class="sxs-lookup"><span data-stu-id="ce12e-110">-or-</span></span><br /><br /> <span data-ttu-id="ce12e-111">このインターフェイスの派生元のインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="ce12e-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="ce12e-112">コンマを使用して、複数の名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="ce12e-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce12e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce12e-113">Remarks</span></span>  
 <span data-ttu-id="ce12e-114">使用する場合、`Inherits`ステートメントはクラスまたはインターフェイスの定義では、最初の空白、コメント以外の次の行である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce12e-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="ce12e-115">すぐに従ってください、`Class`または`Interface`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="ce12e-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="ce12e-116">使用することができます`Inherits`クラスまたはインターフェイスでのみです。</span><span class="sxs-lookup"><span data-stu-id="ce12e-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="ce12e-117">つまり、継承の宣言のコンテキストがソース ファイル、名前空間、構造体、モジュール、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce12e-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ce12e-118">ルール</span><span class="sxs-lookup"><span data-stu-id="ce12e-118">Rules</span></span>  
  
- <span data-ttu-id="ce12e-119">**クラスの継承します。**</span><span class="sxs-lookup"><span data-stu-id="ce12e-119">**Class Inheritance.**</span></span> <span data-ttu-id="ce12e-120">クラスで使用する場合、`Inherits`ステートメントでは、1 つだけの基本クラスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ce12e-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="ce12e-121">クラスは、その中に入れ子になったクラスから継承できません。</span><span class="sxs-lookup"><span data-stu-id="ce12e-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="ce12e-122">**インターフェイスの継承します。**</span><span class="sxs-lookup"><span data-stu-id="ce12e-122">**Interface Inheritance.**</span></span> <span data-ttu-id="ce12e-123">インターフェイスで使用する場合、`Inherits`ステートメントでは、1 つまたは複数の基底インターフェイスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ce12e-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="ce12e-124">同じ名前のメンバーが定義されている場合でも、2 つのインターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="ce12e-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="ce12e-125">これを行う場合、実装コードは、実装しています。 どのメンバーを指定する名前の修飾を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce12e-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="ce12e-126">インターフェイスより制限の厳しいアクセス レベルを持つ別のインターフェイスから継承できません。</span><span class="sxs-lookup"><span data-stu-id="ce12e-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="ce12e-127">たとえば、`Public`インターフェイスから継承することはできません、`Friend`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ce12e-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="ce12e-128">インターフェイスは、内部に入れ子になったインターフェイスから継承できません。</span><span class="sxs-lookup"><span data-stu-id="ce12e-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="ce12e-129">.NET Framework におけるクラス継承の例は、<xref:System.ArgumentException>から継承されるクラス、<xref:System.SystemException>クラス。</span><span class="sxs-lookup"><span data-stu-id="ce12e-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="ce12e-130">これにより、<xref:System.ArgumentException>すべての定義済みプロパティとなどのシステム例外によって必要な手順、<xref:System.Exception.Message%2A>プロパティおよび<xref:System.Exception.ToString%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ce12e-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="ce12e-131">.NET Framework のインターフェイスの継承の例は、<xref:System.Collections.ICollection>から継承するインターフェイスを<xref:System.Collections.IEnumerable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ce12e-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="ce12e-132">これにより、<xref:System.Collections.ICollection>コレクションを走査するために必要な列挙子の定義を継承します。</span><span class="sxs-lookup"><span data-stu-id="ce12e-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce12e-133">例</span><span class="sxs-lookup"><span data-stu-id="ce12e-133">Example</span></span>  
 <span data-ttu-id="ce12e-134">次の例では、`Inherits`クラスの名前付け方法を表示するステートメント`thisClass`という名前の基本クラスのすべてのメンバーを継承できる`anotherClass`します。</span><span class="sxs-lookup"><span data-stu-id="ce12e-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="ce12e-135">例</span><span class="sxs-lookup"><span data-stu-id="ce12e-135">Example</span></span>  
 <span data-ttu-id="ce12e-136">次の例では、複数のインターフェイスの継承を示します。</span><span class="sxs-lookup"><span data-stu-id="ce12e-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="ce12e-137">という名前のインターフェイス`thisInterface`内のすべての定義が含まれています、 <xref:System.IComparable>、 <xref:System.IDisposable>、および<xref:System.IFormattable>継承されたメンバーでは、それぞれ 2 つのオブジェクトの種類に固有の比較を解放するインターフェイスには、リソースが割り当てられますをオブジェクトとしての値を表現して、`String`します。</span><span class="sxs-lookup"><span data-stu-id="ce12e-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="ce12e-138">実装するクラス`thisInterface`すべて基底インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce12e-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce12e-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce12e-139">See also</span></span>

- [<span data-ttu-id="ce12e-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="ce12e-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="ce12e-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="ce12e-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="ce12e-142">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ce12e-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="ce12e-143">継承の基本</span><span class="sxs-lookup"><span data-stu-id="ce12e-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="ce12e-144">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce12e-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

---
title: Inherits ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 6e6e9cc9210232059210862f2bda691c57b372d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353226"
---
# <a name="inherits-statement"></a><span data-ttu-id="40eb6-102">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="40eb6-102">Inherits Statement</span></span>
<span data-ttu-id="40eb6-103">現在のクラスまたはインターフェイスが、別のクラスまたはインターフェイスのセットから属性、変数、プロパティ、プロシージャ、およびイベントを継承するようにします。</span><span class="sxs-lookup"><span data-stu-id="40eb6-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40eb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="40eb6-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="40eb6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="40eb6-105">Parts</span></span>  
  
|<span data-ttu-id="40eb6-106">用語</span><span class="sxs-lookup"><span data-stu-id="40eb6-106">Term</span></span>|<span data-ttu-id="40eb6-107">Definition</span><span class="sxs-lookup"><span data-stu-id="40eb6-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="40eb6-108">必須。</span><span class="sxs-lookup"><span data-stu-id="40eb6-108">Required.</span></span> <span data-ttu-id="40eb6-109">このクラスの派生元であるクラスの名前。</span><span class="sxs-lookup"><span data-stu-id="40eb6-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="40eb6-110">または</span><span class="sxs-lookup"><span data-stu-id="40eb6-110">-or-</span></span><br /><br /> <span data-ttu-id="40eb6-111">このインターフェイスの派生元のインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="40eb6-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="40eb6-112">複数の名前を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="40eb6-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40eb6-113">コメント</span><span class="sxs-lookup"><span data-stu-id="40eb6-113">Remarks</span></span>  
 <span data-ttu-id="40eb6-114">使用する場合、`Inherits` ステートメントは、クラスまたはインターフェイス定義の最初の空白でない、コメント以外の行である必要があります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="40eb6-115">`Class` または `Interface` ステートメントの直後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="40eb6-116">`Inherits` は、クラスまたはインターフェイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="40eb6-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="40eb6-117">つまり、継承の宣言コンテキストをソースファイル、名前空間、構造体、モジュール、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="40eb6-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="40eb6-118">ルール</span><span class="sxs-lookup"><span data-stu-id="40eb6-118">Rules</span></span>  
  
- <span data-ttu-id="40eb6-119">**クラスの継承。**</span><span class="sxs-lookup"><span data-stu-id="40eb6-119">**Class Inheritance.**</span></span> <span data-ttu-id="40eb6-120">クラスで `Inherits` ステートメントを使用する場合、指定できる基底クラスは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="40eb6-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="40eb6-121">クラスは、入れ子にされたクラスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="40eb6-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="40eb6-122">**インターフェイスの継承。**</span><span class="sxs-lookup"><span data-stu-id="40eb6-122">**Interface Inheritance.**</span></span> <span data-ttu-id="40eb6-123">インターフェイスで `Inherits` ステートメントが使用されている場合は、1つまたは複数の基本インターフェイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40eb6-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="40eb6-124">それぞれが同じ名前のメンバーを定義している場合でも、2つのインターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="40eb6-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="40eb6-125">その場合、実装するコードでは、実装するメンバーを指定するために名前の修飾を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="40eb6-126">インターフェイスは、より制限の厳しいアクセスレベルを持つ別のインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="40eb6-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="40eb6-127">たとえば、`Public` インターフェイスは、`Friend` インターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="40eb6-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="40eb6-128">インターフェイスは、その中に入れ子にされたインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="40eb6-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="40eb6-129">.NET Framework でのクラス継承の例として、<xref:System.SystemException> クラスを継承する <xref:System.ArgumentException> クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="40eb6-130">これにより、<xref:System.Exception.Message%2A> プロパティや <xref:System.Exception.ToString%2A> メソッドなど、システム例外に必要なすべての定義済みプロパティとプロシージャを <xref:System.ArgumentException> できます。</span><span class="sxs-lookup"><span data-stu-id="40eb6-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="40eb6-131">.NET Framework でのインターフェイスの継承の例として、<xref:System.Collections.IEnumerable> インターフェイスから継承する <xref:System.Collections.ICollection> インターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="40eb6-132">これにより、<xref:System.Collections.ICollection> は、コレクションを走査するために必要な列挙子の定義を継承します。</span><span class="sxs-lookup"><span data-stu-id="40eb6-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40eb6-133">例</span><span class="sxs-lookup"><span data-stu-id="40eb6-133">Example</span></span>  
 <span data-ttu-id="40eb6-134">次の例では、`Inherits` ステートメントを使用して、`thisClass` という名前のクラスが `anotherClass`という名前の基本クラスのすべてのメンバーを継承する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="40eb6-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="40eb6-135">例</span><span class="sxs-lookup"><span data-stu-id="40eb6-135">Example</span></span>  
 <span data-ttu-id="40eb6-136">次の例は、複数のインターフェイスの継承を示しています。</span><span class="sxs-lookup"><span data-stu-id="40eb6-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="40eb6-137">`thisInterface` という名前のインターフェイスには、<xref:System.IComparable>、<xref:System.IDisposable>、および <xref:System.IFormattable> インターフェイス内のすべての定義が含まれるようになりました。継承されたメンバーは、2つのオブジェクトの型固有の比較、割り当てられたリソースの解放、およびオブジェクトの値の `String`としての表現をそれぞれ提供します。</span><span class="sxs-lookup"><span data-stu-id="40eb6-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="40eb6-138">`thisInterface` を実装するクラスは、すべての基本インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40eb6-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eb6-139">参照</span><span class="sxs-lookup"><span data-stu-id="40eb6-139">See also</span></span>

- [<span data-ttu-id="40eb6-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="40eb6-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="40eb6-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="40eb6-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="40eb6-142">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="40eb6-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="40eb6-143">継承の基本</span><span class="sxs-lookup"><span data-stu-id="40eb6-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="40eb6-144">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40eb6-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

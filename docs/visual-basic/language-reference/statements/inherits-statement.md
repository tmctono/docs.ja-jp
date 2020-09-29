---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: dd8fbc71fdc859bb127764951464278267c0984c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875231"
---
# <a name="inherits-statement"></a><span data-ttu-id="b001f-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="b001f-102">Inherits Statement</span></span>

<span data-ttu-id="b001f-103">現在のクラスまたはインターフェイスで、属性、変数、プロパティ、プロシージャ、およびイベントを別のクラスまたは一連のインターフェイスから継承させます。</span><span class="sxs-lookup"><span data-stu-id="b001f-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b001f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b001f-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="b001f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b001f-105">Parts</span></span>  
  
|<span data-ttu-id="b001f-106">用語</span><span class="sxs-lookup"><span data-stu-id="b001f-106">Term</span></span>|<span data-ttu-id="b001f-107">定義</span><span class="sxs-lookup"><span data-stu-id="b001f-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="b001f-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="b001f-108">Required.</span></span> <span data-ttu-id="b001f-109">このクラスの派生元のクラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="b001f-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="b001f-110">\- または -</span><span class="sxs-lookup"><span data-stu-id="b001f-110">-or-</span></span><br /><br /> <span data-ttu-id="b001f-111">このインターフェイスの派生元のインターフェイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="b001f-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="b001f-112">複数の名前を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="b001f-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b001f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b001f-113">Remarks</span></span>  

 <span data-ttu-id="b001f-114">使用した場合、`Inherits` ステートメントが、クラスまたはインターフェイス定義の最初の空行でもコメント行でもない行に記述されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b001f-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="b001f-115">それは、`Class` または `Interface` ステートメントの直後に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b001f-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="b001f-116">`Inherits` は、クラスまたはインターフェイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b001f-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="b001f-117">つまり、継承の宣言コンテキストは、ソース ファイル、名前空間、構造体、モジュール、プロシージャ、ブロックにすることができません。</span><span class="sxs-lookup"><span data-stu-id="b001f-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b001f-118">ルール</span><span class="sxs-lookup"><span data-stu-id="b001f-118">Rules</span></span>  
  
- <span data-ttu-id="b001f-119">**クラスの継承。**</span><span class="sxs-lookup"><span data-stu-id="b001f-119">**Class Inheritance.**</span></span> <span data-ttu-id="b001f-120">クラスで `Inherits` ステートメントを使用する場合、指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="b001f-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="b001f-121">クラスは、その中の入れ子にされたクラスから継承できません。</span><span class="sxs-lookup"><span data-stu-id="b001f-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="b001f-122">**インターフェイスの継承。**</span><span class="sxs-lookup"><span data-stu-id="b001f-122">**Interface Inheritance.**</span></span> <span data-ttu-id="b001f-123">インターフェイスで `Inherits` ステートメントを使用している場合、1 つまたは複数の基底インターフェイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b001f-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="b001f-124">それぞれが同じ名前のメンバーを定義している場合でも、2 つのインターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="b001f-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="b001f-125">その場合、実装するコードでは、実装するメンバーを指定するために名前の修飾を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b001f-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="b001f-126">インターフェイスは、より制限の厳しいアクセス レベルの別のインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="b001f-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="b001f-127">たとえば、`Public` インターフェイスは、`Friend` インターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="b001f-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="b001f-128">インターフェイスは、その中に入れ子にされたインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="b001f-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="b001f-129">.NET Framework でのクラス継承の例として、<xref:System.SystemException> クラスから継承する <xref:System.ArgumentException> クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="b001f-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="b001f-130">これにより、<xref:System.ArgumentException> に、<xref:System.Exception.Message%2A> プロパティや <xref:System.Exception.ToString%2A> メソッドなど、システム例外に必要なすべての定義済みプロパティとプロシージャを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b001f-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="b001f-131">.NET Framework でのインターフェイスの継承の例として、<xref:System.Collections.IEnumerable> インターフェイスから継承する <xref:System.Collections.ICollection> インターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="b001f-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="b001f-132">これにより、<xref:System.Collections.ICollection> で、コレクションを走査するために必要な列挙子の定義が継承されます。</span><span class="sxs-lookup"><span data-stu-id="b001f-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b001f-133">例</span><span class="sxs-lookup"><span data-stu-id="b001f-133">Example</span></span>  

 <span data-ttu-id="b001f-134">次の例では、`Inherits` ステートメントを使用して、`thisClass` という名前のクラスで `anotherClass` という名前の基底クラスのすべてのメンバーを継承する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b001f-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="b001f-135">例</span><span class="sxs-lookup"><span data-stu-id="b001f-135">Example</span></span>  

 <span data-ttu-id="b001f-136">次の例では、複数インターフェイスの継承を示しています。</span><span class="sxs-lookup"><span data-stu-id="b001f-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="b001f-137">`thisInterface` という名前のインターフェイスに、<xref:System.IComparable>、<xref:System.IDisposable>、および <xref:System.IFormattable> インターフェイスのすべての定義が含まれるようになりました。継承されたメンバーではそれぞれ、2 つのオブジェクトの型固有の比較、割り当てられたリソースの解放、および `String` としてのオブジェクトの値の表現が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b001f-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="b001f-138">`thisInterface` を実装するクラスでは、すべての基底インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b001f-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b001f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b001f-139">See also</span></span>

- [<span data-ttu-id="b001f-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="b001f-140">MustInherit</span></span>](../modifiers/mustinherit.md)
- [<span data-ttu-id="b001f-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="b001f-141">NotInheritable</span></span>](../modifiers/notinheritable.md)
- [<span data-ttu-id="b001f-142">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="b001f-142">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="b001f-143">継承の基本</span><span class="sxs-lookup"><span data-stu-id="b001f-143">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="b001f-144">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b001f-144">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)

---
title: In (ジェネリック修飾子) - Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004869"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="7c78b-102">In (ジェネリック修飾子) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c78b-102">In (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="7c78b-103">ジェネリック型パラメーターの `In` キーワードは、型パラメーターが反変であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c78b-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c78b-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c78b-104">Remarks</span></span>

<span data-ttu-id="7c78b-105">反変性は、ジェネリック パラメーターによって指定された型よりも弱い派生型を使用できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="7c78b-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="7c78b-106">これにより、バリアント インターフェイスを実装するクラスの暗黙の型変換とデリゲート型の暗黙の型変換が可能となります。</span><span class="sxs-lookup"><span data-stu-id="7c78b-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="7c78b-107">詳細については、「[共変性と反変性](../../programming-guide/concepts/covariance-contravariance/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c78b-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="7c78b-108">ルール</span><span class="sxs-lookup"><span data-stu-id="7c78b-108">Rules</span></span>

<span data-ttu-id="7c78b-109">`In` キーワードは、ジェネリック インターフェイスとデリゲートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c78b-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>
  
<span data-ttu-id="7c78b-110">型パラメーターをジェネリック インターフェイスまたはデリゲートで反変として宣言できるのは、メソッド引数の型としてのみ使用され、メソッドの戻り値の型としては使用されない場合です。</span><span class="sxs-lookup"><span data-stu-id="7c78b-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="7c78b-111">`ByRef` パラメーターを共変または反変にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7c78b-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>

<span data-ttu-id="7c78b-112">共変性および反変性は参照型ではサポートされ、値の型ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7c78b-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>

<span data-ttu-id="7c78b-113">Visual Basic では、デリゲート型を指定せずに反変のインターフェイスでイベントを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c78b-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="7c78b-114">また、反変のインターフェイスでは、入れ子になったクラス、列挙型、または構造体を使用することはできませんが、入れ子になったインターフェイスを使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="7c78b-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="7c78b-115">動作</span><span class="sxs-lookup"><span data-stu-id="7c78b-115">Behavior</span></span>

<span data-ttu-id="7c78b-116">反変の型パラメーターを持つインターフェイスを使用すると、そのインターフェイスのメソッドは、インターフェイス型パラメーターによって指定された型よりも弱い派生型の引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7c78b-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="7c78b-117">たとえば、.NET Framework 4 の <xref:System.Collections.Generic.IComparer%601> インターフェイスでは T 型が反変なので、`Employee` が `Person` から継承する場合、特別な変換メソッドを使用しなくても `IComparer(Of Person)` 型のオブジェクトを `IComparer(Of Employee)` 型のオブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7c78b-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits from `Person`.</span></span>

<span data-ttu-id="7c78b-118">反変のデリゲートには、型は同じでありながらより弱い派生ジェネリック型パラメーターを持つ別のデリゲートを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7c78b-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

## <a name="example---contravariant-generic-interface"></a><span data-ttu-id="7c78b-119">例 - 反変のジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c78b-119">Example - contravariant generic interface</span></span>

<span data-ttu-id="7c78b-120">次の例では、反変のジェネリック インターフェイスを宣言、拡張、および実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c78b-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="7c78b-121">また、このインターフェイスを実装するクラスの暗黙的な変換を使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="7c78b-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a><span data-ttu-id="7c78b-122">例 - 反変の汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="7c78b-122">Example - contravariant generic delegate</span></span>

<span data-ttu-id="7c78b-123">次の例では、反変の汎用デリゲートを宣言、インスタンス化、および呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c78b-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="7c78b-124">また、デリゲート型を暗黙的に変換する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="7c78b-124">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="7c78b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c78b-125">See also</span></span>

- [<span data-ttu-id="7c78b-126">ジェネリック インターフェイスの変性</span><span class="sxs-lookup"><span data-stu-id="7c78b-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="7c78b-127">Out</span><span class="sxs-lookup"><span data-stu-id="7c78b-127">Out</span></span>](out-generic-modifier.md)

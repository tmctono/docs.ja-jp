---
title: 匿名型の定義
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: f8ac26577a7fbef865605a7ecf643fa733b2c2c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344927"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="055e6-102">匿名型の定義 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="055e6-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="055e6-103">匿名型のインスタンスの宣言に応答して、コンパイラは、型の指定されたプロパティを含む新しいクラス定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="055e6-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="055e6-104">コンパイラで生成されたコード</span><span class="sxs-lookup"><span data-stu-id="055e6-104">Compiler-Generated Code</span></span>

<span data-ttu-id="055e6-105">次の `product`の定義では、コンパイラは、`Name`、`Price`、および `OnHand`プロパティを含む新しいクラス定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="055e6-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="055e6-106">クラス定義には、次のようなプロパティ定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="055e6-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="055e6-107">キープロパティに `Set` メソッドがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="055e6-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="055e6-108">キープロパティの値は読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="055e6-108">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="055e6-109">また、匿名型の定義には、パラメーターなしのコンストラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="055e6-109">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="055e6-110">パラメーターを必要とするコンストラクターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="055e6-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="055e6-111">匿名型の宣言に少なくとも1つのキープロパティが含まれている場合、型定義は <xref:System.Object>: <xref:System.Object.Equals%2A>、<xref:System.Object.GetHashCode%2A>、および <xref:System.Object.ToString%2A>から継承された3つのメンバーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="055e6-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="055e6-112">キープロパティが宣言されていない場合は、<xref:System.Object.ToString%2A> のみがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="055e6-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="055e6-113">オーバーライドは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="055e6-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="055e6-114">2つの匿名型のインスタンスが同じインスタンスである場合、または次の条件を満たしている場合、`Equals` は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="055e6-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="055e6-115">これらのプロパティの数は同じです。</span><span class="sxs-lookup"><span data-stu-id="055e6-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="055e6-116">プロパティは同じ順序で、同じ名前と推論された型を使用して宣言されます。</span><span class="sxs-lookup"><span data-stu-id="055e6-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="055e6-117">名前比較では、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="055e6-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="055e6-118">少なくとも1つのプロパティがキープロパティであり、`Key` キーワードが同じプロパティに適用されています。</span><span class="sxs-lookup"><span data-stu-id="055e6-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="055e6-119">キープロパティの対応する各ペアの比較によって `True`が返されます。</span><span class="sxs-lookup"><span data-stu-id="055e6-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="055e6-120">たとえば、次の例では、`Equals` は `employee01` と `employee08`に対してのみ `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="055e6-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="055e6-121">各行の前のコメントは、新しいインスタンスが `employee01`と一致しない理由を指定します。</span><span class="sxs-lookup"><span data-stu-id="055e6-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="055e6-122">`GetHashcode` には、適切に一意の GetHashCode アルゴリズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="055e6-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="055e6-123">アルゴリズムでは、キープロパティのみを使用してハッシュコードを計算します。</span><span class="sxs-lookup"><span data-stu-id="055e6-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="055e6-124">`ToString` は、次の例に示すように、連結されたプロパティ値の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="055e6-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="055e6-125">キーとキー以外のプロパティの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="055e6-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="055e6-126">匿名型の明示的に名前が付けられたプロパティは、これらの生成されたメソッドと競合しません。</span><span class="sxs-lookup"><span data-stu-id="055e6-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="055e6-127">つまり、`.Equals`、`.GetHashCode`、または `.ToString` を使用してプロパティの名前を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="055e6-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="055e6-128">少なくとも1つのキープロパティを含む匿名型定義は、<xref:System.IEquatable%601?displayProperty=nameWithType> インターフェイスも実装します。 `T` は匿名型の型です。</span><span class="sxs-lookup"><span data-stu-id="055e6-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="055e6-129">匿名型の宣言では、同じアセンブリ内に存在する場合にのみ、同じ匿名型が作成され、そのプロパティの名前と推論される型は同じで、プロパティは同じ順序で宣言され、同じプロパティがキープロパティとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="055e6-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="055e6-130">参照</span><span class="sxs-lookup"><span data-stu-id="055e6-130">See also</span></span>

- [<span data-ttu-id="055e6-131">匿名型</span><span class="sxs-lookup"><span data-stu-id="055e6-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="055e6-132">方法 : 匿名型の宣言におけるプロパティ名と型を推論する</span><span class="sxs-lookup"><span data-stu-id="055e6-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)

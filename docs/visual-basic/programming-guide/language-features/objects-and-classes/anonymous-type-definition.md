---
title: 匿名型の定義 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: c8696ef58e0177d2d2bc6e2d4731206be77a33af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753884"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="865f4-102">匿名型の定義 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="865f4-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="865f4-103">匿名型のインスタンスの宣言に応答してでは、コンパイラは、型の指定したプロパティを格納する新しいクラス定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="865f4-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="865f4-104">コンパイラによって生成されたコード</span><span class="sxs-lookup"><span data-stu-id="865f4-104">Compiler-Generated Code</span></span>

<span data-ttu-id="865f4-105">次の定義の`product`、コンパイラは、プロパティを格納する新しいクラス定義を作成します。 `Name`、 `Price`、と`OnHand`します。</span><span class="sxs-lookup"><span data-stu-id="865f4-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="865f4-106">クラス定義には、次のようなプロパティの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="865f4-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="865f4-107">あることに注意してくださいありません`Set`メソッド主要なプロパティ。</span><span class="sxs-lookup"><span data-stu-id="865f4-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="865f4-108">キー プロパティの値とは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="865f4-108">The values of key properties are read-only.</span></span>

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

<span data-ttu-id="865f4-109">さらに、匿名型の定義には、既定のコンス トラクターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="865f4-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="865f4-110">パラメーターを必要とするコンス トラクターが許可されていません。</span><span class="sxs-lookup"><span data-stu-id="865f4-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="865f4-111">型定義から継承された 3 つのメンバーよりも優先される場合、匿名型の宣言には、少なくとも 1 つのキー プロパティが含まれています、 <xref:System.Object>: <xref:System.Object.Equals%2A>、 <xref:System.Object.GetHashCode%2A>、および<xref:System.Object.ToString%2A>します。</span><span class="sxs-lookup"><span data-stu-id="865f4-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="865f4-112">キー プロパティが宣言されていない場合、のみ<xref:System.Object.ToString%2A>オーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="865f4-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="865f4-113">上書きは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="865f4-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="865f4-114">`Equals` 返します`True`匿名型の 2 つのインスタンスが、同じインスタンスである場合、または、次の条件を満たしている場合。</span><span class="sxs-lookup"><span data-stu-id="865f4-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="865f4-115">同じ数のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="865f4-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="865f4-116">プロパティが同じ名前を持つ、同じ順序で宣言されているし、推論された型が同じです。</span><span class="sxs-lookup"><span data-stu-id="865f4-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="865f4-117">名前の比較は区別されません。</span><span class="sxs-lookup"><span data-stu-id="865f4-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="865f4-118">キー プロパティでは、少なくとも 1 つのプロパティと`Key`キーワードは、同じのプロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="865f4-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="865f4-119">キー プロパティの対応する各ペアの比較を返します`True`します。</span><span class="sxs-lookup"><span data-stu-id="865f4-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="865f4-120">たとえば、次の例についてで`Equals`返します`True`のみ`employee01`と`employee08`。</span><span class="sxs-lookup"><span data-stu-id="865f4-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="865f4-121">各行の新しいインスタンスが一致しない理由理由を指定する前にコメント`employee01`します。</span><span class="sxs-lookup"><span data-stu-id="865f4-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="865f4-122">`GetHashcode` 適切に一意の GetHashCode アルゴリズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="865f4-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="865f4-123">アルゴリズムでは、キー プロパティだけを使用して、ハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="865f4-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="865f4-124">`ToString` 次の例に示すように、連結されたプロパティの値の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="865f4-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="865f4-125">キーとキー以外のプロパティの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="865f4-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="865f4-126">生成されたこれらのメソッドと競合する、匿名型のプロパティを明示的に指定できません。</span><span class="sxs-lookup"><span data-stu-id="865f4-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="865f4-127">つまり、使用することはできません`.Equals`、 `.GetHashCode`、または`.ToString`にプロパティの名前します。</span><span class="sxs-lookup"><span data-stu-id="865f4-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="865f4-128">匿名型の定義には少なくとも 1 つ含まれているキー プロパティも実装、<xref:System.IEquatable%601?displayProperty=nameWithType>インターフェイス、場所`T`匿名型の種類です。</span><span class="sxs-lookup"><span data-stu-id="865f4-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="865f4-129">同じアセンブリで発生した、そのプロパティは、同じ名前を持つと推論された型が同じ、プロパティを同じ順序で宣言および同じプロパティがキー プロパティとしてマークされている場合にのみ、匿名型の宣言は、同じ匿名型を作成します。</span><span class="sxs-lookup"><span data-stu-id="865f4-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="865f4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="865f4-130">See also</span></span>

- [<span data-ttu-id="865f4-131">匿名型</span><span class="sxs-lookup"><span data-stu-id="865f4-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="865f4-132">方法: 匿名型の宣言におけるプロパティ名と型を推論します。</span><span class="sxs-lookup"><span data-stu-id="865f4-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)

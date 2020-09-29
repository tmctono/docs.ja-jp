---
title: プライベート コンストラクター - C# プログラミング ガイド
description: プライベート コンストラクターは、C# では特別なインスタンス コンストラクターであり、オブジェクトの作成方法を制限するために使用されます。 これは、ファクトリ メソッド、またはその他のコンストラクション表現形式で使用できます。
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: c6048424128b462bfc56d9c7c3cf8f75cca9298d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159346"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="deefa-104">プライベート コンストラクター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="deefa-104">Private Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="deefa-105">プライベート コンストラクターは、特別なインスタンス コンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="deefa-105">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="deefa-106">通常は、静的メンバーだけを含むクラスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="deefa-106">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="deefa-107">クラスに 1 つ以上のプライベート コンストラクターがあり、パブリック コンストラクターがない場合、他のクラス (入れ子になったクラスを除く) は、このクラスのインスタンスを作成できません。</span><span class="sxs-lookup"><span data-stu-id="deefa-107">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="deefa-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="deefa-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="deefa-109">空のコンストラクターを宣言すると、パラメーターなしのコンストラクターは自動生成されません。</span><span class="sxs-lookup"><span data-stu-id="deefa-109">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="deefa-110">コンストラクターにアクセス修飾子を指定しない場合でも、コンストラクターは既定でプライベートになります。</span><span class="sxs-lookup"><span data-stu-id="deefa-110">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="deefa-111">しかし、通常は、[プライベート](../../language-reference/keywords/private.md)修飾子を明示的に使用して、クラスをインスタンス化できないことを明確に示します。</span><span class="sxs-lookup"><span data-stu-id="deefa-111">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="deefa-112">プライベート コンストラクターは、<xref:System.Math> クラスなどのインスタンス フィールドやメソッドが存在しない場合や、クラスのインスタンスを取得するためにメソッドが呼び出される場合に、クラスのインスタンスが作成されないようにするために使用します。</span><span class="sxs-lookup"><span data-stu-id="deefa-112">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="deefa-113">クラス内のすべてのメソッドが静的な場合は、クラス全体を静的にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="deefa-113">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="deefa-114">詳細については、「[静的クラスと静的クラス メンバー](./static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deefa-114">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="deefa-115">例</span><span class="sxs-lookup"><span data-stu-id="deefa-115">Example</span></span>  

 <span data-ttu-id="deefa-116">次に示すのは、プライベート コンストラクターを使用するクラスの例です。</span><span class="sxs-lookup"><span data-stu-id="deefa-116">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="deefa-117">この例で、次のステートメントをコメント解除すると、保護レベルのためにコンストラクターにアクセスできなくなり、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="deefa-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="deefa-118">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="deefa-118">C# Language Specification</span></span>  

<span data-ttu-id="deefa-119">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[プライベート コンストラクター](~/_csharplang/spec/classes.md#private-constructors)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="deefa-119">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="deefa-120">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="deefa-120">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="deefa-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="deefa-121">See also</span></span>

- [<span data-ttu-id="deefa-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="deefa-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="deefa-123">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="deefa-123">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="deefa-124">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="deefa-124">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="deefa-125">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="deefa-125">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="deefa-126">private</span><span class="sxs-lookup"><span data-stu-id="deefa-126">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="deefa-127">public</span><span class="sxs-lookup"><span data-stu-id="deefa-127">public</span></span>](../../language-reference/keywords/public.md)

---
title: プライベート コンストラクター - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 2f8b93fbeb7c2996f3e2683fe86f159fbfa61a92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705445"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="ef635-102">プライベート コンストラクター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ef635-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="ef635-103">プライベート コンストラクターは、特別なインスタンス コンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="ef635-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="ef635-104">通常は、静的メンバーだけを含むクラスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef635-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="ef635-105">クラスに 1 つ以上のプライベート コンストラクターがあり、パブリック コンストラクターがない場合、他のクラス (入れ子になったクラスを除く) は、このクラスのインスタンスを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ef635-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="ef635-106">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ef635-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="ef635-107">空のコンストラクターを宣言すると、パラメーターなしのコンストラクターは自動生成されません。</span><span class="sxs-lookup"><span data-stu-id="ef635-107">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="ef635-108">コンストラクターにアクセス修飾子を指定しない場合でも、コンストラクターは既定でプライベートになります。</span><span class="sxs-lookup"><span data-stu-id="ef635-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="ef635-109">しかし、通常は、[プライベート](../../language-reference/keywords/private.md)修飾子を明示的に使用して、クラスをインスタンス化できないことを明確に示します。</span><span class="sxs-lookup"><span data-stu-id="ef635-109">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="ef635-110">プライベート コンストラクターは、<xref:System.Math> クラスなどのインスタンス フィールドやメソッドが存在しない場合や、クラスのインスタンスを取得するためにメソッドが呼び出される場合に、クラスのインスタンスが作成されないようにするために使用します。</span><span class="sxs-lookup"><span data-stu-id="ef635-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="ef635-111">クラス内のすべてのメソッドが静的な場合は、クラス全体を静的にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ef635-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="ef635-112">詳細については、「[静的クラスと静的クラス メンバー](./static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef635-112">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef635-113">例</span><span class="sxs-lookup"><span data-stu-id="ef635-113">Example</span></span>  
 <span data-ttu-id="ef635-114">次に示すのは、プライベート コンストラクターを使用するクラスの例です。</span><span class="sxs-lookup"><span data-stu-id="ef635-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="ef635-115">この例で、次のステートメントをコメント解除すると、保護レベルのためにコンストラクターにアクセスできなくなり、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ef635-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ef635-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ef635-116">C# Language Specification</span></span>  

<span data-ttu-id="ef635-117">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[プライベート コンストラクター](~/_csharplang/spec/classes.md#private-constructors)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef635-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ef635-118">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="ef635-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef635-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef635-119">See also</span></span>

- [<span data-ttu-id="ef635-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ef635-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ef635-121">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="ef635-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="ef635-122">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="ef635-122">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="ef635-123">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="ef635-123">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="ef635-124">private</span><span class="sxs-lookup"><span data-stu-id="ef635-124">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="ef635-125">public</span><span class="sxs-lookup"><span data-stu-id="ef635-125">public</span></span>](../../language-reference/keywords/public.md)

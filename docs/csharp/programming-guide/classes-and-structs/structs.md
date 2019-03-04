---
title: 構造体 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 6c260408b7cdbb7bd55477a57ca879d89c3c0144
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977033"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="140a8-102">構造体 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="140a8-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="140a8-103">構造体は [struct](../../language-reference/keywords/struct.md) キーワードを使って定義します。次はその例です。</span><span class="sxs-lookup"><span data-stu-id="140a8-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="140a8-104">構造体の構文はクラスとほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="140a8-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="140a8-105">構造体の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="140a8-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="140a8-106">構造体は次の点でクラスよりも制限されています。</span><span class="sxs-lookup"><span data-stu-id="140a8-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="140a8-107">構造体宣言内では、const または static と宣言されているフィールド以外は初期化できません。</span><span class="sxs-lookup"><span data-stu-id="140a8-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="140a8-108">構造体では、既定のコンストラクター (パラメーターなしのコンストラクター) やファイナライザーを宣言できません。</span><span class="sxs-lookup"><span data-stu-id="140a8-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="140a8-109">構造体は、割り当て時にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="140a8-109">Structs are copied on assignment.</span></span> <span data-ttu-id="140a8-110">構造体を新しい変数に割り当てると、すべてのデータがコピーされ、新しいコピーを変更しても、元のコピーのデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="140a8-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="140a8-111">これは、`Dictionary<string, myStruct>` などの値の型のコレクションを使用する際に重要です。</span><span class="sxs-lookup"><span data-stu-id="140a8-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="140a8-112">参照型であるクラスとは異なり、構造体は値型です。</span><span class="sxs-lookup"><span data-stu-id="140a8-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="140a8-113">クラスとは異なり、構造体は `new` 演算子を使用せずにインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="140a8-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="140a8-114">構造体は、パラメーターのあるコンストラクターを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="140a8-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="140a8-115">構造体は、他の構造体やクラスから継承できず、基本クラスになることはできません。</span><span class="sxs-lookup"><span data-stu-id="140a8-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="140a8-116">すべての構造体が <xref:System.ValueType> を直接継承し、System.ValueType は <xref:System.Object> を継承します。</span><span class="sxs-lookup"><span data-stu-id="140a8-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="140a8-117">構造体は、インターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="140a8-117">A struct can implement interfaces.</span></span> 
- <span data-ttu-id="140a8-118">構造体は `null` にすることができません。変数が null 許容型として宣言されない限り、構造体変数に `null` を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="140a8-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable type.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="140a8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="140a8-119">Related sections</span></span>  

<span data-ttu-id="140a8-120">詳細情報</span><span class="sxs-lookup"><span data-stu-id="140a8-120">For more information:</span></span>  
  
- [<span data-ttu-id="140a8-121">構造体の使用</span><span class="sxs-lookup"><span data-stu-id="140a8-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="140a8-122">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="140a8-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="140a8-123">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="140a8-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="140a8-124">方法: メソッドに構造体を渡すこととクラス参照を渡すことの違いを理解する</span><span class="sxs-lookup"><span data-stu-id="140a8-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="140a8-125">方法: 構造体間にユーザー定義の変換を実装する</span><span class="sxs-lookup"><span data-stu-id="140a8-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="140a8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="140a8-126">See also</span></span>

- [<span data-ttu-id="140a8-127">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="140a8-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="140a8-128">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="140a8-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="140a8-129">クラス</span><span class="sxs-lookup"><span data-stu-id="140a8-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="140a8-130">識別子名</span><span class="sxs-lookup"><span data-stu-id="140a8-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)

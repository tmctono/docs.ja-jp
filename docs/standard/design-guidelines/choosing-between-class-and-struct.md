---
title: クラスまたは構造体の選択
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
author: KrzysztofCwalina
ms.openlocfilehash: 5041368ca1a440698c399c935ac72aba2002c3ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615267"
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="415ca-102">クラスまたは構造体の選択</span><span class="sxs-lookup"><span data-stu-id="415ca-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="415ca-103">すべてのフレームワーク設計者が直面する基本的な設計上の決定の 1 つが、ある型をクラス (参照型) として設計するか、構造体 (値型) として設計するかという点です。</span><span class="sxs-lookup"><span data-stu-id="415ca-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="415ca-104">この決定を下すためには、参照型と値の型の動作の違いをよく理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="415ca-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="415ca-105">取り上げる最初の違いは、メモリー割り当てと解放に関するものです。参照型はヒープ メモリに割り当てられガベージ コレクションの対象となります。一方、値型はスタック メモリか、それを含む型の内部に割り当てられ、スタックがアンワインドされるかそれを含む型が解放される時に解放されます。</span><span class="sxs-lookup"><span data-stu-id="415ca-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="415ca-106">そのため、一般的に値型の割り当てと解放は、参照型よりも低コストです。</span><span class="sxs-lookup"><span data-stu-id="415ca-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="415ca-107">次の違いは配列に関するものです。参照型の配列では、インスタンスは配列外に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="415ca-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="415ca-108">つまり、配列要素はヒープ上にあるインスタンスへの参照であるということです。</span><span class="sxs-lookup"><span data-stu-id="415ca-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="415ca-109">値型の配列はインラインです。つまり、配列要素は値型の実際のインスタンスであるということです。</span><span class="sxs-lookup"><span data-stu-id="415ca-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="415ca-110">したがって、値型の配列の割り当てと解放は、参照型の配列と比べてかなり低コストになります。</span><span class="sxs-lookup"><span data-stu-id="415ca-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="415ca-111">さらに、ほとんどのケースでは、値型の配列では参照の局所性がとても良くなります。</span><span class="sxs-lookup"><span data-stu-id="415ca-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="415ca-112">値型は、参照型やそれが実装するインターフェイスにキャストされる時にボックス化されます。</span><span class="sxs-lookup"><span data-stu-id="415ca-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="415ca-113">そして、値型に再キャストされたときにボックス化解除されます。</span><span class="sxs-lookup"><span data-stu-id="415ca-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="415ca-114">ボックス化されたオブジェクトはヒープに割り当てられ、ガベージ コレクションの対象となるため、ボックス化とボックス化解除があまりに頻繁に行われると、ヒープ メモリ、ガベージ コレクター、そして最終的にはアプリケーション全体のパフォーマンスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="415ca-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="415ca-115">これに対し、参照型はキャストされるため、このようなボックス化は行われません。</span><span class="sxs-lookup"><span data-stu-id="415ca-115">In contrast, no such boxing occurs as reference types are cast.</span></span> <span data-ttu-id="415ca-116">(詳細については、[ボックス化とボックス化解除](../../csharp/programming-guide/types/boxing-and-unboxing.md)を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="415ca-116">(For more information, see [Boxing and Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).</span></span>
  
 <span data-ttu-id="415ca-117">次の点は、コピーに関するものです。参照型が参照のみをコピーする一方、値型は値全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="415ca-117">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="415ca-118">そのため、大きな参照型の割り当ては、大きな値型の割り当てよりも低コストです。</span><span class="sxs-lookup"><span data-stu-id="415ca-118">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="415ca-119">最後の点です。値型は値渡しされますが、参照型は参照渡しされます。</span><span class="sxs-lookup"><span data-stu-id="415ca-119">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="415ca-120">参照型インスタンスへの変更は、そのインスタンスを指すすべての参照に影響します。</span><span class="sxs-lookup"><span data-stu-id="415ca-120">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="415ca-121">値型インスタンスは、値渡しされるときにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="415ca-121">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="415ca-122">値型インスタンスが変更されたとしても、その他のコピーにはもちろん影響しません。</span><span class="sxs-lookup"><span data-stu-id="415ca-122">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="415ca-123">ユーザーが明示的にそうしなくても、引数を渡したり戻り値を返したりするときに暗黙的にコピーが作成されるため、変更可能な値型は、多くのユーザーにとって混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="415ca-123">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="415ca-124">そのため、値型は変更不可能であるべきです。</span><span class="sxs-lookup"><span data-stu-id="415ca-124">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="415ca-125">一般に、フレームワーク内の型の大部分は、クラスであるべきです。</span><span class="sxs-lookup"><span data-stu-id="415ca-125">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="415ca-126">ただし、状況によっては値型の特性により構造体を使用する方が適切な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="415ca-126">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="415ca-127">**✓** ある型のインスタンスは小さく、一般的に有効期間が短いかその他のオブジェクトに埋め込まれるのであれば、クラスの代わりに構造体を定義することを\*\*考慮してください。</span><span class="sxs-lookup"><span data-stu-id="415ca-127">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="415ca-128">**X** 次の条件をすべて満たさない限り、構造体を\*\*定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="415ca-128">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
- <span data-ttu-id="415ca-129">プリミティブ型 (`int`、`double`など) のように、論理的に 1 つの値を表す。</span><span class="sxs-lookup"><span data-stu-id="415ca-129">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
- <span data-ttu-id="415ca-130">インスタンスのサイズは 16 バイト未満である。</span><span class="sxs-lookup"><span data-stu-id="415ca-130">It has an instance size under 16 bytes.</span></span>  
  
- <span data-ttu-id="415ca-131">変更不可である。</span><span class="sxs-lookup"><span data-stu-id="415ca-131">It is immutable.</span></span>  
  
- <span data-ttu-id="415ca-132">頻繁にボックス化することはない。</span><span class="sxs-lookup"><span data-stu-id="415ca-132">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="415ca-133">他のすべてのケースでは、クラスとして、型を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="415ca-133">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="415ca-134">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="415ca-134">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="415ca-135">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="415ca-135">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415ca-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="415ca-136">See also</span></span>

- [<span data-ttu-id="415ca-137">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="415ca-137">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="415ca-138">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="415ca-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

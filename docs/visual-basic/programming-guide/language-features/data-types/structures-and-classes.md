---
title: 構造体とクラス
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 3353935a74bb77fa4a630e706aa425063c7a610a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346326"
---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="c6771-102">構造体とクラス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6771-102">Structures and Classes (Visual Basic)</span></span>
<span data-ttu-id="c6771-103">Visual Basic は構造体とクラスの構文を統一します。結果として、両方のエンティティが同じ機能の大部分をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6771-103">Visual Basic unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="c6771-104">ただし、構造体とクラスには重要な違いもあります。</span><span class="sxs-lookup"><span data-stu-id="c6771-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="c6771-105">クラスには参照型を使用できるという利点があります。参照を渡すことは、構造体変数をすべてのデータと共に渡すよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="c6771-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="c6771-106">一方、構造体では、グローバルヒープにメモリを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6771-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="c6771-107">構造体から継承することはできないため、構造体は拡張する必要のないオブジェクトに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6771-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="c6771-108">作成するオブジェクトのインスタンスサイズが小さい場合は構造体を使用し、クラスと構造体のパフォーマンス特性を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="c6771-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="c6771-109">共通</span><span class="sxs-lookup"><span data-stu-id="c6771-109">Similarities</span></span>  
 <span data-ttu-id="c6771-110">構造体とクラスは、次の点で似ています。</span><span class="sxs-lookup"><span data-stu-id="c6771-110">Structures and classes are similar in the following respects:</span></span>  
  
- <span data-ttu-id="c6771-111">どちらも*コンテナー*型であり、他の型をメンバーとして含むことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c6771-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
- <span data-ttu-id="c6771-112">どちらにもメンバーがあります。これには、コンストラクター、メソッド、プロパティ、フィールド、定数、列挙体、イベント、およびイベントハンドラーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c6771-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="c6771-113">ただし、これらのメンバーは、構造体の宣言された*要素*と混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="c6771-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
- <span data-ttu-id="c6771-114">どちらのメンバーも、個別のアクセスレベルを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="c6771-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="c6771-115">たとえば、1つのメンバーを `Public` および別の `Private`として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
- <span data-ttu-id="c6771-116">どちらもインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-116">Both can implement interfaces.</span></span>  
  
- <span data-ttu-id="c6771-117">どちらも、パラメーターの有無にかかわらず、共有コンストラクターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="c6771-117">Both can have shared constructors, with or without parameters.</span></span>  
  
- <span data-ttu-id="c6771-118">プロパティが少なくとも1つのパラメーターを受け取る場合は、どちらも*既定のプロパティ*を公開できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
- <span data-ttu-id="c6771-119">どちらもイベントを宣言して発生させることができ、どちらもデリゲートを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="c6771-120">[残領域]</span><span class="sxs-lookup"><span data-stu-id="c6771-120">Differences</span></span>  
 <span data-ttu-id="c6771-121">構造体とクラスは、次の点で異なります。</span><span class="sxs-lookup"><span data-stu-id="c6771-121">Structures and classes differ in the following particulars:</span></span>  
  
- <span data-ttu-id="c6771-122">構造体は*値型*です。クラスは*参照型*です。</span><span class="sxs-lookup"><span data-stu-id="c6771-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="c6771-123">構造体型の変数は、データへの参照をクラス型として格納するのではなく、構造体のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="c6771-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
- <span data-ttu-id="c6771-124">構造体はスタック割り当てを使用します。クラスは、ヒープ割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6771-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
- <span data-ttu-id="c6771-125">既定では、すべての構造体要素が `Public` されます。クラス変数および定数は既定では `Private` ますが、他のクラスメンバーは既定では `Public` ます。</span><span class="sxs-lookup"><span data-stu-id="c6771-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="c6771-126">クラスメンバーのこの動作は、既定の Visual Basic 6.0 システムとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6771-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
- <span data-ttu-id="c6771-127">構造体には、少なくとも1つの非共有変数または非共有のカスタム event 要素が必要です。クラスは完全に空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6771-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
- <span data-ttu-id="c6771-128">構造体要素を `Protected`として宣言することはできません。クラスメンバーは、を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
- <span data-ttu-id="c6771-129">構造体プロシージャでイベントを処理できるのは、それが[共有](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` プロシージャであり、かつ、 [AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)を使用した場合のみです。すべてのクラスプロシージャは、 [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)キーワードまたは `AddHandler` ステートメントを使用して、イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="c6771-130">詳細については、「 [イベント](../../../../visual-basic/programming-guide/language-features/events/index.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。</span><span class="sxs-lookup"><span data-stu-id="c6771-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
- <span data-ttu-id="c6771-131">構造体変数の宣言では、配列の初期化子または初期サイズを指定できません。クラス変数宣言では、を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
- <span data-ttu-id="c6771-132">構造体は <xref:System.ValueType?displayProperty=nameWithType> クラスから暗黙的に継承し、他の型から継承することはできません。クラスは、<xref:System.ValueType?displayProperty=nameWithType>以外のクラスまたはクラスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=nameWithType> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="c6771-133">構造体は継承できません。クラスはです。</span><span class="sxs-lookup"><span data-stu-id="c6771-133">Structures are not inheritable; classes are.</span></span>  
  
- <span data-ttu-id="c6771-134">構造体は終了されないため、共通言語ランタイム (CLR) は、どの構造体でも <xref:System.Object.Finalize%2A> メソッドを呼び出すことはありません。クラスは、ガベージコレクター (GC) によって終了されます。これは、アクティブな参照が残っていないことを検出したときに、クラスの <xref:System.Object.Finalize%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c6771-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
- <span data-ttu-id="c6771-135">構造体はコンストラクターを必要としません。クラスは、を行います。</span><span class="sxs-lookup"><span data-stu-id="c6771-135">A structure does not require a constructor; a class does.</span></span>  
  
- <span data-ttu-id="c6771-136">構造体は、パラメーターを受け取る場合にのみ、非共有コンストラクターを持つことができます。クラスは、パラメーターの有無にかかわらず、これらを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="c6771-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="c6771-137">すべての構造体には、パラメーターを持たない暗黙のパブリックコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="c6771-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="c6771-138">このコンストラクターは、すべての構造体のデータ要素を既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="c6771-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="c6771-139">この動作を再定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6771-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="c6771-140">インスタンスと変数</span><span class="sxs-lookup"><span data-stu-id="c6771-140">Instances and Variables</span></span>  
 <span data-ttu-id="c6771-141">構造体は値型であるため、各構造体変数は個々の構造体インスタンスに永続的にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="c6771-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="c6771-142">ただし、クラスは参照型であり、オブジェクト変数はさまざまなタイミングでさまざまなクラスインスタンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="c6771-143">この区別は、次の方法で構造体とクラスの使用に影響します。</span><span class="sxs-lookup"><span data-stu-id="c6771-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
- <span data-ttu-id="c6771-144">**イニシャライズ.**</span><span class="sxs-lookup"><span data-stu-id="c6771-144">**Initialization.**</span></span> <span data-ttu-id="c6771-145">構造体変数には、構造体のパラメーターなしのコンストラクターを使用した要素の初期化が暗黙的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6771-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="c6771-146">したがって、`Dim s As struct1` は `Dim s As struct1 = New struct1()`と同じです。</span><span class="sxs-lookup"><span data-stu-id="c6771-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
- <span data-ttu-id="c6771-147">**変数を割り当てています。**</span><span class="sxs-lookup"><span data-stu-id="c6771-147">**Assigning Variables.**</span></span> <span data-ttu-id="c6771-148">ある構造体変数を別の構造体変数に割り当てるか、または構造体インスタンスをプロシージャ引数に渡すと、すべての変数要素の現在の値が新しい構造体にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c6771-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="c6771-149">あるオブジェクト変数を別のオブジェクト変数に割り当てるか、またはオブジェクト変数をプロシージャに渡すと、参照ポインターだけがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c6771-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
- <span data-ttu-id="c6771-150">**何も割り当てません。**</span><span class="sxs-lookup"><span data-stu-id="c6771-150">**Assigning Nothing.**</span></span> <span data-ttu-id="c6771-151">構造体変数に値[Nothing](../../../../visual-basic/language-reference/nothing.md)を割り当てることができますが、インスタンスは引き続き変数に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c6771-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="c6771-152">変数要素は割り当てによって再初期化されますが、そのメソッドを呼び出してデータ要素にアクセスすることはできます。</span><span class="sxs-lookup"><span data-stu-id="c6771-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="c6771-153">これに対して、オブジェクト変数を `Nothing`に設定した場合、どのクラスインスタンスとも関連付けを解除すると、別のインスタンスを割り当てるまで変数を介してメンバーにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6771-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
- <span data-ttu-id="c6771-154">**複数のインスタンス。**</span><span class="sxs-lookup"><span data-stu-id="c6771-154">**Multiple Instances.**</span></span> <span data-ttu-id="c6771-155">オブジェクト変数は、異なるタイミングで異なるクラスインスタンスを割り当てることができ、複数のオブジェクト変数が同じクラスインスタンスを同時に参照できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="c6771-156">クラスメンバーの値に加えた変更は、同じインスタンスを指す別の変数を介してアクセスされた場合に、それらのメンバーに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="c6771-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="c6771-157">ただし、構造体要素は、独自のインスタンス内で分離されます。</span><span class="sxs-lookup"><span data-stu-id="c6771-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="c6771-158">その値に対する変更は、同じ `Structure` 宣言の他のインスタンスであっても、他の構造体変数には反映されません。</span><span class="sxs-lookup"><span data-stu-id="c6771-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
- <span data-ttu-id="c6771-159">**等.**</span><span class="sxs-lookup"><span data-stu-id="c6771-159">**Equality.**</span></span> <span data-ttu-id="c6771-160">2つの構造体の等価テストは、要素ごとのテストで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6771-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="c6771-161"><xref:System.Object.Equals%2A> メソッドを使用して、2つのオブジェクト変数を比較できます。</span><span class="sxs-lookup"><span data-stu-id="c6771-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="c6771-162"><xref:System.Object.Equals%2A> 2 つの変数が同じインスタンスを指しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c6771-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6771-163">参照</span><span class="sxs-lookup"><span data-stu-id="c6771-163">See also</span></span>

- [<span data-ttu-id="c6771-164">データの種類</span><span class="sxs-lookup"><span data-stu-id="c6771-164">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="c6771-165">複合データ型</span><span class="sxs-lookup"><span data-stu-id="c6771-165">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="c6771-166">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="c6771-166">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="c6771-167">構造体</span><span class="sxs-lookup"><span data-stu-id="c6771-167">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c6771-168">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="c6771-168">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="c6771-169">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="c6771-169">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="c6771-170">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c6771-170">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

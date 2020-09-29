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
ms.openlocfilehash: e7ca5b9d55611eafad88517e71f9807fe2aa4416
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086219"
---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="6df4f-102">構造体とクラス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6df4f-102">Structures and Classes (Visual Basic)</span></span>

<span data-ttu-id="6df4f-103">Visual Basic では構造体とクラスの構文が統一されており、結果として、両方のエンティティで同じ機能の大部分がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-103">Visual Basic unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="6df4f-104">ただし、構造体とクラスの間には重要な違いもあります。</span><span class="sxs-lookup"><span data-stu-id="6df4f-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="6df4f-105">クラスには参照型にすることができるという利点があります。参照を渡すことは、構造体変数をすべてのデータと共に渡すよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="6df4f-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="6df4f-106">一方、構造体では、グローバル ヒープにメモリを割り当てる必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6df4f-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="6df4f-107">構造体から継承することはできないため、拡張する必要のないオブジェクトに対してのみ構造体を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6df4f-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="6df4f-108">作成しようとするオブジェクトのインスタンス サイズが小さい場合は構造体を使用します。クラスと構造体のパフォーマンス特性を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6df4f-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="6df4f-109">類似点</span><span class="sxs-lookup"><span data-stu-id="6df4f-109">Similarities</span></span>  

 <span data-ttu-id="6df4f-110">構造体とクラスは、次の点で似ています。</span><span class="sxs-lookup"><span data-stu-id="6df4f-110">Structures and classes are similar in the following respects:</span></span>  
  
- <span data-ttu-id="6df4f-111">どちらも "*コンテナー*" 型です。つまり、他の型がメンバーとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df4f-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
- <span data-ttu-id="6df4f-112">どちらにもメンバーがあります。これには、コンストラクター、メソッド、プロパティ、フィールド、定数、列挙体、イベント、およびイベント ハンドラーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="6df4f-113">ただし、これらのメンバーを、構造体の宣言された "*要素*" と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6df4f-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
- <span data-ttu-id="6df4f-114">どちらのメンバーにも個別のアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="6df4f-115">たとえば、1 つのメンバーを `Public` および別のメンバーを `Private` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
- <span data-ttu-id="6df4f-116">どちらもインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-116">Both can implement interfaces.</span></span>  
  
- <span data-ttu-id="6df4f-117">どちらも、パラメーターの有無にかかわらず、共有コンストラクターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-117">Both can have shared constructors, with or without parameters.</span></span>  
  
- <span data-ttu-id="6df4f-118">どちらも "*既定のプロパティ*" を公開できます (そのプロパティが少なくとも 1 つのパラメーターを受け取る場合)。</span><span class="sxs-lookup"><span data-stu-id="6df4f-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
- <span data-ttu-id="6df4f-119">どちらもイベントを宣言して発生させることができ、どちらもデリゲートを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="6df4f-120">相違点</span><span class="sxs-lookup"><span data-stu-id="6df4f-120">Differences</span></span>  

 <span data-ttu-id="6df4f-121">構造体とクラスは、次の点で異なります。</span><span class="sxs-lookup"><span data-stu-id="6df4f-121">Structures and classes differ in the following particulars:</span></span>  
  
- <span data-ttu-id="6df4f-122">構造体は "*値型*" で、クラスは "*参照型*" です。</span><span class="sxs-lookup"><span data-stu-id="6df4f-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="6df4f-123">構造体型の変数は、クラス型のようにデータへの参照を格納するのではなく、構造体のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="6df4f-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
- <span data-ttu-id="6df4f-124">構造体はスタック割り当てを使用し、クラスはヒープ割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="6df4f-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
- <span data-ttu-id="6df4f-125">すべての構造体要素は既定で `Public` です。クラスの変数および定数は既定で `Private` ですが、他のクラス メンバーは既定で `Public` です。</span><span class="sxs-lookup"><span data-stu-id="6df4f-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="6df4f-126">クラス メンバーのこの動作によって、Visual Basic 6.0 システムの既定値との互換性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
- <span data-ttu-id="6df4f-127">構造体には少なくとも 1 つの非共有変数または非共有非カスタムのイベント要素が必要です。クラスは完全に空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
- <span data-ttu-id="6df4f-128">構造体要素を `Protected` として宣言することはできません。クラス メンバーは宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
- <span data-ttu-id="6df4f-129">構造体プロシージャがイベントを処理できるのは、それが[共有](../../../language-reference/modifiers/shared.md) `Sub` プロシージャであり、[AddHandler ステートメント](../../../language-reference/statements/addhandler-statement.md)を使用する場合のみです。すべてのクラス プロシージャは、[Handles](../../../language-reference/statements/handles-clause.md) キーワードまたは `AddHandler` ステートメントを使用してイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-129">A structure procedure can handle events only if it is a [Shared](../../../language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="6df4f-130">詳細については、「[イベント](../events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df4f-130">For more information, see [Events](../events/index.md).</span></span>  
  
- <span data-ttu-id="6df4f-131">構造体変数の宣言では、配列の初期化子または初期サイズを指定できません。クラス変数の宣言ではできます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
- <span data-ttu-id="6df4f-132">構造体は <xref:System.ValueType?displayProperty=nameWithType> クラスを暗黙的に継承し、他の型を継承することはできません。クラスは、<xref:System.ValueType?displayProperty=nameWithType> 以外の任意のクラス (1 つまたは複数) を継承できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=nameWithType> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="6df4f-133">構造体を継承することはできません。クラスはできます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-133">Structures are not inheritable; classes are.</span></span>  
  
- <span data-ttu-id="6df4f-134">構造体は終了することがないため、共通言語ランタイム (CLR) は、どの構造体に対しても <xref:System.Object.Finalize%2A> メソッドを呼び出すことはありません。クラスは、ガベージ コレクター (GC) によって終了されます。これは、アクティブな参照が残っていないことを検出したときに、クラスに対して <xref:System.Object.Finalize%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6df4f-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
- <span data-ttu-id="6df4f-135">構造体ではコンストラクターが必要ありません。クラスでは必要です。</span><span class="sxs-lookup"><span data-stu-id="6df4f-135">A structure does not require a constructor; a class does.</span></span>  
  
- <span data-ttu-id="6df4f-136">構造体が非共有コンストラクターを持つことができるのは、パラメーターを受け取る場合のみです。クラスは、パラメーターの有無にかかわらず持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="6df4f-137">すべての構造体には、パラメーターなしの暗黙のパブリック コンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="6df4f-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="6df4f-138">このコンストラクターでは、構造体のすべてのデータ要素が既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="6df4f-139">この動作を再定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="6df4f-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="6df4f-140">インスタンスと変数</span><span class="sxs-lookup"><span data-stu-id="6df4f-140">Instances and Variables</span></span>  

 <span data-ttu-id="6df4f-141">構造体は値型であるため、各構造体変数は個々の構造体インスタンスに永続的にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="6df4f-142">ただし、クラスは参照型であり、オブジェクト変数はさまざまな時点でさまざまなクラス インスタンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="6df4f-143">この違いは、次のように構造体とクラスの使用方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="6df4f-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
- <span data-ttu-id="6df4f-144">**初期化。**</span><span class="sxs-lookup"><span data-stu-id="6df4f-144">**Initialization.**</span></span> <span data-ttu-id="6df4f-145">構造体変数には、構造体のパラメーターなしのコンストラクターを使用した、要素の初期化が暗黙的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="6df4f-146">したがって、`Dim s As struct1` は `Dim s As struct1 = New struct1()` と同じです。</span><span class="sxs-lookup"><span data-stu-id="6df4f-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
- <span data-ttu-id="6df4f-147">**変数の代入。**</span><span class="sxs-lookup"><span data-stu-id="6df4f-147">**Assigning Variables.**</span></span> <span data-ttu-id="6df4f-148">ある構造体変数を別の構造体変数に代入したり、構造体インスタンスをプロシージャ引数に渡したりすると、すべての変数要素の現在の値が新しい構造体にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="6df4f-149">あるオブジェクト変数を別のオブジェクト変数に代入したり、オブジェクト変数をプロシージャに渡したりすると、参照ポインターだけがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
- <span data-ttu-id="6df4f-150">**Nothing の代入。**</span><span class="sxs-lookup"><span data-stu-id="6df4f-150">**Assigning Nothing.**</span></span> <span data-ttu-id="6df4f-151">値 [Nothing](../../../language-reference/nothing.md) を構造体変数に代入することができますが、インスタンスはその変数に関連付けられたままになります。</span><span class="sxs-lookup"><span data-stu-id="6df4f-151">You can assign the value [Nothing](../../../language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="6df4f-152">引き続き、メソッドを呼び出してデータ要素にアクセスすることができますが、変数要素は代入によって再初期化されています。</span><span class="sxs-lookup"><span data-stu-id="6df4f-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="6df4f-153">対照的に、オブジェクト変数を `Nothing` に設定した場合は、クラス インスタンスとの関連付けが解除され、別のインスタンスを割り当てるまで変数を介してメンバーにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6df4f-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
- <span data-ttu-id="6df4f-154">**複数インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="6df4f-154">**Multiple Instances.**</span></span> <span data-ttu-id="6df4f-155">1 つのオブジェクト変数には、さまざまな時点でさまざまなクラス インスタンスを割り当てることができます。また、複数のオブジェクト変数が同じクラス インスタンスを同時に参照できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="6df4f-156">クラス メンバーの値に加える変更が、それらのメンバーに影響を与えるのは、同じインスタンスを指す別の変数を介してそれらがアクセスされるときです。</span><span class="sxs-lookup"><span data-stu-id="6df4f-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="6df4f-157">ただし、構造体要素はそれ自体のインスタンス内に分離されています。</span><span class="sxs-lookup"><span data-stu-id="6df4f-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="6df4f-158">その値に対する変更は、同じ `Structure` 宣言の他のインスタンスであっても、他の構造体変数には反映されません。</span><span class="sxs-lookup"><span data-stu-id="6df4f-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
- <span data-ttu-id="6df4f-159">**等価。**</span><span class="sxs-lookup"><span data-stu-id="6df4f-159">**Equality.**</span></span> <span data-ttu-id="6df4f-160">2 つの構造体の等価テストは、要素ごとのテストで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df4f-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="6df4f-161"><xref:System.Object.Equals%2A> メソッドを使用して、2 つのオブジェクト変数を比較できます。</span><span class="sxs-lookup"><span data-stu-id="6df4f-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="6df4f-162"><xref:System.Object.Equals%2A> は、2 つの変数が同じインスタンスを指しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6df4f-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df4f-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="6df4f-163">See also</span></span>

- [<span data-ttu-id="6df4f-164">データの種類</span><span class="sxs-lookup"><span data-stu-id="6df4f-164">Data Types</span></span>](index.md)
- [<span data-ttu-id="6df4f-165">複合データ型</span><span class="sxs-lookup"><span data-stu-id="6df4f-165">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="6df4f-166">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="6df4f-166">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="6df4f-167">構造体</span><span class="sxs-lookup"><span data-stu-id="6df4f-167">Structures</span></span>](structures.md)
- [<span data-ttu-id="6df4f-168">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="6df4f-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="6df4f-169">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="6df4f-169">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="6df4f-170">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6df4f-170">Objects and Classes</span></span>](../objects-and-classes/index.md)

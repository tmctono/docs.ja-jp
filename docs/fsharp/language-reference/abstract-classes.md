---
title: 抽象クラス
description: 一部またはすべてのメンバーを実装しないままにして F# 抽象クラスをについて説明し、多様な種類のオブジェクトのセットの共通の機能を表します。
ms.date: 05/16/2016
ms.openlocfilehash: 8251d481c9056d40a0b13ae3c89353406986c116
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645541"
---
# <a name="abstract-classes"></a><span data-ttu-id="82bf9-103">抽象クラス</span><span class="sxs-lookup"><span data-stu-id="82bf9-103">Abstract Classes</span></span>

<span data-ttu-id="82bf9-104">*抽象クラス*は派生クラスによって実装を提供できるように実装されていません、一部またはすべてのメンバーのままにするクラス。</span><span class="sxs-lookup"><span data-stu-id="82bf9-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="82bf9-105">構文</span><span class="sxs-lookup"><span data-stu-id="82bf9-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="82bf9-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="82bf9-106">Remarks</span></span>

<span data-ttu-id="82bf9-107">オブジェクト指向プログラミングでは、抽象クラスは、階層の基本クラスとして使用され、オブジェクトの種類の多様な一連の共通機能を表します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="82bf9-108">「抽象」という名前からわかるように、抽象クラス多くの場合、対応していない問題ドメインの具体的なエンティティに直接します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="82bf9-109">ただし、どのような多くのさまざまな具体的なエンティティが共通を表すこれらの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="82bf9-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="82bf9-110">抽象クラスがあります、`AbstractClass`属性。</span><span class="sxs-lookup"><span data-stu-id="82bf9-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="82bf9-111">実装し、メンバーが実装されていませんができます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="82bf9-112">用語の使用*抽象*クラスは、他の .NET 言語と同様に適用するとただし、用語の使用*抽象*メソッド (およびプロパティ) に適用する場合からの F# で少し異なりますが、他の .NET 言語で使用します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="82bf9-113">F#でメソッドをマークすると、`abstract`キーワードでは、このことを示しますメンバーと呼ばれる、エントリ、*仮想ディスパッチ スロット*、その型の仮想関数の内部テーブルでします。</span><span class="sxs-lookup"><span data-stu-id="82bf9-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="82bf9-114">メソッドが仮想、つまり、ですが、`virtual`キーワードは、F# 言語では使用されません。</span><span class="sxs-lookup"><span data-stu-id="82bf9-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="82bf9-115">キーワード`abstract`メソッドを実装するかどうかに関係なく、仮想メソッドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="82bf9-116">仮想ディスパッチ スロットの宣言は、そのディスパッチ スロットのメソッドの定義とは別です。</span><span class="sxs-lookup"><span data-stu-id="82bf9-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="82bf9-117">そのため、抽象メソッドの宣言といずれかを別の定義の両方の組み合わせは、仮想メソッドの宣言と定義を別の .NET 言語での F# と同じ、`default`キーワードまたは`override`キーワード。</span><span class="sxs-lookup"><span data-stu-id="82bf9-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="82bf9-118">詳細と例については、次を参照してください。[メソッド](members/methods.md)します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="82bf9-119">クラスは、宣言が定義されていない抽象メソッドがある場合にのみ抽象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="82bf9-120">したがって、抽象メソッドを使用するクラスは、必ずしも抽象クラスではできません。</span><span class="sxs-lookup"><span data-stu-id="82bf9-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="82bf9-121">クラスが抽象メソッドを定義されていない場合は使用しないでください、 **AbstractClass**属性。</span><span class="sxs-lookup"><span data-stu-id="82bf9-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="82bf9-122">前の構文で*アクセシビリティ修飾子*できる`public`、`private`または`internal`します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="82bf9-123">詳細については、「[Access Control](access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bf9-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="82bf9-124">他の種類と同様、基底クラスと 1 つ以上のインターフェイスの基本抽象クラスことができます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="82bf9-125">と共に別々 の行に各基底クラスまたはインターフェイスが表示されます、`inherit`キーワード。</span><span class="sxs-lookup"><span data-stu-id="82bf9-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="82bf9-126">抽象クラスの型定義は、完全に定義されたメンバーを含めることができますが、抽象メンバーを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="82bf9-127">抽象メンバーの構文は、前の構文とは別に示しています。</span><span class="sxs-lookup"><span data-stu-id="82bf9-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="82bf9-128">この構文では、*型シグネチャ*のメンバーを含む一覧、パラメーターの順序と戻り値の型で型で区切られている`->`トークンや`*`カリー化を適切なトークンとタプルパラメーター。</span><span class="sxs-lookup"><span data-stu-id="82bf9-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="82bf9-129">抽象メンバー型のシグネチャの構文は、シグネチャ ファイルで使用して、Visual Studio コード エディターでの IntelliSense によって表示されるのと同じです。</span><span class="sxs-lookup"><span data-stu-id="82bf9-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="82bf9-130">次のコードでは、抽象クラスが 2 つ非抽象派生クラス、四角形や円の図形を示します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="82bf9-131">この例では、抽象クラス、メソッド、およびプロパティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="82bf9-132">例では、抽象クラスの図形は、具体的なエンティティの円、四角形の共通の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="82bf9-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="82bf9-133">(2 次元座標システム) のすべての図形の一般的な機能はアウト、Shape クラスに抽象化します。 グリッド、回転の角度と面積と周プロパティ上の位置。</span><span class="sxs-lookup"><span data-stu-id="82bf9-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="82bf9-134">これは、オーバーライドできます、位置、個々 の図形を変更できませんが、動作を除く。</span><span class="sxs-lookup"><span data-stu-id="82bf9-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="82bf9-135">インバリアントの回転は、その対称性のため、Circle クラスのように、回転メソッドをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="82bf9-136">ように、Circle クラスでは、回転メソッドは何も実行しないメソッドに置換されます。</span><span class="sxs-lookup"><span data-stu-id="82bf9-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="82bf9-137">**出力:**</span><span class="sxs-lookup"><span data-stu-id="82bf9-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="82bf9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="82bf9-138">See also</span></span>

- [<span data-ttu-id="82bf9-139">クラス</span><span class="sxs-lookup"><span data-stu-id="82bf9-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="82bf9-140">メンバー</span><span class="sxs-lookup"><span data-stu-id="82bf9-140">Members</span></span>](members/index.md)
- [<span data-ttu-id="82bf9-141">メソッド</span><span class="sxs-lookup"><span data-stu-id="82bf9-141">Methods</span></span>](members/methods.md)
- [<span data-ttu-id="82bf9-142">Properties</span><span class="sxs-lookup"><span data-stu-id="82bf9-142">Properties</span></span>](members/Properties.md)

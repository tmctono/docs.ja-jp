---
title: 抽象クラス
description: 一部またはすべてのメンバーを実装しないままにして F# 抽象クラスをについて説明し、多様な種類のオブジェクトのセットの共通の機能を表します。
ms.date: 05/16/2016
ms.openlocfilehash: d7fc87178cff7c5c824992c97198b49f87025f00
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082949"
---
# <a name="abstract-classes"></a><span data-ttu-id="9e1c5-103">抽象クラス</span><span class="sxs-lookup"><span data-stu-id="9e1c5-103">Abstract Classes</span></span>

<span data-ttu-id="9e1c5-104">*抽象クラス*は、一部またはすべてのメンバーを実装しないままにして、派生クラスによって実装を提供できるようにするクラスです。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e1c5-105">構文</span><span class="sxs-lookup"><span data-stu-id="9e1c5-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="9e1c5-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e1c5-106">Remarks</span></span>

<span data-ttu-id="9e1c5-107">オブジェクト指向プログラミングでは、抽象クラスが階層の基底クラスとして使用され、さまざまな種類のオブジェクトの共通機能を表します。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="9e1c5-108">"Abstract" という名前が示すとおり、多くの場合、抽象クラスは問題ドメインの具象エンティティに直接対応していません。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="9e1c5-109">ただし、共通のさまざまな具象エンティティの数を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="9e1c5-110">抽象クラスに`AbstractClass`は属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="9e1c5-111">実装および実装されていないメンバーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="9e1c5-112">用語の使用*抽象*クラスは、他の .NET 言語と同様に適用するとただし、用語の使用*抽象*メソッド (およびプロパティ) に適用する場合からの F# で少し異なりますが、他の .NET 言語で使用します。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="9e1c5-113">でF#は、メソッドが`abstract`キーワードでマークされている場合、その型の仮想関数の内部テーブルに、メンバーに*仮想ディスパッチスロット*と呼ばれるエントリがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="9e1c5-114">メソッドが仮想、つまり、ですが、`virtual`キーワードは、F# 言語では使用されません。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="9e1c5-115">キーワード`abstract`は、メソッドが実装されているかどうかに関係なく、仮想メソッドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="9e1c5-116">仮想ディスパッチスロットの宣言は、そのディスパッチスロットのメソッドの定義とは別のものです。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="9e1c5-117">そのため、抽象メソッドの宣言といずれかを別の定義の両方の組み合わせは、仮想メソッドの宣言と定義を別の .NET 言語での F# と同じ、`default`キーワードまたは`override`キーワード。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="9e1c5-118">詳細と例については、「[メソッド](./members/methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-118">For more information and examples, see [Methods](./members/methods.md).</span></span>

<span data-ttu-id="9e1c5-119">クラスは、宣言されているが定義されていない抽象メソッドがある場合にのみ、抽象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="9e1c5-120">したがって、抽象メソッドを持つクラスは、必ずしも抽象クラスではありません。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="9e1c5-121">クラスに未定義の抽象メソッドがある場合を除き、 **AbstractClass**属性は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="9e1c5-122">前の構文では、*アクセシビリティ-修飾子*に`public`は`private` 、 `internal`、またはを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="9e1c5-123">詳細については、「[Access Control](access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="9e1c5-124">他の型と同様に、抽象クラスは基底クラスと1つ以上の基本インターフェイスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="9e1c5-125">各基底クラスまたはインターフェイスは、 `inherit`キーワードと共に個別の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="9e1c5-126">抽象クラスの型定義には、完全に定義されたメンバーを含めることができますが、抽象メンバーを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="9e1c5-127">抽象メンバーの構文は、前の構文で個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="9e1c5-128">この構文では、メンバーの*型シグネチャ*は、列挙型と戻り値の型を含むリストであり、カリー化および`->`タプルのパラメーターに`*`は、トークンまたはトークンで区切られています。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="9e1c5-129">抽象メンバー型シグネチャの構文は、署名ファイルで使用される構文と、Visual Studio Code エディターで IntelliSense によって示されるシグネチャと同じです。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="9e1c5-130">次のコードは、抽象クラスの図形を示しています。抽象クラスには、2つの非抽象派生クラス (Square と Circle) があります。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="9e1c5-131">この例は、抽象クラス、メソッド、およびプロパティの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="9e1c5-132">この例では、抽象クラスのシェイプは、具象エンティティの circle と square の共通要素を表しています。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="9e1c5-133">(2 次元座標系内の) すべての図形の共通機能は、形状クラスに抽象化されます。これは、グリッド上の位置、回転角度、および領域と境界のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="9e1c5-134">これらは、位置、つまり個々の図形が変更できない動作を除き、オーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="9e1c5-135">回転メソッドは、対称軸クラスのようにオーバーライドできます。これは、対称によって回転が不変です。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="9e1c5-136">そのため、Circle クラスでは、ローテーションメソッドは何も実行しないメソッドに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="9e1c5-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="9e1c5-137">**出力:**</span><span class="sxs-lookup"><span data-stu-id="9e1c5-137">**Output:**</span></span>

```console
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="9e1c5-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e1c5-138">See also</span></span>

- [<span data-ttu-id="9e1c5-139">クラス</span><span class="sxs-lookup"><span data-stu-id="9e1c5-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="9e1c5-140">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e1c5-140">Members</span></span>](./members/index.md)
- [<span data-ttu-id="9e1c5-141">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e1c5-141">Methods</span></span>](./members/methods.md)
- [<span data-ttu-id="9e1c5-142">Properties</span><span class="sxs-lookup"><span data-stu-id="9e1c5-142">Properties</span></span>](./members/Properties.md)

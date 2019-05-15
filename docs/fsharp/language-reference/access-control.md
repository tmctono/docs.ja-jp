---
title: アクセス制御
description: 型、メソッド、および F# のプログラミング言語で、関数などのプログラミング要素へのアクセスを制御する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: a284d2fa4f98e444279276f58b70a15560537ca4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645609"
---
# <a name="access-control"></a><span data-ttu-id="15e63-103">アクセス制御</span><span class="sxs-lookup"><span data-stu-id="15e63-103">Access Control</span></span>

<span data-ttu-id="15e63-104">*アクセス制御*型、メソッド、および関数など、特定のプログラム要素を使用できるは、クライアントの宣言を参照します。</span><span class="sxs-lookup"><span data-stu-id="15e63-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="15e63-105">アクセス制御の基礎</span><span class="sxs-lookup"><span data-stu-id="15e63-105">Basics of Access Control</span></span>

<span data-ttu-id="15e63-106">F#、コントロールのアクセス指定子`public`、 `internal`、および`private`モジュール、型、メソッド、値の定義、関数、プロパティ、および明示的なフィールドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="15e63-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="15e63-107">`public` すべての呼び出し元によって、エンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="15e63-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="15e63-108">`internal` エンティティに同じアセンブリからのみアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="15e63-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="15e63-109">`private` エンティティを外側の型またはモジュールからのみアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="15e63-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="15e63-110">アクセス指定子`protected`をサポートしている言語で作成されたタイプを使用している場合は許容されるが、F# で使用されていない`protected`アクセスします。</span><span class="sxs-lookup"><span data-stu-id="15e63-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="15e63-111">そのため、保護されているメソッドをオーバーライドする場合、メソッドが、クラスとその子孫内でのみアクセス可能なします。</span><span class="sxs-lookup"><span data-stu-id="15e63-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="15e63-112">場合を除き、エンティティの名前の前に、指定子を配置する一般に、`mutable`または`inline`指定子を使用すると、コントロールのアクセス指定子の後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="15e63-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="15e63-113">アクセス指定子が使用されていない場合、既定値は`public`、除く`let`型では、常にバインド`private`型にします。</span><span class="sxs-lookup"><span data-stu-id="15e63-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="15e63-114">F# での署名は、F# プログラム要素へのアクセスを制御するための別のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="15e63-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="15e63-115">署名は、アクセス制御の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="15e63-115">Signatures are not required for access control.</span></span> <span data-ttu-id="15e63-116">詳細については、「[シグネチャ](signatures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e63-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="15e63-117">アクセス制御のルール</span><span class="sxs-lookup"><span data-stu-id="15e63-117">Rules for Access Control</span></span>

<span data-ttu-id="15e63-118">アクセス制御では、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="15e63-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="15e63-119">継承宣言 (の使用は、`inherit`クラスの基本クラスを指定する)、インターフェイスの宣言 (つまりを指定するクラスがインターフェイスを実装する) 場合は、および抽象メンバーが常に外側の型と同じのアクセシビリティを持ちます。</span><span class="sxs-lookup"><span data-stu-id="15e63-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="15e63-120">そのため、これらのコンストラクトでアクセス制御の指定子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="15e63-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="15e63-121">個々 の判別共用体ケースのユーザー補助機能は、弁別子付き共用体自体のアクセシビリティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="15e63-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="15e63-122">特定の共用体ケースは、共用体自体よりもそれはずばりアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="15e63-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="15e63-123">ユーザー補助のレコードの種類の個々 のフィールドのことはできませんが、レコード自体のアクセシビリティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="15e63-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="15e63-124">特定のレコードのラベルは、レコード自体よりもそれはずばりアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="15e63-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="15e63-125">例</span><span class="sxs-lookup"><span data-stu-id="15e63-125">Example</span></span>

<span data-ttu-id="15e63-126">次のコードでは、コントロールのアクセス指定子の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="15e63-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="15e63-127">プロジェクトで、2 つのファイルがある`Module1.fs`と`Module2.fs`します。</span><span class="sxs-lookup"><span data-stu-id="15e63-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="15e63-128">各ファイルは、暗黙的にモジュールです。</span><span class="sxs-lookup"><span data-stu-id="15e63-128">Each file is implicitly a module.</span></span> <span data-ttu-id="15e63-129">そのため、2 つのモジュールがある`Module1`と`Module2`します。</span><span class="sxs-lookup"><span data-stu-id="15e63-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="15e63-130">プライベート型と内部の型がで定義されている`Module1`します。</span><span class="sxs-lookup"><span data-stu-id="15e63-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="15e63-131">プライベート型からアクセスできない`Module2`が内部の型ができます。</span><span class="sxs-lookup"><span data-stu-id="15e63-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="15e63-132">次のコードで作成された型のアクセシビリティをテストする`Module1.fs`します。</span><span class="sxs-lookup"><span data-stu-id="15e63-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="15e63-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="15e63-133">See also</span></span>

- [<span data-ttu-id="15e63-134">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="15e63-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="15e63-135">シグネチャ</span><span class="sxs-lookup"><span data-stu-id="15e63-135">Signatures</span></span>](signatures.md)

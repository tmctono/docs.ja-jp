---
title: アクセス制御
description: 型、メソッド、および F# のプログラミング言語で、関数などのプログラミング要素へのアクセスを制御する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 38f8f3fd4114c0428fbe8baca71594cd07740b2c
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817858"
---
# <a name="access-control"></a><span data-ttu-id="6603a-103">アクセス制御</span><span class="sxs-lookup"><span data-stu-id="6603a-103">Access Control</span></span>

<span data-ttu-id="6603a-104">*アクセス制御*とは、型、メソッド、関数など、特定のプログラム要素を使用できるクライアントを宣言することを指します。</span><span class="sxs-lookup"><span data-stu-id="6603a-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="6603a-105">Access Control の基礎</span><span class="sxs-lookup"><span data-stu-id="6603a-105">Basics of Access Control</span></span>

<span data-ttu-id="6603a-106">でF#は、アクセス制御指定`public`子`internal`、、 `private`およびを、モジュール、型、メソッド、値の定義、関数、プロパティ、および明示的なフィールドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="6603a-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="6603a-107">`public`すべての呼び出し元がエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="6603a-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="6603a-108">`internal`エンティティが同じアセンブリからのみアクセス可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6603a-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="6603a-109">`private`外側の型またはモジュールからのみエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="6603a-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="6603a-110">アクセス指定子`protected`をサポートしている言語で作成されたタイプを使用している場合は許容されるが、F# で使用されていない`protected`アクセスします。</span><span class="sxs-lookup"><span data-stu-id="6603a-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="6603a-111">したがって、保護されたメソッドをオーバーライドすると、メソッドはクラスとその子孫内でのみアクセス可能な状態になります。</span><span class="sxs-lookup"><span data-stu-id="6603a-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="6603a-112">一般に、指定子は、 `mutable`または`inline`指定子が使用されている場合を除き、エンティティの名前の前に配置されます。これは、アクセス制御指定子の後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6603a-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="6603a-113">アクセス指定子が使用されていない`public`場合、既定`let`値はです。ただし、型の`private`バインディングは、常に型になります。</span><span class="sxs-lookup"><span data-stu-id="6603a-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="6603a-114">F# での署名は、F# プログラム要素へのアクセスを制御するための別のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="6603a-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="6603a-115">アクセス制御に署名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6603a-115">Signatures are not required for access control.</span></span> <span data-ttu-id="6603a-116">詳細については、「[シグネチャ](signatures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6603a-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="6603a-117">Access Control の規則</span><span class="sxs-lookup"><span data-stu-id="6603a-117">Rules for Access Control</span></span>

<span data-ttu-id="6603a-118">アクセス制御には、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6603a-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="6603a-119">継承宣言 (つまり、を使用`inherit`してクラスの基底クラスを指定)、インターフェイス宣言 (つまり、クラスがインターフェイスを実装することを指定)、抽象メンバーは、外側の型と同じアクセシビリティを常に持っています。</span><span class="sxs-lookup"><span data-stu-id="6603a-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="6603a-120">したがって、アクセス制御指定子は、これらのコンストラクトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6603a-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="6603a-121">判別共用体の個々のケースのアクセシビリティは、判別共用体自体のアクセシビリティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6603a-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="6603a-122">つまり、特定の共用体ケースは、共用体自体よりもアクセシビリティが低くなります。</span><span class="sxs-lookup"><span data-stu-id="6603a-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="6603a-123">レコード型の個々のフィールドのアクセシビリティは、レコード自体のアクセシビリティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6603a-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="6603a-124">つまり、特定のレコードラベルは、レコード自体よりもアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6603a-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="6603a-125">例</span><span class="sxs-lookup"><span data-stu-id="6603a-125">Example</span></span>

<span data-ttu-id="6603a-126">次のコードは、アクセス制御指定子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6603a-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="6603a-127">プロジェクトには、 `Module1.fs`と`Module2.fs`の2つのファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="6603a-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="6603a-128">各ファイルは暗黙的にモジュールです。</span><span class="sxs-lookup"><span data-stu-id="6603a-128">Each file is implicitly a module.</span></span> <span data-ttu-id="6603a-129">したがって、 `Module1`とと`Module2`いう2つのモジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="6603a-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="6603a-130">プライベート型と内部型はで`Module1`定義されています。</span><span class="sxs-lookup"><span data-stu-id="6603a-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="6603a-131">プライベート型にから`Module2`アクセスすることはできませんが、内部型はにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6603a-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="6603a-132">次のコードでは、で`Module1.fs`作成された型のアクセシビリティをテストします。</span><span class="sxs-lookup"><span data-stu-id="6603a-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="6603a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="6603a-133">See also</span></span>

- [<span data-ttu-id="6603a-134">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="6603a-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6603a-135">シグネチャ</span><span class="sxs-lookup"><span data-stu-id="6603a-135">Signatures</span></span>](signatures.md)

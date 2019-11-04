---
title: アクセス制御
description: F#プログラミング言語で、型、メソッド、関数などのプログラミング要素へのアクセスを制御する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425112"
---
# <a name="access-control"></a><span data-ttu-id="9eff6-103">アクセス制御</span><span class="sxs-lookup"><span data-stu-id="9eff6-103">Access Control</span></span>

<span data-ttu-id="9eff6-104">*アクセス制御*とは、型、メソッド、関数など、特定のプログラム要素を使用できるクライアントを宣言することを指します。</span><span class="sxs-lookup"><span data-stu-id="9eff6-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="9eff6-105">Access Control の基礎</span><span class="sxs-lookup"><span data-stu-id="9eff6-105">Basics of Access Control</span></span>

<span data-ttu-id="9eff6-106">でF#は、アクセス制御指定子 `public`、`internal`、および `private` をモジュール、型、メソッド、値定義、関数、プロパティ、および明示的なフィールドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="9eff6-107">`public` は、すべての呼び出し元がエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="9eff6-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="9eff6-108">`internal` は、同じアセンブリからエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="9eff6-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="9eff6-109">`private` は、外側の型またはモジュールからのみエンティティにアクセスできることを示します。</span><span class="sxs-lookup"><span data-stu-id="9eff6-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="9eff6-110">アクセス指定子 `protected` はでF#は使用されませんが、`protected` アクセスをサポートする言語で作成された型を使用している場合は許容されます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="9eff6-111">したがって、保護されたメソッドをオーバーライドすると、メソッドはクラスとその子孫内でのみアクセス可能な状態になります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="9eff6-112">一般に、指定子は、`mutable` または `inline` 指定子が使用されている場合を除き、エンティティの名前の前に配置されます。これは、アクセス制御指定子の後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="9eff6-113">アクセス指定子が使用されていない場合、既定値は `public`になります。ただし、型の `let` バインディングの場合は、常に型に `private` ます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="9eff6-114">のシグネチャF#には、プログラム要素へのF#アクセスを制御するための別のメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9eff6-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="9eff6-115">アクセス制御に署名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9eff6-115">Signatures are not required for access control.</span></span> <span data-ttu-id="9eff6-116">詳細については、「[シグネチャ](signature-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eff6-116">For more information, see [Signatures](signature-files.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="9eff6-117">Access Control の規則</span><span class="sxs-lookup"><span data-stu-id="9eff6-117">Rules for Access Control</span></span>

<span data-ttu-id="9eff6-118">アクセス制御には、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="9eff6-119">継承宣言 (つまり、クラスの基底クラスを指定するために `inherit` を使用する)、インターフェイス宣言 (つまり、クラスがインターフェイスを実装することを指定する) と、抽象メンバーは、外側の型と同じアクセシビリティを常に持っています。</span><span class="sxs-lookup"><span data-stu-id="9eff6-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="9eff6-120">したがって、アクセス制御指定子は、これらのコンストラクトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9eff6-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="9eff6-121">判別共用体の個々のケースのアクセシビリティは、判別共用体自体のアクセシビリティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="9eff6-122">つまり、特定の共用体ケースは、共用体自体よりもアクセシビリティが低くなります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="9eff6-123">レコード型の個々のフィールドのアクセシビリティは、レコード自体のアクセシビリティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="9eff6-124">つまり、特定のレコードラベルは、レコード自体よりもアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="9eff6-125">例</span><span class="sxs-lookup"><span data-stu-id="9eff6-125">Example</span></span>

<span data-ttu-id="9eff6-126">次のコードは、アクセス制御指定子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9eff6-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="9eff6-127">プロジェクトには、`Module1.fs` と `Module2.fs`の2つのファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="9eff6-128">各ファイルは暗黙的にモジュールです。</span><span class="sxs-lookup"><span data-stu-id="9eff6-128">Each file is implicitly a module.</span></span> <span data-ttu-id="9eff6-129">したがって、`Module1` と `Module2`の2つのモジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="9eff6-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="9eff6-130">プライベート型と内部型は `Module1`で定義されます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="9eff6-131">プライベート型に `Module2`からアクセスすることはできませんが、内部型ではアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9eff6-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="9eff6-132">次のコードは、`Module1.fs`で作成された型のアクセシビリティをテストします。</span><span class="sxs-lookup"><span data-stu-id="9eff6-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="9eff6-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eff6-133">See also</span></span>

- [<span data-ttu-id="9eff6-134">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="9eff6-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9eff6-135">シグネチャ</span><span class="sxs-lookup"><span data-stu-id="9eff6-135">Signatures</span></span>](signature-files.md)

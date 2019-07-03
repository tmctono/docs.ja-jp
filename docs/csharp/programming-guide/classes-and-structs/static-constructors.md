---
title: 静的コンストラクター - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: f053a74fcb87971506b83ca8ca2076517ddddf56
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307105"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="4ee20-102">静的コンストラクター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4ee20-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="4ee20-103">静的コンストラクターは、任意の [static](../../../csharp/language-reference/keywords/static.md) データを初期化するため、または 1 回だけ実行する必要がある特定のアクションを実行するために使います。</span><span class="sxs-lookup"><span data-stu-id="4ee20-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="4ee20-104">最初のインスタンスが作成され前、または静的メンバーが参照される前に、自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
 
## <a name="remarks"></a><span data-ttu-id="4ee20-105">解説</span><span class="sxs-lookup"><span data-stu-id="4ee20-105">Remarks</span></span>
<span data-ttu-id="4ee20-106">静的コンストラクターには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-106">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="4ee20-107">静的コンストラクターはアクセス修飾子を取らず、パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="4ee20-107">A static constructor does not take access modifiers or have parameters.</span></span>  

- <span data-ttu-id="4ee20-108">クラスまたは構造体は、静的コンストラクターを 1 つだけ持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-108">A class or struct can only have one static constructor.</span></span>

- <span data-ttu-id="4ee20-109">静的コンストラクターを継承またはオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ee20-109">Static constructors cannot be inherited or overloaded.</span></span>

- <span data-ttu-id="4ee20-110">静的コンストラクターは、直接呼び出すことはできず、共通言語ランタイム (CLR) によって呼び出されることだけが意図されています。</span><span class="sxs-lookup"><span data-stu-id="4ee20-110">A static constructor cannot be called directly and is only meant to be called by the common language runtime (CLR).</span></span> <span data-ttu-id="4ee20-111">自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-111">It is invoked automatically.</span></span>

- <span data-ttu-id="4ee20-112">ユーザーは、プログラムで静的コンストラクターが実行されるタイミングを制御できません。</span><span class="sxs-lookup"><span data-stu-id="4ee20-112">The user has no control on when the static constructor is executed in the program.</span></span>
  
- <span data-ttu-id="4ee20-113">静的コンストラクターは、最初のインスタンスが作成され前、または静的メンバーが参照される前に、[クラス](../../../csharp/language-reference/keywords/class.md)を初期化するために自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-113">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="4ee20-114">静的コンストラクターは、インスタンス コンストラクターの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-114">A static constructor will run before an instance constructor.</span></span> <span data-ttu-id="4ee20-115">イベントまたはデリゲートに割り当てられている静的メソッドが呼び出されるときは型の静的コンストラクターが呼び出されますが、割り当てられるときは呼び出されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4ee20-115">Note that a type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span> <span data-ttu-id="4ee20-116">静的フィールド変数初期化子が静的コンストラクターのクラスに存在する場合、初期化子は、静的コンストラクターの実行の直前に、クラス宣言に出現するテキストの順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-116">If static field variable initializers are present in the class of the static constructor, they will be executed in the textual order in which they appear in the class declaration immediately prior to the execution of the static constructor.</span></span>

- <span data-ttu-id="4ee20-117">静的フィールドを初期化するための静的コンストラクターを提供しないと、すべての静的フィールドは、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」で示されている既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-117">If you don't provide a static constructor to initialize static fields, all static fields are initialized to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 
  
- <span data-ttu-id="4ee20-118">静的コンストラクターが例外をスローした場合、ランタイムがその静的コンストラクターを再度呼び出すことはなく、その型は、プログラムが実行しているアプリケーション ドメインの有効期間中、初期化されないままになります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-118">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span> <span data-ttu-id="4ee20-119">ほとんどの場合、静的コンストラクターで型をインスタンス化できないとき、または静的コンストラクター内でハンドルされない例外が発生したときは、<xref:System.TypeInitializationException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-119">Most commonly, a <xref:System.TypeInitializationException> exception is thrown when a static constructor is unable to instantiate a type or for an unhandled exception occurring within a static constructor.</span></span> <span data-ttu-id="4ee20-120">ソース コードで明示的に定義されていない暗黙的な静的コンストラクターでは、トラブルシューティングの際に中間言語 (IL) のコードを調べることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-120">For implicit static constructors that are not explicitly defined in source code, troubleshooting may require inspection of the intermediate language (IL) code.</span></span>

- <span data-ttu-id="4ee20-121">静的コンストラクターが存在すると、<xref:System.Reflection.TypeAttributes.BeforeFieldInit> 型属性を追加できません。</span><span class="sxs-lookup"><span data-stu-id="4ee20-121">The presence of a static constructor prevents the addition of the <xref:System.Reflection.TypeAttributes.BeforeFieldInit> type attribute.</span></span> <span data-ttu-id="4ee20-122">これにより、ランタイムの最適化が制限されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-122">This limits runtime optimization.</span></span>

- <span data-ttu-id="4ee20-123">`static readonly` として宣言されているフィールドは、その宣言の一部として、または静的コンストラクター内でのみ、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-123">A field declared as `static readonly` may only be assigned as part of its declaration or in a static constructor.</span></span> <span data-ttu-id="4ee20-124">明示的な静的コンストラクターが必要ない場合は、ランタイムのより適切な最適化のため、静的コンストラクターではなく、宣言時に静的フィールドを初期化します。</span><span class="sxs-lookup"><span data-stu-id="4ee20-124">When an explicit static constructor is not required, initialize static fields at declaration, rather than through a static constructor for better runtime optimization.</span></span>

> [!Note]
> <span data-ttu-id="4ee20-125">直接アクセスすることはできませんが、初期化の例外のトラブルシューティングを助けるため、明示的な静的コンストラクターが存在することを文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-125">Though not directly accessible, the presence of an explicit static constructor should be documented to assist with troubleshooting initialization exceptions.</span></span>

### <a name="usage"></a><span data-ttu-id="4ee20-126">使用法</span><span class="sxs-lookup"><span data-stu-id="4ee20-126">Usage</span></span>

- <span data-ttu-id="4ee20-127">静的コンストラクターの一般的な用途は、クラスがログ ファイルを使っていて、このファイルにエントリを書き込むためにコンストラクターが使われる場合です。</span><span class="sxs-lookup"><span data-stu-id="4ee20-127">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
- <span data-ttu-id="4ee20-128">コンストラクターが `LoadLibrary` メソッドを呼び出すことができる場合は、アンマネージ コードのラッパー クラスを作成するときにも静的コンストラクターが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-128">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  

- <span data-ttu-id="4ee20-129">静的コンストラクターは、制約 (型パラメーターの制約) によりコンパイル時にチェックできない型パラメーターに対して、実行時にチェックを強制するのに適した場所でもあります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-129">Static constructors are also a convenient place to enforce run-time checks on the type parameter that cannot be checked at compile-time via constraints (Type parameter constraints).</span></span>

## <a name="example"></a><span data-ttu-id="4ee20-130">例</span><span class="sxs-lookup"><span data-stu-id="4ee20-130">Example</span></span>
 <span data-ttu-id="4ee20-131">この例では、`Bus` クラスに静的コンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-131">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="4ee20-132">`Bus` の最初のインスタンスが作成されるとき (`bus1`)、静的コンストラクターが呼び出されてクラスが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="4ee20-132">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="4ee20-133">サンプルの出力では、`Bus` のインスタンスが 2 つでも静的コンストラクターは 1 回だけ実行されること、およびインスタンス コンストラクターの実行前に静的コンストラクターが実行されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="4ee20-133">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]
 
## <a name="c-language-specification"></a><span data-ttu-id="4ee20-134">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4ee20-134">C# language specification</span></span>
<span data-ttu-id="4ee20-135">詳しくは、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[Static constructors (静的コンストラクター)](~/_csharplang/spec/classes.md#static-constructors)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ee20-135">For more information, see the [Static constructors](~/_csharplang/spec/classes.md#static-constructors) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ee20-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ee20-136">See also</span></span>

- [<span data-ttu-id="4ee20-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4ee20-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4ee20-138">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="4ee20-138">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="4ee20-139">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="4ee20-139">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="4ee20-140">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="4ee20-140">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="4ee20-141">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="4ee20-141">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="4ee20-142">コンストラクターのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="4ee20-142">Constructor Design Guidelines</span></span>](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [<span data-ttu-id="4ee20-143">セキュリティの警告 - CA2121: 静的コンストラクターはプライベートでなければなりません</span><span class="sxs-lookup"><span data-stu-id="4ee20-143">Security Warning - CA2121: Static constructors should be private</span></span>](https://docs.microsoft.com/en-us/visualstudio/code-quality/ca2121-static-constructors-should-be-private)

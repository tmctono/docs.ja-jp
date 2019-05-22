---
title: 静的コンストラクター - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 110d83caad0c588fa899a4129897784e9c74aab8
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881911"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="e2db0-102">静的コンストラクター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e2db0-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="e2db0-103">静的コンストラクターは、任意の [static](../../../csharp/language-reference/keywords/static.md) データを初期化するため、または 1 回だけ実行する必要がある特定のアクションを実行するために使います。</span><span class="sxs-lookup"><span data-stu-id="e2db0-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="e2db0-104">最初のインスタンスが作成され前、または静的メンバーが参照される前に、自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2db0-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="e2db0-105">静的コンストラクターには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="e2db0-105">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="e2db0-106">静的コンストラクターはアクセス修飾子を取らず、パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="e2db0-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
- <span data-ttu-id="e2db0-107">静的コンストラクターは、最初のインスタンスが作成され前、または静的メンバーが参照される前に、[クラス](../../../csharp/language-reference/keywords/class.md)を初期化するために自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2db0-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="e2db0-108">イベントまたはデリゲートに割り当てられている静的メソッドが呼び出されるときは型の静的コンストラクターが呼び出されますが、割り当てられるときは呼び出されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e2db0-108">Note that a type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span>
  
- <span data-ttu-id="e2db0-109">静的コンストラクターを直接呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e2db0-109">A static constructor cannot be called directly.</span></span>  
  
- <span data-ttu-id="e2db0-110">ユーザーは、プログラムで静的コンストラクターが実行されるタイミングを制御できません。</span><span class="sxs-lookup"><span data-stu-id="e2db0-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
- <span data-ttu-id="e2db0-111">静的コンストラクターの一般的な用途は、クラスがログ ファイルを使っていて、このファイルにエントリを書き込むためにコンストラクターが使われる場合です。</span><span class="sxs-lookup"><span data-stu-id="e2db0-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
- <span data-ttu-id="e2db0-112">コンストラクターが `LoadLibrary` メソッドを呼び出すことができる場合は、アンマネージ コードのラッパー クラスを作成するときにも静的コンストラクターが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2db0-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
- <span data-ttu-id="e2db0-113">静的コンストラクターが例外をスローした場合、ランタイムがその静的コンストラクターを再度呼び出すことはなく、その型は、プログラムが実行しているアプリケーション ドメインの有効期間中、初期化されないままになります。</span><span class="sxs-lookup"><span data-stu-id="e2db0-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2db0-114">例</span><span class="sxs-lookup"><span data-stu-id="e2db0-114">Example</span></span>  
 <span data-ttu-id="e2db0-115">この例では、`Bus` クラスに静的コンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="e2db0-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="e2db0-116">`Bus` の最初のインスタンスが作成されるとき (`bus1`)、静的コンストラクターが呼び出されてクラスが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e2db0-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="e2db0-117">サンプルの出力では、`Bus` のインスタンスが 2 つでも静的コンストラクターは 1 回だけ実行されること、およびインスタンス コンストラクターの実行前に静的コンストラクターが実行されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e2db0-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="e2db0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2db0-118">See also</span></span>

- [<span data-ttu-id="e2db0-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e2db0-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e2db0-120">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="e2db0-120">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="e2db0-121">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="e2db0-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="e2db0-122">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="e2db0-122">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="e2db0-123">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="e2db0-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

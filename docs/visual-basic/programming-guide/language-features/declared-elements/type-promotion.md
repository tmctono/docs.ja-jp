---
title: 型の上位変換 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 02d53770186f7600b190231dc73938ff1589cef6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610358"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="14e54-102">型の上位変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14e54-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="14e54-103">モジュール内のプログラミング要素を宣言するときに、Visual Basic は、モジュールを含む名前空間には、そのスコープを昇格します。</span><span class="sxs-lookup"><span data-stu-id="14e54-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="14e54-104">これと呼ばれます*の上位変換*します。</span><span class="sxs-lookup"><span data-stu-id="14e54-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="14e54-105">次の例では、モジュールのスケルトン定義し、そのモジュールの 2 つのメンバーを示します。</span><span class="sxs-lookup"><span data-stu-id="14e54-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="14e54-106">内で`projModule`プログラミング、モジュール レベルで宣言された要素に昇格`projNamespace`します。</span><span class="sxs-lookup"><span data-stu-id="14e54-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="14e54-107">前の例では、`basicEnum`と`innerClass`昇格されますが、`numberSub`モジュール レベルで宣言されていないためは。</span><span class="sxs-lookup"><span data-stu-id="14e54-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="14e54-108">型の上位変換の効果</span><span class="sxs-lookup"><span data-stu-id="14e54-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="14e54-109">型の上位変換の効果は、修飾文字列が、モジュール名を含める必要がないことです。</span><span class="sxs-lookup"><span data-stu-id="14e54-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="14e54-110">次の例では、前の例では、プロシージャに 2 つの呼び出しをでいます。</span><span class="sxs-lookup"><span data-stu-id="14e54-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 <span data-ttu-id="14e54-111">前の例では、最初の呼び出しは、完全修飾文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="14e54-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="14e54-112">ただし、これは必要ありません型の上位変換のためです。</span><span class="sxs-lookup"><span data-stu-id="14e54-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="14e54-113">2 番目の呼び出しもアクセス モジュールのメンバーを含めずに`projModule`修飾文字列にします。</span><span class="sxs-lookup"><span data-stu-id="14e54-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="14e54-114">型の上位変換の無効化</span><span class="sxs-lookup"><span data-stu-id="14e54-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="14e54-115">名前空間には、既にモジュール メンバーと同じ名前のメンバーが、型の上位変換は、モジュール メンバーの無効化します。</span><span class="sxs-lookup"><span data-stu-id="14e54-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="14e54-116">次の例では、列挙体と同じ名前空間内のモジュールのスケルトン定義を示します。</span><span class="sxs-lookup"><span data-stu-id="14e54-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 <span data-ttu-id="14e54-117">Visual Basic では、前の例では、クラスに昇格できません`abc`に`thisNameSpace`名前空間レベルで同じ名前の列挙型が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="14e54-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="14e54-118">アクセスする`abcSub`、完全修飾文字列を使用する必要があります`thisNamespace.thisModule.abc.abcSub`します。</span><span class="sxs-lookup"><span data-stu-id="14e54-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="14e54-119">ただし、クラス`xyz`はまだ昇格し、アクセスできる`xyzSub`短い修飾文字列`thisNamespace.xyz.xyzSub`します。</span><span class="sxs-lookup"><span data-stu-id="14e54-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="14e54-120">部分型の型の上位変換の無効化</span><span class="sxs-lookup"><span data-stu-id="14e54-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="14e54-121">クラスまたはモジュール内の構造体を使用している場合、[部分](../../../../visual-basic/language-reference/modifiers/partial.md)キーワード、型の上位変換は自動的に失敗のクラスまたは構造体、名前空間には、同じ名前のメンバーであるかどうか。</span><span class="sxs-lookup"><span data-stu-id="14e54-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="14e54-122">モジュールの他の要素は、型の上位変換も対象です。</span><span class="sxs-lookup"><span data-stu-id="14e54-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="14e54-123">**結果。**</span><span class="sxs-lookup"><span data-stu-id="14e54-123">**Consequences.**</span></span> <span data-ttu-id="14e54-124">部分定義の型の上位変換の無効化には、予期しない結果とコンパイラ エラーも可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14e54-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="14e54-125">次の例では、モジュール内では、クラスのスケルトンの部分的な定義を示します。</span><span class="sxs-lookup"><span data-stu-id="14e54-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 <span data-ttu-id="14e54-126">前の例では、開発者は、コンパイラの 2 つの部分定義をマージする`sampleClass`します。</span><span class="sxs-lookup"><span data-stu-id="14e54-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="14e54-127">ただし、コンパイラが部分定義内での昇格を考慮しない`sampleModule`します。</span><span class="sxs-lookup"><span data-stu-id="14e54-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="14e54-128">2 つの個別のクラスをコンパイルしようという名前をその結果、`sampleClass`がさまざまな認定パス。</span><span class="sxs-lookup"><span data-stu-id="14e54-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="14e54-129">コンパイラは、完全修飾されたパスがまったく同じ場合にのみ、部分定義をマージします。</span><span class="sxs-lookup"><span data-stu-id="14e54-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="14e54-130">推奨事項</span><span class="sxs-lookup"><span data-stu-id="14e54-130">Recommendations</span></span>  
 <span data-ttu-id="14e54-131">次の推奨事項は、適切なプログラミング手法を表します。</span><span class="sxs-lookup"><span data-stu-id="14e54-131">The following recommendations represent good programming practice.</span></span>  
  
- <span data-ttu-id="14e54-132">**一意の名前。**</span><span class="sxs-lookup"><span data-stu-id="14e54-132">**Unique Names.**</span></span> <span data-ttu-id="14e54-133">プログラミング要素の名前付けに対するフル コントロールがある場合は常には一意の名前をすべての場所で使用します。</span><span class="sxs-lookup"><span data-stu-id="14e54-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="14e54-134">同じ名前では、余分な認定を必要し、によって、コードが読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="14e54-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="14e54-135">微妙なエラーと予期しない結果になることができますも。</span><span class="sxs-lookup"><span data-stu-id="14e54-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
- <span data-ttu-id="14e54-136">**完全に修飾します。**</span><span class="sxs-lookup"><span data-stu-id="14e54-136">**Full Qualification.**</span></span> <span data-ttu-id="14e54-137">モジュールと同じ名前空間の他の要素を使用して、最も安全なアプローチは常にすべてのプログラミング要素の完全修飾を使用するがします。</span><span class="sxs-lookup"><span data-stu-id="14e54-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="14e54-138">型の上位変換は、モジュール メンバーの無効化、そのメンバーを完全修飾しない場合は、誤って別のプログラミング要素にアクセスするでした。</span><span class="sxs-lookup"><span data-stu-id="14e54-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e54-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e54-139">See also</span></span>

- [<span data-ttu-id="14e54-140">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="14e54-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="14e54-141">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="14e54-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="14e54-142">Partial</span><span class="sxs-lookup"><span data-stu-id="14e54-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="14e54-143">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="14e54-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="14e54-144">方法: コントロール変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="14e54-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="14e54-145">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="14e54-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

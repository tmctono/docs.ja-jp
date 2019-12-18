---
title: 型の上位変換
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
ms.openlocfilehash: aa05bd7dc87510aedb0facadf4b7590c8ec57d1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345271"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="a162b-102">型の上位変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a162b-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="a162b-103">モジュールでプログラミング要素を宣言すると、Visual Basic はそのスコープをモジュールを含む名前空間に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="a162b-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="a162b-104">これは、*型の上位変換*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a162b-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="a162b-105">次の例は、モジュールのスケルトン定義とそのモジュールの2つのメンバーを示しています。</span><span class="sxs-lookup"><span data-stu-id="a162b-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="a162b-106">`projModule`内では、モジュールレベルで宣言されたプログラミング要素が `projNamespace`に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="a162b-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="a162b-107">前の例では、`basicEnum` と `innerClass` は昇格されますが、`numberSub` はありません。これは、モジュールレベルで宣言されていないためです。</span><span class="sxs-lookup"><span data-stu-id="a162b-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="a162b-108">型の上位変換の効果</span><span class="sxs-lookup"><span data-stu-id="a162b-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="a162b-109">型の上位変換の効果は、修飾文字列にモジュール名を含める必要がないことです。</span><span class="sxs-lookup"><span data-stu-id="a162b-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="a162b-110">次の例では、前の例のプロシージャを2回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a162b-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a162b-111">前の例では、最初の呼び出しで完全修飾文字列を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a162b-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="a162b-112">ただし、型の上位変換のためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a162b-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="a162b-113">2番目の呼び出しは、修飾文字列に `projModule` を含めずに、モジュールのメンバーにもアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a162b-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="a162b-114">型の上位変換の無効化</span><span class="sxs-lookup"><span data-stu-id="a162b-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="a162b-115">名前空間にモジュールメンバーと同じ名前のメンバーが既に存在する場合、そのモジュールメンバーに対して型の上位変換は使用されません。</span><span class="sxs-lookup"><span data-stu-id="a162b-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="a162b-116">次の例は、同じ名前空間内の列挙型とモジュールのスケルトン定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="a162b-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 <span data-ttu-id="a162b-117">前の例では、名前空間レベルで同じ名前の列挙が既に存在するため、Visual Basic はクラス `abc` を `thisNameSpace` に昇格できません。</span><span class="sxs-lookup"><span data-stu-id="a162b-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="a162b-118">`abcSub`にアクセスするには、完全修飾文字列 `thisNamespace.thisModule.abc.abcSub`を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a162b-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="a162b-119">ただし、クラス `xyz` は引き続き昇格され、`xyzSub` には、短い修飾文字列 `thisNamespace.xyz.xyzSub`を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a162b-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="a162b-120">部分型の型の上位変換の無効化</span><span class="sxs-lookup"><span data-stu-id="a162b-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="a162b-121">モジュール内のクラスまたは構造体が[Partial](../../../../visual-basic/language-reference/modifiers/partial.md)キーワードを使用している場合は、そのクラスまたは構造体に対して型の昇格が自動的に無効になります。名前空間に同じ名前のメンバーが含まれているかどうかは異なります。</span><span class="sxs-lookup"><span data-stu-id="a162b-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="a162b-122">モジュール内の他の要素は、引き続き型の上位変換の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a162b-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="a162b-123">**措置.**</span><span class="sxs-lookup"><span data-stu-id="a162b-123">**Consequences.**</span></span> <span data-ttu-id="a162b-124">部分定義の型の上位変換を無効にすると、予期しない結果が発生し、コンパイラエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a162b-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="a162b-125">次の例は、クラスのスケルトン部分定義を示しています。そのうちの1つがモジュール内にあります。</span><span class="sxs-lookup"><span data-stu-id="a162b-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a162b-126">前の例では、開発者は、`sampleClass`の2つの部分定義をマージすることをコンパイラに要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a162b-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="a162b-127">ただし、コンパイラは `sampleModule`内の部分定義の上位変換を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="a162b-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="a162b-128">結果として、2つの個別のクラスと別個のクラスをコンパイルしようとします。このクラスには `sampleClass` 名前が付けられますが、修飾パスは異なります。</span><span class="sxs-lookup"><span data-stu-id="a162b-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="a162b-129">コンパイラは、完全修飾されたパスがまったく同じ場合にのみ、部分定義をマージします。</span><span class="sxs-lookup"><span data-stu-id="a162b-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="a162b-130">推奨事項</span><span class="sxs-lookup"><span data-stu-id="a162b-130">Recommendations</span></span>  
 <span data-ttu-id="a162b-131">次の推奨事項は、適切なプログラミング手法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a162b-131">The following recommendations represent good programming practice.</span></span>  
  
- <span data-ttu-id="a162b-132">**一意の名前。**</span><span class="sxs-lookup"><span data-stu-id="a162b-132">**Unique Names.**</span></span> <span data-ttu-id="a162b-133">プログラミング要素の名前付けを完全に制御できる場合は、常に一意の名前を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a162b-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="a162b-134">同一の名前には追加の修飾が必要であり、コードが読みにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a162b-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="a162b-135">また、軽度のエラーや予期しない結果につながる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="a162b-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
- <span data-ttu-id="a162b-136">**完全修飾。**</span><span class="sxs-lookup"><span data-stu-id="a162b-136">**Full Qualification.**</span></span> <span data-ttu-id="a162b-137">同じ名前空間内のモジュールとその他の要素を使用する場合、最も安全な方法は、すべてのプログラミング要素に対して常に完全修飾を使用することです。</span><span class="sxs-lookup"><span data-stu-id="a162b-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="a162b-138">モジュールメンバーの型の上位変換が無効になっていて、そのメンバーを完全に修飾していない場合、誤って別のプログラミング要素にアクセスする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a162b-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a162b-139">参照</span><span class="sxs-lookup"><span data-stu-id="a162b-139">See also</span></span>

- [<span data-ttu-id="a162b-140">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="a162b-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="a162b-141">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="a162b-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="a162b-142">Partial</span><span class="sxs-lookup"><span data-stu-id="a162b-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="a162b-143">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="a162b-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="a162b-144">方法: 変数のスコープを制御する</span><span class="sxs-lookup"><span data-stu-id="a162b-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="a162b-145">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="a162b-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

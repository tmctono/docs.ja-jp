---
title: out パラメーター修飾子 - C# リファレンス
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 57308992268e1285cfeb82b28e2abf213e7a831b
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805857"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="e3646-102">out パラメーター修飾子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e3646-102">out parameter modifier (C# Reference)</span></span>

<span data-ttu-id="e3646-103">`out` キーワードによって、参照により引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="e3646-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="e3646-104">仮パラメーターを引数 (変数にする必要があります) の別名にします。</span><span class="sxs-lookup"><span data-stu-id="e3646-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="e3646-105">つまり、パラメーターに対するすべての操作は引数に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="e3646-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="e3646-106">これは、[ref](ref.md) キーワードと似ていますが、`ref` では、変数を初期化してから渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3646-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="e3646-107">[in](in-parameter-modifier.md) キーワードとも似ていますが、`in` では、呼び出されたメソッドで引数の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="e3646-108">`out` パラメーターを使用するには、メソッド定義と呼び出し元のメソッドの両方で `out` キーワードを明示的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3646-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="e3646-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e3646-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="e3646-110">`out` キーワードは、ジェネリック型パラメーターと共に使用すると、型パラメーターが共変であることを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3646-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="e3646-111">このコンテキストでの `out` キーワードの使用方法の詳細については、「[out (ジェネリック修飾子)](out-generic-modifier.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3646-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="e3646-112">`out` の引数として渡される変数は、メソッド呼び出しで渡される前に初期化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3646-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="e3646-113">ただし、呼び出されたメソッドでは、メソッドから制御が返される前に値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3646-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="e3646-114">`in`、`ref`、および `out` キーワードは、オーバーロード解決のためのメソッド シグネチャの一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="e3646-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="e3646-115">したがって、唯一の違いが、1 つのメソッドは `ref` または `in` 引数を受け取り、もう一方のメソッドは `out` 引数を受け取ることである場合、メソッドはオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="e3646-116">たとえば、次のコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="e3646-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="e3646-117">ただし、一方のメソッドが `ref`、`in`、または `out` 引数を受け取り、もう一方のメソッドにいずれの修飾子もない場合は、オーバーロードを実行できます。この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3646-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="e3646-118">コンパイラは、呼び出しサイトのパラメーター修飾子と、メソッド呼び出しで使用されるパラメーター修飾子を照合して、最適なオーバーロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3646-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="e3646-119">プロパティは変数ではないため、`out` パラメーターとして渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="e3646-120">次の種類のメソッドには、`in`、`ref`、`out` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="e3646-121">[async](./async.md) 修飾子を使用して定義した Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="e3646-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="e3646-122">[yield return](./yield.md) または `yield break` ステートメントを含む Iterator メソッド。</span><span class="sxs-lookup"><span data-stu-id="e3646-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="e3646-123">さらに、[拡張メソッド](../../programming-guide/classes-and-structs/extension-methods.md)には次の制約があります。</span><span class="sxs-lookup"><span data-stu-id="e3646-123">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="e3646-124">拡張メソッドの最初の引数では、`out` キーワードを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3646-124">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="e3646-125">拡張メソッドの最初の引数が構造体ではない場合、または構造体として制約されていないジェネリック型である場合、その引数で `ref` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-125">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="e3646-126">最初の引数が構造体である場合を除き、`in` キーワードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3646-126">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="e3646-127">ジェネリック型では、構造体として制約されている場合であっても、`in` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3646-127">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="declaring-out-parameters"></a><span data-ttu-id="e3646-128">`out` パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="e3646-128">Declaring `out` parameters</span></span>

<span data-ttu-id="e3646-129">`out` 引数を含むメソッドの宣言は、複数の値を返すための従来の回避策です。</span><span class="sxs-lookup"><span data-stu-id="e3646-129">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="e3646-130">C#7.0 以降、同様のシナリオでは[タプル](../../tuples.md)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e3646-130">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="e3646-131">次の例では `out` を使用して、1 つのメソッド呼び出しで 3 つの変数を返します。</span><span class="sxs-lookup"><span data-stu-id="e3646-131">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="e3646-132">3 番目の引数が null に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e3646-132">The third argument is assigned to null.</span></span> <span data-ttu-id="e3646-133">これにより、必要に応じてメソッドが値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e3646-133">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="e3646-134">`out` 引数を含むメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="e3646-134">Calling a method with an `out` argument</span></span>

<span data-ttu-id="e3646-135">C# 6 以前では、変数を別のステートメントで宣言してから `out` 引数として渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3646-135">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="e3646-136">次の例では、`number` という名前の変数を宣言してから、文字列を数値に変換する [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) メソッドに渡しています。</span><span class="sxs-lookup"><span data-stu-id="e3646-136">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="e3646-137">C# 7.0 以降では、`out` 変数を、別の変数宣言内ではなく、メソッド呼び出しの引数リスト内で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e3646-137">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="e3646-138">これにより、よりコンパクトで読みやすいコードが生成されます。また、メソッド呼び出しの前に誤って変数に値を割り当てることもなくなります。</span><span class="sxs-lookup"><span data-stu-id="e3646-138">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="e3646-139">次の例は前の例と似ていますが、[Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) メソッドの呼び出しで `number` 変数を定義している点が異なります。</span><span class="sxs-lookup"><span data-stu-id="e3646-139">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="e3646-140">前の例では、`number` 変数は `int` として厳密に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="e3646-140">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="e3646-141">次の例のように、暗黙的に型指定されたローカル変数を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3646-141">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="e3646-142">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e3646-142">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3646-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3646-143">See also</span></span>

- [<span data-ttu-id="e3646-144">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e3646-144">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3646-145">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e3646-145">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e3646-146">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="e3646-146">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="e3646-147">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3646-147">Method Parameters</span></span>](./method-parameters.md)

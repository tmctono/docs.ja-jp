---
title: パラメーターのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 5a0f6e0fab5d0f2fe8574e348fc6b8ae726eeb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757405"
---
# <a name="parameter-design"></a><span data-ttu-id="5a296-102">パラメーターのデザイン</span><span class="sxs-lookup"><span data-stu-id="5a296-102">Parameter Design</span></span>
<span data-ttu-id="5a296-103">このセクションでは、引数をチェックするためのガイドラインにセクションを含むパラメーターのデザインの大まかなガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a296-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="5a296-104">さらで説明されているガイドラインを参照する必要があります[パラメーターの名前付け](../../../docs/standard/design-guidelines/naming-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="5a296-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="5a296-105">**✓ DO** メンバーで必要な機能を提供する少なくとも派生パラメーター型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="5a296-106">たとえば、コレクションを列挙し、コンソールには、各項目を印刷する方法を設計する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="5a296-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="5a296-107">このようなメソッドが受け取る必要があります<xref:System.Collections.IEnumerable>、パラメーターとしていない<xref:System.Collections.ArrayList>または<xref:System.Collections.IList>など。</span><span class="sxs-lookup"><span data-stu-id="5a296-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="5a296-108">**X DO NOT** 予約済みのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="5a296-109">メンバーへの複数の入力は、将来のバージョンで必要な場合は、新しいオーバー ロードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5a296-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="5a296-110">**X DO NOT** ポインター、ポインターの配列または多次元配列をパラメーターとして受け取るメソッドがパブリックに公開します。</span><span class="sxs-lookup"><span data-stu-id="5a296-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="5a296-111">ポインターと多次元配列が正しく使用する比較的困難です。</span><span class="sxs-lookup"><span data-stu-id="5a296-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="5a296-112">ほとんどの場合、Api をパラメーターとしてこれらの型を防ぐために再設計できます。</span><span class="sxs-lookup"><span data-stu-id="5a296-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="5a296-113">**✓ DO** すべて配置`out`で値をすべてのパラメーターと`ref`パラメーター (除外パラメーター配列) のパラメーターの順序のオーバー ロード間の不整合が発生する場合でも (を参照してください[メンバーオーバー ロード](../../../docs/standard/design-guidelines/member-overloading.md))。</span><span class="sxs-lookup"><span data-stu-id="5a296-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="5a296-114">`out`パラメーターは、余分な戻り値として見なすことができ、理解しやすく、メソッドのシグネチャは、グループ化することです。</span><span class="sxs-lookup"><span data-stu-id="5a296-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="5a296-115">**✓ DO** メンバーをオーバーライドするときに名前のパラメーターまたはインターフェイス メンバーの実装で一貫しています。</span><span class="sxs-lookup"><span data-stu-id="5a296-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="5a296-116">これには、メソッド間の関係向上と通信します。</span><span class="sxs-lookup"><span data-stu-id="5a296-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="5a296-117">列挙型とブール型パラメーターの選択</span><span class="sxs-lookup"><span data-stu-id="5a296-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="5a296-118">**✓ DO** メンバーが 2 つ以上のブール型パラメーターを持っている場合は、列挙型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="5a296-119">**X DO NOT** ブール値を使用してない場合は、絶対に 3 つ以上の値が必要な表示できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5a296-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="5a296-120">列挙型は、今後追加するため、値の余地を与えるので説明する列挙型に値を追加するすべての影響を考慮する必要があります[列挙型デザイン](../../../docs/standard/design-guidelines/enum.md)します。</span><span class="sxs-lookup"><span data-stu-id="5a296-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="5a296-121">**✓ CONSIDER** は本当に 2 つの状態の値であり、のみを使用してブール型プロパティを初期化するコンス トラクターのパラメーターのブール値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="5a296-122">引数の検証</span><span class="sxs-lookup"><span data-stu-id="5a296-122">Validating Arguments</span></span>  
 <span data-ttu-id="5a296-123">**✓ DO** パブリック、プロテクト、または明示的に実装されたメンバーに渡される引数を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a296-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="5a296-124">スロー <xref:System.ArgumentException?displayProperty=nameWithType>、または検証に失敗した場合、そのサブクラスのいずれか。</span><span class="sxs-lookup"><span data-stu-id="5a296-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="5a296-125">パブリックまたはプロテクト メンバー自体で発生する必ずしも必要はありません、実際の検証に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a296-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="5a296-126">プライベートまたは内部ルーチン内の下位レベルで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a296-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="5a296-127">重要な点は、エンドユーザーに公開されている領域全体が、引数を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a296-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="5a296-128">**✓ DO** スロー <xref:System.ArgumentNullException> null 引数が渡され、メンバーが null の引数をサポートしていない場合。</span><span class="sxs-lookup"><span data-stu-id="5a296-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="5a296-129">**✓ DO** 列挙型のパラメーターを検証します。</span><span class="sxs-lookup"><span data-stu-id="5a296-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="5a296-130">列挙型の引数は列挙型で定義された範囲内になりますとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5a296-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="5a296-131">CLR では、値が列挙型で定義されていない場合でも、任意の整数値を列挙型の値にキャストします。</span><span class="sxs-lookup"><span data-stu-id="5a296-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="5a296-132">**X DO NOT** 使用<xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>enum の範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a296-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="5a296-133">**✓ DO** 変更可能な引数がありますが変更されている検証後に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a296-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="5a296-134">メンバーが機密性の高いセキュリティの場合は、コピーを作成し、検証および引数を処理することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="5a296-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="5a296-135">パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5a296-135">Parameter Passing</span></span>  
 <span data-ttu-id="5a296-136">Framework デザイナーの観点からは、パラメーターの 3 つの主なグループ: 値渡しのパラメーター、`ref`パラメーター、および`out`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5a296-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="5a296-137">引数が値渡しのパラメーターで渡されると、メンバーは、実際に渡された引数のコピーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a296-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="5a296-138">引数が値型の場合、引数のコピーは、スタックに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a296-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="5a296-139">引数が参照型の場合は、参照のコピーは、スタックに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a296-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="5a296-140">パラメーターの値渡しを c#、VB.NET、および C++ では、既定値などの最も人気のある CLR 言語。</span><span class="sxs-lookup"><span data-stu-id="5a296-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="5a296-141">引数が渡された場合、`ref`パラメーター、メンバーはで渡される実際の引数への参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a296-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="5a296-142">引数が値型の場合、引数への参照はスタックに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a296-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="5a296-143">引数が参照型の場合は、参照への参照はスタックに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a296-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="5a296-144">`Ref` パラメーターは、メンバーの呼び出し元によって渡される引数を変更する許可を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a296-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="5a296-145">`Out` パラメーターはのような`ref`パラメーターは、小さな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="5a296-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="5a296-146">割り当てられていないし、前に、いくつかの値が割り当てられているメンバーの本文で読み取ることができません、パラメーターが最初と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5a296-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="5a296-147">また、パラメーターは、メンバーを返す前に、いくつかの値を割り当てられるがあります。</span><span class="sxs-lookup"><span data-stu-id="5a296-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="5a296-148">**X AVOID** を使用して`out`または`ref`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5a296-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="5a296-149">使用して`out`または`ref`パラメーターには、ポインター、値型と参照型の違いの理解および複数の戻り値を持つメソッドの処理の使用経験が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a296-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="5a296-150">また、間の差`out`と`ref`パラメーターはあまり理解されていません。</span><span class="sxs-lookup"><span data-stu-id="5a296-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="5a296-151">フレームワークの設計者、一般向けの設計ではユーザーがマスターの操作は期待できません`out`または`ref`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5a296-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="5a296-152">**X DO NOT** 参照型を参照渡しされます。</span><span class="sxs-lookup"><span data-stu-id="5a296-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="5a296-153">いくつかの例外の参照を交換するのに使用できるメソッドなど、規則があります。</span><span class="sxs-lookup"><span data-stu-id="5a296-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="5a296-154">可変個のパラメーターを持つメンバー</span><span class="sxs-lookup"><span data-stu-id="5a296-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="5a296-155">メンバーを可変個の引数を受け取ることができますが、配列パラメーターを提供することによって表現されます。</span><span class="sxs-lookup"><span data-stu-id="5a296-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="5a296-156">たとえば、<xref:System.String>次のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a296-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="5a296-157">ユーザーが呼び出すことができますし、<xref:System.String.Format%2A?displayProperty=nameWithType>メソッドは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5a296-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="5a296-158">配列パラメーターに c# params キーワードを追加すると、いわゆる params 配列パラメーターにパラメーターを変更し、一時配列を作成するショートカットを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a296-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="5a296-159">これにより、引数リスト内で直接、配列要素を渡すことによって、メソッドを呼び出すユーザー。</span><span class="sxs-lookup"><span data-stu-id="5a296-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="5a296-160">パラメーター リストの最後のパラメーターにのみ、params キーワードを追加できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a296-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="5a296-161">**✓ CONSIDER** 要素の数が少ない配列を渡すエンドユーザーが予想される場合、配列パラメーターに、params キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a296-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="5a296-162">多数の要素が渡されることに共通のシナリオと予想される場合は、ユーザーが、これら要素をインラインを渡していない可能性がありますし、そのため、params キーワードは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a296-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="5a296-163">**X AVOID** があれば、呼び出し元はほとんどの場合、入力既に配列内に params 配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="5a296-164">たとえば、バイトの配列パラメーターを持つメンバーは、個々 のバイトを渡すことによってほとんどないというは。</span><span class="sxs-lookup"><span data-stu-id="5a296-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="5a296-165">このため、.NET Framework でバイト配列パラメーターは、params キーワードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a296-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="5a296-166">**X DO NOT** params 配列パラメーターを受け取るメンバーによって、配列が変更された場合、params 配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a296-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="5a296-167">多くのコンパイラが呼び出しサイトで一時配列に、メンバーの引数を有効にするため、配列は、一時オブジェクトである可能性があり、そのため、配列への変更は失われます。</span><span class="sxs-lookup"><span data-stu-id="5a296-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="5a296-168">**✓ CONSIDER** 単純なオーバー ロードで、params キーワードを使用する場合でもより複雑なオーバー ロードでは使用できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a296-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="5a296-169">すべてのオーバー ロードである場合でも、1 つのオーバー ロードで params 配列を持つユーザーは値のかどうかを自問します。</span><span class="sxs-lookup"><span data-stu-id="5a296-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="5a296-170">**✓ DO** パラメーターを params キーワードを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="5a296-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="5a296-171">**✓ CONSIDER** 非常にパフォーマンスが重視される Api の引数の数が少ない呼び出しに対して特別なオーバー ロードとコード パスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a296-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="5a296-172">これにより、引数の数が少ない、API が呼び出されたときに、配列オブジェクトを作成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="5a296-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="5a296-173">配列パラメーターの単数形を取得し、数値のサフィックスを追加することによって、パラメーターの名前を形成します。</span><span class="sxs-lookup"><span data-stu-id="5a296-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="5a296-174">全体のコード パスを特別なケースに配列を作成するだけでなくより一般的なメソッドを呼び出す場合、これを行うだけする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a296-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="5a296-175">**✓ DO** params 配列引数として null を渡すことがあります。</span><span class="sxs-lookup"><span data-stu-id="5a296-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="5a296-176">配列が処理する前に null でないことを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a296-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="5a296-177">**X DO NOT** を使用して、`varargs`メソッド、それ以外の場合、省略記号と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5a296-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="5a296-178">C++ などのいくつかの CLR 言語という変数パラメーター リストを渡すための別の規則のサポート`varargs`メソッド。</span><span class="sxs-lookup"><span data-stu-id="5a296-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="5a296-179">CLS 準拠ではないために、規則は、フレームワークでは使用されませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a296-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="5a296-180">ポインター パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a296-180">Pointer Parameters</span></span>  
 <span data-ttu-id="5a296-181">一般に、ポインターがマネージ コードを適切に設計されたフレームワークのパブリック アクセスの領域には表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a296-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="5a296-182">ほとんどの場合、ポインターをカプセル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a296-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="5a296-183">ただし、ポインターは相互運用性の理由から、必要な場合によっては、適切なポインターを使用して、このような場合は。</span><span class="sxs-lookup"><span data-stu-id="5a296-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="5a296-184">**✓ DO** ポインターが CLS 準拠ではないために、ポインター引数を受け取り、メンバーの代替を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a296-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="5a296-185">**X AVOID** 高い引数のポインター引数のチェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a296-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="5a296-186">**✓ DO** 共通ポインターに関連する規則を伴うメンバーをデザインするときに従う必要です。</span><span class="sxs-lookup"><span data-stu-id="5a296-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="5a296-187">たとえばは、開始インデックスを渡す必要が単純なポインターの算術演算は、同じ結果に使用できるため、</span><span class="sxs-lookup"><span data-stu-id="5a296-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="5a296-188">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="5a296-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5a296-189">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="5a296-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a296-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a296-190">See also</span></span>

- [<span data-ttu-id="5a296-191">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="5a296-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="5a296-192">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="5a296-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

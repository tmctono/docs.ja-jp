---
title: C# の予約済み属性:Null 許容のスタティック分析
ms.date: 04/14/2020
description: これらの属性は、null 許容および null 非許容参照型に対するより適切な静的分析を提供するために、コンパイラによって解釈されます。
ms.openlocfilehash: 0315d78db7517541efe578d8675c0f2fe45f5aea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389812"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a><span data-ttu-id="d40b7-103">予約済み属性はコンパイラの null 状態の静的分析に寄与する</span><span class="sxs-lookup"><span data-stu-id="d40b7-103">Reserved attributes contribute to the compiler's null state static analysis</span></span>

<span data-ttu-id="d40b7-104">null 許容コンテキストの場合、コンパイラではコードの静的分析を実行して、すべての参照型変数の null 状態を判断します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-104">In a nullable context, the compiler performs static analysis of code to determine the null state of all reference type variables:</span></span>

- <span data-ttu-id="d40b7-105">*null 以外*:静的分析では、変数が null 以外の値に割り当てられていると判断されました。</span><span class="sxs-lookup"><span data-stu-id="d40b7-105">*not null*: Static analysis determined that the variable is assigned to a non-null value.</span></span>
- <span data-ttu-id="d40b7-106">*null の可能性あり*:静的分析では、変数に null 以外の値が割り当てられていることを判断できません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-106">*maybe null*: Static analysis cannot determine that a variable is assigned a non-null value.</span></span>

<span data-ttu-id="d40b7-107">API のセマンティクスについての情報をコンパイラに提供する、いくつかの属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-107">You can apply a number of attributes that provide information to the compiler about the semantics of your APIs.</span></span> <span data-ttu-id="d40b7-108">この情報は、コンパイラで静的分析を実行し、変数が null でないかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-108">That information helps the compiler perform static analysis and determine when a variable is not null.</span></span> <span data-ttu-id="d40b7-109">この記事では、これらの各属性とその使用方法について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-109">This article provides a brief description of each of those attributes and how to use them.</span></span> <span data-ttu-id="d40b7-110">すべての例では C# 8.0 以降を想定しており、コードは null 許容コンテキストに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-110">All the examples assume C# 8.0 or newer, and the code is in a nullable context.</span></span>

<span data-ttu-id="d40b7-111">よくある例から始めましょう。</span><span class="sxs-lookup"><span data-stu-id="d40b7-111">Let's start with a familiar example.</span></span> <span data-ttu-id="d40b7-112">ライブラリに、リソース文字列を取得するための次の API があるとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-112">Imagine your library has the following API to retrieve a resource string:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="d40b7-113">前述の例では、.NET のよくある `Try*` パターンに従っています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-113">The preceding example follows the familiar `Try*` pattern in .NET.</span></span> <span data-ttu-id="d40b7-114">この API には、2 つの参照引数 (`key` および `message` パラメーター) があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-114">There are two reference arguments for this API: the `key` and the `message` parameter.</span></span> <span data-ttu-id="d40b7-115">この API には、これらの引数の null 性に関連する次の規則があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-115">This API has the following rules relating to the nullness of these arguments:</span></span>

- <span data-ttu-id="d40b7-116">呼び出し元では、`key` の引数として `null` を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-116">Callers shouldn't pass `null` as the argument for `key`.</span></span>
- <span data-ttu-id="d40b7-117">呼び出し元では、`message` の引数として、値が `null` の変数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-117">Callers can pass a variable whose value is `null` as the argument for `message`.</span></span>
- <span data-ttu-id="d40b7-118">`TryGetMessage` メソッドから `true` が返された場合、`message` の値は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-118">If the `TryGetMessage` method returns `true`, the value of `message` isn't null.</span></span> <span data-ttu-id="d40b7-119">戻り値が `false,` である場合、`message` (およびその null 状態) の値は null です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-119">If the return value is `false,` the value of `message` (and its null state) is null.</span></span>

<span data-ttu-id="d40b7-120">`key` の規則は、変数型で表すことができます。`key` は null 非許容参照型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-120">The rule for `key` can be expressed by the variable type: `key` should be a non-nullable reference type.</span></span> <span data-ttu-id="d40b7-121">`message` パラメーターはより複雑です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-121">The `message` parameter is more complex.</span></span> <span data-ttu-id="d40b7-122">引数として `null` が許可されますが、成功した場合、`out` 引数が null でないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-122">It allows `null` as the argument, but guarantees that, on success, that `out` argument isn't null.</span></span> <span data-ttu-id="d40b7-123">これらのシナリオでは、予測を記述するために、より豊富なボキャブラリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-123">For these scenarios, you need a richer vocabulary to describe the expectations.</span></span>

<span data-ttu-id="d40b7-124">変数の null 状態に関する追加情報を表すために、いくつかの属性が追加されました。</span><span class="sxs-lookup"><span data-stu-id="d40b7-124">Several attributes have been added to express additional information about the null state of variables.</span></span> <span data-ttu-id="d40b7-125">C# 8 で null 許容参照型型が導入される前に記述したすべてのコードでは、"*null が認識されません*" でした。</span><span class="sxs-lookup"><span data-stu-id="d40b7-125">All code you wrote before C# 8 introduced nullable reference types was *null oblivious*.</span></span> <span data-ttu-id="d40b7-126">つまり、参照型変数は null である可能性がありますが、null チェックは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-126">That means any reference type variable may be null, but null checks aren't required.</span></span> <span data-ttu-id="d40b7-127">コードが "*null 許容認識*" になると、それらの規則は変わります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-127">Once your code is *nullable aware*, those rules change.</span></span> <span data-ttu-id="d40b7-128">参照型を `null` 値にすることはできません。また、null 許容参照型は、逆参照される前に `null` に対してチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-128">Reference types should never be the `null` value, and nullable reference types must be checked against `null` before being dereferenced.</span></span>

<span data-ttu-id="d40b7-129">API の規則は、`TryGetValue` API シナリオで見たとおり、より複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-129">The rules for your APIs are likely more complicated, as you saw with the `TryGetValue` API scenario.</span></span> <span data-ttu-id="d40b7-130">多くの API には、変数を `null` にできる場合やできない場合のより複雑な規則があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-130">Many of your APIs have more complex rules for when variables can or can't be `null`.</span></span> <span data-ttu-id="d40b7-131">このような場合は、次の属性のいずれかを使用して、これらの規則を表します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-131">In these cases, you'll use one of the following attributes to express those rules:</span></span>

- <span data-ttu-id="d40b7-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute):null 非許容の入力引数は null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="d40b7-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute):null 許容の入力引数を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>
- <span data-ttu-id="d40b7-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute):null 非許容の戻り値は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="d40b7-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute):null 許容の戻り値が null になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="d40b7-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 非許容の入力引数は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 許容の入力引数は null にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute):指定されたパラメーターの引数が null でない場合、戻り値は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="d40b7-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute):メソッドから制御が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="d40b7-140">つまり、常に例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-140">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="d40b7-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute):関連付けられた `bool` パラメーターに指定された値がある場合、このメソッドから制御が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>

<span data-ttu-id="d40b7-142">前述の説明は、各属性動作に関するクイック リファレンスです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-142">The preceding descriptions are a quick reference to what each attribute does.</span></span> <span data-ttu-id="d40b7-143">次の各セクションでは、動作と意味について、より詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-143">Each following section describes the behavior and meaning more thoroughly.</span></span>

<span data-ttu-id="d40b7-144">これらの属性を追加すると、API の規則に関する詳細情報がコンパイラに与えられます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-144">Adding these attributes gives the compiler more information about the rules for your API.</span></span> <span data-ttu-id="d40b7-145">呼び出し元のコードが、null 許容が有効なコンテキストでコンパイルされると、呼び出し元がこれらの規則に違反したときに、コンパイラによって警告されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-145">When calling code is compiled in a nullable enabled context, the compiler will warn callers when they violate those rules.</span></span> <span data-ttu-id="d40b7-146">これらの属性では、実装に対する追加のチェックが有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-146">These attributes don't enable additional checks on your implementation.</span></span>

## <a name="specify-preconditions-allownull-and-disallownull"></a><span data-ttu-id="d40b7-147">事前条件を指定する: `AllowNull` と `DisallowNull`</span><span class="sxs-lookup"><span data-stu-id="d40b7-147">Specify preconditions: `AllowNull` and `DisallowNull`</span></span>

<span data-ttu-id="d40b7-148">適切な既定値が設定されているため、`null` を返すことのない読み取りおよび書き込みプロパティについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-148">Consider a read/write property that never returns `null` because it has a reasonable default value.</span></span> <span data-ttu-id="d40b7-149">呼び出し元では、その既定値に設定するときに、set アクセサーに `null` を渡します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-149">Callers pass `null` to the set accessor when setting it to that default value.</span></span> <span data-ttu-id="d40b7-150">たとえば、チャット ルームで画面名を要求するメッセージング システムがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-150">For example, consider a messaging system that asks for a screen name in a chat room.</span></span> <span data-ttu-id="d40b7-151">何も指定されていない場合、システムによってランダムな名前が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-151">If none is provided, the system generates a random name:</span></span>

```csharp
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName;
```

<span data-ttu-id="d40b7-152">null 許容の認識されないコンテキストで上記のコードをコンパイルする場合、何も問題はありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-152">When you compile the preceding code in a nullable oblivious context, everything is fine.</span></span> <span data-ttu-id="d40b7-153">null 許容参照型を有効にすると、`ScreenName` プロパティが null 非許容参照になります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-153">Once you enable nullable reference types, the `ScreenName` property becomes a non-nullable reference.</span></span> <span data-ttu-id="d40b7-154">これは `get` アクセサーでは正しい動作です。`null` が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-154">That's correct for the `get` accessor: it never returns `null`.</span></span> <span data-ttu-id="d40b7-155">呼び出し元では、返されたプロパティで `null` をチェックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-155">Callers don't need to check the returned property for `null`.</span></span> <span data-ttu-id="d40b7-156">しかし、ここでプロパティを `null` に設定すると、警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-156">But now setting the property to `null` generates a warning.</span></span> <span data-ttu-id="d40b7-157">この種類のコードを引き続きサポートするには、次のコードに示すように、<xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> 属性をプロパティに追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-157">In order to continue to support this type of code, you add the <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> attribute to the property, as shown in the following code:</span></span>

```csharp
[AllowNull]
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName = GenerateRandomScreenName();
```

<span data-ttu-id="d40b7-158">これと、この記事で説明されている他の属性を使用するには、<xref:System.Diagnostics.CodeAnalysis> の `using` ディレクティブを追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-158">You may need to add a `using` directive for <xref:System.Diagnostics.CodeAnalysis> to use this and other attributes discussed in this article.</span></span> <span data-ttu-id="d40b7-159">属性は、`set` アクセサーではなく、プロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-159">The attribute is applied to the property, not the `set` accessor.</span></span> <span data-ttu-id="d40b7-160">`AllowNull` 属性では "*事前条件*" を指定し、入力にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-160">The `AllowNull` attribute specifies *pre-conditions*, and only applies to inputs.</span></span> <span data-ttu-id="d40b7-161">`get` アクセサーには戻り値がありますが、入力引数はありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-161">The `get` accessor has a return value, but no input arguments.</span></span> <span data-ttu-id="d40b7-162">したがって、`AllowNull` 属性は `set` アクセサーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-162">Therefore, the `AllowNull` attribute only applies to the `set` accessor.</span></span>

<span data-ttu-id="d40b7-163">前の例では、引数に `AllowNull` 属性を追加する場合の検索方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-163">The preceding example demonstrates what to look for when adding the `AllowNull` attribute on an argument:</span></span>

1. <span data-ttu-id="d40b7-164">その変数の一般的なコントラクトは、`null` にできないため、null 非許容参照型が必要であるというものです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-164">The general contract for that variable is that it shouldn't be `null`, so you want a non-nullable reference type.</span></span>
1. <span data-ttu-id="d40b7-165">入力変数を `null` にするシナリオはありますが、それらは最も一般的な使用方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-165">There are scenarios for the input variable to be `null`, though they aren't the most common usage.</span></span>

<span data-ttu-id="d40b7-166">ほとんどの場合、プロパティ、または `in`、`out`、および `ref` 引数にこの属性が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-166">Most often you'll need this attribute for properties, or `in`, `out`, and `ref` arguments.</span></span> <span data-ttu-id="d40b7-167">`AllowNull` 属性は、通常は変数が null 以外だが、`null` を事前条件として許可する必要がある場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-167">The `AllowNull` attribute is the best choice when a variable is typically non-null, but you need to allow `null` as a precondition.</span></span>

<span data-ttu-id="d40b7-168">`DisallowNull` を使用するシナリオと比較してください。この属性を使用して、null 許容参照型の入力変数を `null` にできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-168">Contrast that with scenarios for using `DisallowNull`: You use this attribute to specify that an input variable of a nullable reference type shouldn't be `null`.</span></span> <span data-ttu-id="d40b7-169">`null` は既定値であるが、クライアントでは null 以外の値にしか設定できないというプロパティについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-169">Consider a property where `null` is the default value, but clients can only set it to a non-null value.</span></span> <span data-ttu-id="d40b7-170">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-170">Consider the following code:</span></span>

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

<span data-ttu-id="d40b7-171">上記のコードは、`ReviewComment` が `null` である可能性はあるが、`null` に設定できないという設計を表すのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-171">The preceding code is the best way to express your design that the `ReviewComment` could be `null`, but can't be set to `null`.</span></span> <span data-ttu-id="d40b7-172">このコードが null 許容認識になると、<xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType> を使用して、呼び出し元に対して、この概念をより明確に表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-172">Once this code is nullable aware, you can express this concept more clearly to callers using the <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>:</span></span>

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

<span data-ttu-id="d40b7-173">null 許容コンテキストでは、`ReviewComment` `get` アクセサーから `null` の既定値が返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-173">In a nullable context, the `ReviewComment` `get` accessor could return the default value of `null`.</span></span> <span data-ttu-id="d40b7-174">コンパイラからは、アクセスの前にチェックする必要があることが警告されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-174">The compiler warns that it must be checked before access.</span></span> <span data-ttu-id="d40b7-175">さらに、`null` である可能性があっても、呼び出し元で明示的に `null` に設定できないことが、呼び出し元に警告されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-175">Furthermore, it warns callers that, even though it could be `null`, callers shouldn't explicitly set it to `null`.</span></span> <span data-ttu-id="d40b7-176">`DisallowNull` 属性では、"*事前条件*" も指定され、これは `get` アクセサーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-176">The `DisallowNull` attribute also specifies a *pre-condition*, it does not affect the `get` accessor.</span></span> <span data-ttu-id="d40b7-177">以下について、これらの特性を監視する場合は、`DisallowNull` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-177">You use the `DisallowNull` attribute when you observe these characteristics about:</span></span>

1. <span data-ttu-id="d40b7-178">主なシナリオでは (多くの場合、最初にインスタンス化されるときに)、変数が `null` である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-178">The variable could be `null` in core scenarios, often when first instantiated.</span></span>
1. <span data-ttu-id="d40b7-179">変数は、明示的に `null` に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-179">The variable shouldn't be explicitly set to `null`.</span></span>

<span data-ttu-id="d40b7-180">このような状況は、もともと "*null として認識されていなかった*" コードでよく見られます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-180">These situations are common in code that was originally *null oblivious*.</span></span> <span data-ttu-id="d40b7-181">オブジェクト プロパティが、2 つの異なる初期化操作で設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-181">It may be that object properties are set in two distinct initialization operations.</span></span> <span data-ttu-id="d40b7-182">一部のプロパティは、一部の非同期処理が完了した後にのみ設定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-182">It may be that some properties are set only after some asynchronous work has completed.</span></span>

<span data-ttu-id="d40b7-183">`AllowNull` および `DisallowNull` 属性を使用すると、変数の事前条件が、これらの変数の null 許容注釈と一致しない可能性があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-183">The `AllowNull` and `DisallowNull` attributes enable you to specify that preconditions on variables may not match the nullable annotations on those variables.</span></span> <span data-ttu-id="d40b7-184">これにより、API の特性の詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-184">These provide more detail about the characteristics of your API.</span></span> <span data-ttu-id="d40b7-185">この追加情報は、呼び出し元で API を正しく使用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-185">This additional information helps callers use your API correctly.</span></span> <span data-ttu-id="d40b7-186">次の属性を使用して、事前条件を指定することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="d40b7-186">Remember you specify preconditions using the following attributes:</span></span>

- <span data-ttu-id="d40b7-187">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute):null 非許容の入力引数を null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-187">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="d40b7-188">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute):null 許容の入力引数を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-188">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>

## <a name="specify-post-conditions-maybenull-and-notnull"></a><span data-ttu-id="d40b7-189">事後条件を指定する: `MaybeNull` と `NotNull`</span><span class="sxs-lookup"><span data-stu-id="d40b7-189">Specify post-conditions: `MaybeNull` and `NotNull`</span></span>

<span data-ttu-id="d40b7-190">次のシグネチャを持つメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-190">Suppose you have a method with the following signature:</span></span>

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

<span data-ttu-id="d40b7-191">検索された名前が見つからなかったときに `null` を返す、このようなメソッドを記述した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-191">You've likely written a method like this to return `null` when the name sought wasn't found.</span></span> <span data-ttu-id="d40b7-192">`null` は、レコードが見つからなかったことを明確に示しています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-192">The `null` clearly indicates that the record wasn't found.</span></span> <span data-ttu-id="d40b7-193">この例では、戻り値の型を `Customer` から `Customer?` に変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-193">In this example, you'd likely change the return type from `Customer` to `Customer?`.</span></span> <span data-ttu-id="d40b7-194">戻り値を null 許容参照型として宣言すると、この API の意図が明確になります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-194">Declaring the return value as a nullable reference type specifies the intent of this API clearly.</span></span>

<span data-ttu-id="d40b7-195">「[ジェネリック定義と NULL 値の許容](../../nullable-attributes.md#generic-definitions-and-nullability)」に記載されている理由により、その手法はジェネリック メソッドでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-195">For reasons covered under [Generic definitions and nullability](../../nullable-attributes.md#generic-definitions-and-nullability) that technique does not work with generic methods.</span></span> <span data-ttu-id="d40b7-196">同様のパターンに従うジェネリック メソッドがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-196">You may have a generic method that follows a similar pattern:</span></span>

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

<span data-ttu-id="d40b7-197">戻り値が `T?` であることを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-197">You can't specify that the return value is `T?`.</span></span> <span data-ttu-id="d40b7-198">検索された項目が見つからない場合、このメソッドからは `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-198">The method returns `null` when the sought item isn't found.</span></span> <span data-ttu-id="d40b7-199">戻り値の型として `T?` を宣言することはできないため、メソッドの戻り値に `MaybeNull` 注釈を追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-199">Since you can't declare a `T?` return type, you add the `MaybeNull` annotation to the method return:</span></span>

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

<span data-ttu-id="d40b7-200">前のコードでは、コントラクトは null 非許容型を意味するが、戻り値は実際には null である "*可能性がある*" ことを呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-200">The preceding code informs callers that the contract implies a non-nullable type, but the return value *may* actually be null.</span></span>  <span data-ttu-id="d40b7-201">API は null 非許容型で、通常はジェネリック型パラメーターである必要はあるが、`null` が返されるインスタンスが存在する可能性がある場合は、`MaybeNull` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-201">Use the `MaybeNull` attribute when your API should be a non-nullable type, typically a generic type parameter, but there may be instances where `null` would be returned.</span></span>

<span data-ttu-id="d40b7-202">型が null 許容参照型である場合でも、戻り値あるいは `out` または `ref` 引数が null でないことを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-202">You can also specify that a return value or an `out` or `ref` argument isn't null even though the type is a nullable reference type.</span></span> <span data-ttu-id="d40b7-203">配列が、多数の要素を保持するのに十分な大きさであることを保証するメソッドについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-203">Consider a method that ensures an array is large enough to hold a number of elements.</span></span> <span data-ttu-id="d40b7-204">入力引数に容量がない場合、ルーチンで新しい配列を割り当てて、そこに既存のすべての要素をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-204">If the input argument doesn't have capacity, the routine would allocate a new array and copy all the existing elements into it.</span></span> <span data-ttu-id="d40b7-205">入力引数が `null` である場合は、ルーチンで新しいストレージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-205">If the input argument is `null`, the routine would allocate new storage.</span></span> <span data-ttu-id="d40b7-206">十分な容量がある場合、ルーチンでは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-206">If there's sufficient capacity, the routine does nothing:</span></span>

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

<span data-ttu-id="d40b7-207">次のように、このルーチンを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-207">You could call this routine as follows:</span></span>

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

<span data-ttu-id="d40b7-208">null 参照型を有効にした後、確実に前のコードが警告なしでコンパイルされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-208">After enabling null reference types, you want to ensure that the preceding code compiles without warnings.</span></span> <span data-ttu-id="d40b7-209">メソッドから制御が戻ったときに、`storage` 引数が null でないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-209">When the method returns, the `storage` argument is guaranteed to be not null.</span></span> <span data-ttu-id="d40b7-210">しかし、null 参照で `EnsureCapacity` を呼び出すことはできます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-210">However, it's acceptable to call `EnsureCapacity` with a null reference.</span></span> <span data-ttu-id="d40b7-211">`storage` を null 許容参照型にして、`NotNull` 事後条件をパラメーター宣言に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-211">You can make `storage` a nullable reference type, and add the `NotNull` post-condition to the parameter declaration:</span></span>

```csharp
public void EnsureCapacity<T>([NotNull]ref T[]? storage, int size)
```

<span data-ttu-id="d40b7-212">上記のコードは、既存のコントラクトを明確に表しています。呼び出し元では `null` 値を持つ変数を渡すことはできますが、戻り値は null になることはないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-212">The preceding code expresses the existing contract clearly: Callers can pass a variable with the `null` value, but the return value is guaranteed to never be null.</span></span> <span data-ttu-id="d40b7-213">`NotNull` 属性は、`null` が引数として渡される可能性があるが、メソッドから制御が戻ったときにその引数が null でないことが保証される、`ref` および `out` 引数に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-213">The `NotNull` attribute is most useful for `ref` and `out` arguments where `null` may be passed as an argument, but that argument is guaranteed to be not null when the method returns.</span></span>

<span data-ttu-id="d40b7-214">無条件の事後条件は、次の属性を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-214">You specify unconditional postconditions using the following attributes:</span></span>

- <span data-ttu-id="d40b7-215">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute):null 非許容の戻り値は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-215">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="d40b7-216">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute):null 許容の戻り値が null になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-216">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a><span data-ttu-id="d40b7-217">条件付きの事後条件を指定する: `NotNullWhen`、`MaybeNullWhen`、および `NotNullIfNotNull`</span><span class="sxs-lookup"><span data-stu-id="d40b7-217">Specify conditional post-conditions: `NotNullWhen`, `MaybeNullWhen`, and `NotNullIfNotNull`</span></span>

<span data-ttu-id="d40b7-218">`string` メソッド <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> は見慣れたものかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-218">You're likely familiar with the `string` method <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>.</span></span> <span data-ttu-id="d40b7-219">引数が null または空の文字列の場合、このメソッドから `true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-219">This method returns `true` when the argument is null or an empty string.</span></span> <span data-ttu-id="d40b7-220">これは、null チェックの形式です。メソッドから `false` が返された場合、呼び出し元で引数の null チェックを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-220">It's a form of null-check: Callers don't need to null-check the argument if the method returns `false`.</span></span> <span data-ttu-id="d40b7-221">この null 許容認識のようなメソッドを作成するには、引数を null 許容参照型に設定し、`NotNullWhen` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-221">To make a method like this nullable aware, you'd set the argument to a nullable reference type, and add the `NotNullWhen` attribute:</span></span>

```csharp
bool IsNullOrEmpty([NotNullWhen(false)]string? value);
```

<span data-ttu-id="d40b7-222">これにより、戻り値が `false` であるコードでは、null チェックを行う必要がないことがコンパイラに通知されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-222">That informs the compiler that any code where the return value is `false` need not be null-checked.</span></span> <span data-ttu-id="d40b7-223">属性を追加すると、`IsNullOrEmpty` で必要な null チェックが実行されることがコンパイラの静的分析に通知されます。`false` が返された場合、入力引数は `null` ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-223">The addition of the attribute informs the compiler's static analysis that `IsNullOrEmpty` performs the necessary null check: when it returns `false`, the input argument is not `null`.</span></span>

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

<span data-ttu-id="d40b7-224">.NET Core 3.0 の場合、上記のように <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> メソッドに注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-224">The <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> method will be annotated as shown above for .NET Core 3.0.</span></span> <span data-ttu-id="d40b7-225">コードベースには、オブジェクトの状態で null 値をチェックする、同様のメソッドが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-225">You may have similar methods in your codebase that check the state of objects for null values.</span></span> <span data-ttu-id="d40b7-226">コンパイラではカスタムの null チェック メソッドが認識されないため、注釈を自分で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-226">The compiler won't recognize custom null check methods, and you'll need to add the annotations yourself.</span></span> <span data-ttu-id="d40b7-227">属性を追加すると、コンパイラの静的分析で、テストされた変数が null チェックされたかどうが認識されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-227">When you add the attribute, the compiler's static analysis knows when the tested variable has been null checked.</span></span>

<span data-ttu-id="d40b7-228">これらの属性のもう 1 つの用途は、`Try*` パターンです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-228">Another use for these attributes is the `Try*` pattern.</span></span> <span data-ttu-id="d40b7-229">`ref` および `out` 変数の事後条件は、戻り値を通じて伝達されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-229">The postconditions for `ref` and `out` variables are communicated through the return value.</span></span> <span data-ttu-id="d40b7-230">前述のこのメソッドについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-230">Consider this method shown earlier:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="d40b7-231">上記のメソッドは、一般的な .NET 表現形式に従います。戻り値は、`message` が見つかった値に設定されているかどうか、またはメッセージが見つからない場合は、既定値に設定されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-231">The preceding method follows a typical .NET idiom: the return value indicates if `message` was set to the found value or, if no message is found, to the default value.</span></span> <span data-ttu-id="d40b7-232">メソッドから `true` が返された場合、`message` の値は null ではありません。それ以外の場合、メソッドでは `message` が null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-232">If the method returns `true`, the value of `message` isn't null; otherwise, the method sets `message` to null.</span></span>

<span data-ttu-id="d40b7-233">`NotNullWhen` 属性を使用して、その表現方法を伝達することができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-233">You can communicate that idiom using the `NotNullWhen` attribute.</span></span> <span data-ttu-id="d40b7-234">null 許容参照型のシグネチャを更新する場合は、`message` を `string?` にして、属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-234">When you update the signature for nullable reference types, make `message` a `string?` and add an attribute:</span></span>

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

<span data-ttu-id="d40b7-235">前述の例では、`TryGetMessage` から `true` が返された場合、`message` の値は null ではないと認識されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-235">In the preceding example, the value of `message` is known to be not null when `TryGetMessage` returns `true`.</span></span> <span data-ttu-id="d40b7-236">同じように、コードベースで同様のメソッドに注釈を付ける必要があります。引数は `null` である可能性があり、メソッドから `true` が返された場合は null ではないと認識されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-236">You should annotate similar methods in your codebase in the same way: the arguments could be `null`, and are known to be not null when the method returns `true`.</span></span>

<span data-ttu-id="d40b7-237">最後にもう 1 つ属性があります。これも必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-237">There's one final attribute you may also need.</span></span> <span data-ttu-id="d40b7-238">戻り値の null 状態は、1 つまたは複数の入力引数の null 状態に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-238">Sometimes the null state of a return value depends on the null state of one or more input arguments.</span></span> <span data-ttu-id="d40b7-239">特定の入力引数が `null` でない場合は常に、これらのメソッドから null 以外の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-239">These methods will return a non-null value whenever certain input arguments aren't `null`.</span></span> <span data-ttu-id="d40b7-240">これらのメソッドに正しく注釈を付けるには、`NotNullIfNotNull` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-240">To correctly annotate these methods, you use the `NotNullIfNotNull` attribute.</span></span> <span data-ttu-id="d40b7-241">次のメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-241">Consider the following method:</span></span>

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

<span data-ttu-id="d40b7-242">`url` 引数が null でない場合、出力は `null` ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-242">If the `url` argument isn't null, the output isn't `null`.</span></span> <span data-ttu-id="d40b7-243">null 許容参照を有効にすると、API で null 入力が受け入れられることがない場合、そのシグネチャは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-243">Once nullable references are enabled, that signature works correctly, provided your API never accepts a null input.</span></span> <span data-ttu-id="d40b7-244">しかし、入力が null である可能性がある場合は、戻り値も null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-244">However, if the input could be null, then return value could also be null.</span></span> <span data-ttu-id="d40b7-245">したがって、シグネチャを次のコードに変更できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-245">Therefore, you could change the signature to the following code:</span></span>

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="d40b7-246">これも機能しますが、多くの場合、呼び出し元での追加の `null` チェックの実装が強制されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-246">That also works, but will often force callers to implement extra `null` checks.</span></span> <span data-ttu-id="d40b7-247">コントラクトは、入力引数 `url` が `null` である場合にのみ、戻り値が `null` になるというものです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-247">The contract is that the return value would be `null` only when the input argument `url` is `null`.</span></span> <span data-ttu-id="d40b7-248">このコントラクトを表すには、次のコードに示すように、このメソッドに注釈を付けます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-248">To express that contract, you would annotate this method as shown in the following code:</span></span>

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="d40b7-249">戻り値と引数の両方に、`?` で注釈が付けられています。これは、どちらも `null` である可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-249">The return value and the argument have both been annotated with the `?` indicating that either could be `null`.</span></span> <span data-ttu-id="d40b7-250">`url` 引数が `null` でない場合、属性によって、戻り値が null にならないことがさらに明確になります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-250">The attribute further clarifies that the return value won't be null when the `url` argument isn't `null`.</span></span>

<span data-ttu-id="d40b7-251">条件付きの事後条件は、これらの属性を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-251">You specify conditional postconditions using these attributes:</span></span>

- <span data-ttu-id="d40b7-252">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 非許容の入力引数は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-252">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-253">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 許容の入力引数は null にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-253">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-254">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute):指定されたパラメーターの入力引数が null でない場合、戻り値は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-254">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the input argument for the specified parameter isn't null.</span></span>

## <a name="verify-unreachable-code"></a><span data-ttu-id="d40b7-255">到達できないコードを検証する</span><span class="sxs-lookup"><span data-stu-id="d40b7-255">Verify unreachable code</span></span>

<span data-ttu-id="d40b7-256">一部のメソッド (通常は例外ヘルパーまたはその他のユーティリティ メソッド) は、常に例外をスローすることによって終了します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-256">Some methods, typically exception helpers or other utility methods, always exit by throwing an exception.</span></span> <span data-ttu-id="d40b7-257">あるいは、ヘルパーでは、ブール型引数の値に基づいて、例外がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-257">Or, a helper may throw an exception based on the value of a Boolean argument.</span></span>

<span data-ttu-id="d40b7-258">最初のケースでは、メソッド宣言に `DoesNotReturn` 属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-258">In the first case, you can add the `DoesNotReturn` attribute to the method declaration.</span></span> <span data-ttu-id="d40b7-259">コンパイラは、3 つの方法で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-259">The compiler helps you in three ways.</span></span> <span data-ttu-id="d40b7-260">1 つ目では、例外をスローせずにメソッドを終了できるパスがある場合、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-260">First, the compiler issues a warning if there is a path where the method can exit without throwing an exception.</span></span> <span data-ttu-id="d40b7-261">2 つ目では、コンパイラによって、適切な `catch` 句が検出されるまで、そのメソッドの呼び出しの後にコードが "*到達できない*" ものとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-261">Second, the compiler marks any code after a call to that method as *unreachable*, until an appropriate `catch` clause is encountered.</span></span> <span data-ttu-id="d40b7-262">3 つ目では、到達できないコードが null 状態に影響することはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-262">Third, the unreachable code won't affect any null states.</span></span> <span data-ttu-id="d40b7-263">たとえば、次のメソッドがあったとします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-263">Consider this method:</span></span>

```csharp
[DoesNotReturn]
private void FailFast()
{
   throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   if (!isInitialized)
      FailFast();

   // unreachable code:
   this.field = containedField;
}
```

<span data-ttu-id="d40b7-264">2 つ目のケースでは、メソッドのブール型パラメーターに `DoesNotReturnIf` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-264">In the second case, you add the `DoesNotReturnIf` attribute to a Boolean parameter of the method.</span></span> <span data-ttu-id="d40b7-265">前の例は次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-265">You can modify the previous example as follows:</span></span>

```csharp
private void FailFast([DoesNotReturnIf(false)]bool isValid)
{
   if (!isValid)
       throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   FailFast(isInitialized);

   // unreachable code when "isInitialized" is false:
   this.field = containedField;
}
```

## <a name="summary"></a><span data-ttu-id="d40b7-266">まとめ</span><span class="sxs-lookup"><span data-stu-id="d40b7-266">Summary</span></span>

<span data-ttu-id="d40b7-267">null 許容参照型を追加すると、`null` である可能性のある変数に関する API の予測を記述するための、最初のボキャブラリが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-267">Adding nullable reference types provides an initial vocabulary to describe your APIs expectations for variables that could be `null`.</span></span> <span data-ttu-id="d40b7-268">追加の属性では、変数の null 状態を事前条件および事後条件として記述するために、より豊富なボキャブラリが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-268">The additional attributes provide a richer vocabulary to describe the null state of variables as preconditions and postconditions.</span></span> <span data-ttu-id="d40b7-269">これらの属性では、予測をより明確に記述し、API を使用して開発者により優れたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-269">These attributes more clearly describe your expectations and provide a better experience for the developers using your APIs.</span></span>

<span data-ttu-id="d40b7-270">null 許容コンテキストのライブラリを更新する際には、API のユーザーに正しい使用方法を示すために、これらの属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-270">As you update libraries for a nullable context, add these attributes to guide users of your APIs to the correct usage.</span></span> <span data-ttu-id="d40b7-271">これらの属性は、入力引数と戻り値の null 状態を完全に記述するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-271">These attributes help you fully describe the null-state of input arguments and return values:</span></span>

- <span data-ttu-id="d40b7-272">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute):null 非許容の入力引数を null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-272">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="d40b7-273">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute):null 許容の入力引数を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-273">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>
- <span data-ttu-id="d40b7-274">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute):null 非許容の戻り値は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-274">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="d40b7-275">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute):null 許容の戻り値が null になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-275">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="d40b7-276">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 非許容の入力引数は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-276">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-277">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute):メソッドから指定された `bool` 値が返された場合、null 許容の入力引数は null にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-277">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="d40b7-278">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute):指定されたパラメーターの入力引数が null でない場合、戻り値は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-278">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the input argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="d40b7-279">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute):メソッドから制御が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-279">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="d40b7-280">つまり、常に例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-280">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="d40b7-281">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute):関連付けられた `bool` パラメーターに指定された値がある場合、このメソッドから制御が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-281">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>

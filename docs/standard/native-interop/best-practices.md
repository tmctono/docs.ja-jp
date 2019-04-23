---
title: ネイティブ相互運用性のベスト プラクティス - .NET
description: .NET でネイティブ コンポーネントとやり取りするためのベスト プラクティスについて説明します。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 6702d469abf317b3b1f545ce79b980e8581ab5f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196659"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="85ffb-103">ネイティブ相互運用性のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="85ffb-103">Native interoperability best practices</span></span>

<span data-ttu-id="85ffb-104">.NET には、ネイティブ相互運用性コードをカスタマイズするさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="85ffb-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="85ffb-105">この記事には、Microsoft の .NET チームがネイティブ相互運用性のために従うガイダンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85ffb-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="85ffb-106">一般的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="85ffb-106">General guidance</span></span>

<span data-ttu-id="85ffb-107">このセクションのガイダンスは、すべての相互運用シナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="85ffb-108">**✔️ 実行**: メソッドとパラメーターには、呼び出すネイティブ メソッドと同じ名前付けと大文字/小文字の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="85ffb-109">**✔️ 推奨**: 定数値に対して同じ名前付けと大文字/小文字の設定を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="85ffb-110">**✔️ 実行**: ネイティブ型に最も近い .NET 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="85ffb-111">たとえば、C# では、ネイティブ型が `unsigned int` の場合は `uint` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="85ffb-112">**✔️ 実行**: 目的の動作が既定の動作と異なる場合にのみ `[In]` および `[Out]` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="85ffb-113">**✔️ 推奨**: <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> を使用してネイティブ配列バッファーをプールするようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="85ffb-114">**✔️ 推奨**: P/Invoke 宣言をネイティブ ライブラリと同じ名前と大文字/小文字の設定を使用してクラスにラップするようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="85ffb-115">これにより、`[DllImport]` 属性で C# `nameof` 言語機能を使用してネイティブ ライブラリの名前を渡し、ネイティブ ライブラリの名前のスペルを間違えないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="85ffb-116">dllImport 属性の設定</span><span class="sxs-lookup"><span data-stu-id="85ffb-116">DllImport attribute settings</span></span>

| <span data-ttu-id="85ffb-117">設定</span><span class="sxs-lookup"><span data-stu-id="85ffb-117">Setting</span></span> | <span data-ttu-id="85ffb-118">既定値</span><span class="sxs-lookup"><span data-stu-id="85ffb-118">Default</span></span> | <span data-ttu-id="85ffb-119">推奨事項</span><span class="sxs-lookup"><span data-stu-id="85ffb-119">Recommendation</span></span> | <span data-ttu-id="85ffb-120">説明</span><span class="sxs-lookup"><span data-stu-id="85ffb-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="85ffb-121">既定値のままにします</span><span class="sxs-lookup"><span data-stu-id="85ffb-121">keep default</span></span>  | <span data-ttu-id="85ffb-122">これが明示的に false に設定されている場合、失敗した HRESULT の戻り値は例外になります (そして結果として定義内の戻り値は null になります)。</span><span class="sxs-lookup"><span data-stu-id="85ffb-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="85ffb-123">API によって異なります</span><span class="sxs-lookup"><span data-stu-id="85ffb-123">depends on the API</span></span>  | <span data-ttu-id="85ffb-124">API が GetLastError を使用し、Marshal.GetLastWin32Error を使用して値を取得する場合は、true に設定します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="85ffb-125">API がエラーがあるという条件を設定している場合は、誤って上書きされないように他の呼び出しを行う前にエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="85ffb-126">`CharSet.None` (`CharSet.Ansi` の動作にフォールバックします)</span><span class="sxs-lookup"><span data-stu-id="85ffb-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="85ffb-127">定義内に文字列または文字が存在する場合は、明示的に `CharSet.Unicode` または `CharSet.Ansi` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="85ffb-128">文字列のマーシャリング動作と `false` のときの `ExactSpelling` の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-128">This specifies marshalling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="85ffb-129">Unix では `CharSet.Ansi` は実際には UTF8 である点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="85ffb-130">"_ほとんど_" の場合、Windows では Unicode が使用され、Unix では UTF8 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="85ffb-131">詳細については、[文字セットのドキュメント](./charset.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="85ffb-132">ランタイムで `CharSet` 設定の値に応じてサフィックスが "A" または "W" (`CharSet.Ansi` の場合は "A"、`CharSet.Unicode` の場合は "W") の代替の関数名が検索されないときに、これを true に設定し、わずかなパフォーマンス上のメリットを得ます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="85ffb-133">文字列パラメーター</span><span class="sxs-lookup"><span data-stu-id="85ffb-133">String parameters</span></span>

<span data-ttu-id="85ffb-134">CharSet が Unicode の場合または引数が `[MarshalAs(UnmanagedType.LPWSTR)]` であり、"_かつ_" 文字列が (`ref` または `out` ではなく) 値で渡される場合、設定は固定され、ネイティブ コードから (コピーではなく) 直接使用されます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="85ffb-135">文字列の ANSI 処理が明示的に必要ではない限り、必ず `[DllImport]` を `Charset.Unicode` としてマークしてください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="85ffb-136">**❌ 禁止**: `[Out] string` パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="85ffb-137">文字列がインターン処理された文字列で、文字列パラメーターが `[Out]` 属性の値で渡された場合、ランタイムが不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="85ffb-138">文字列のインターン処理の詳細については、<xref:System.String.Intern%2A?displayProperty=nameWithType> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="85ffb-139">**❌ 回避**: `StringBuilder` パラメーターを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="85ffb-140">`StringBuilder` のマーシャリングによって "*常に*" ネイティブ バッファー コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-140">`StringBuilder` marshalling *always* creates a native buffer copy.</span></span> <span data-ttu-id="85ffb-141">そのため、非常に非能率的になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="85ffb-142">その典型的なシナリオとして、文字列を受け取る Windows API を呼び出す場合があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="85ffb-143">目的の容量の SB を作成します (管理容量を割り当てます) **{1}**</span><span class="sxs-lookup"><span data-stu-id="85ffb-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="85ffb-144">呼び出し</span><span class="sxs-lookup"><span data-stu-id="85ffb-144">Invoke</span></span>
   1. <span data-ttu-id="85ffb-145">ネイティブ バッファーを割り当てます **{2}**</span><span class="sxs-lookup"><span data-stu-id="85ffb-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="85ffb-146">`[In]` "_(`StringBuilder` パラメーターの既定値)_" の場合、内容をコピーします</span><span class="sxs-lookup"><span data-stu-id="85ffb-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="85ffb-147">`[Out]` **{3}** "_(`StringBuilder` の既定値でもあります)_" の場合、ネイティブ バッファーを新しく割り当てられたマネージド配列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="85ffb-148">`ToString()` でさらに別のマネージド配列を割り当てます **{4}**</span><span class="sxs-lookup"><span data-stu-id="85ffb-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="85ffb-149">これは、ネイティブ コードから文字列を取得する *{4}* の割り当てです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="85ffb-150">これを制限するために最適な方法は、`StringBuilder` を別の呼び出しで再利用することですが、それでも *1* つの割り当てが節約されるだけです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="85ffb-151">`ArrayPool` から文字バッファーを使用してキャッシュする方がはるかにお勧めです。以降の呼び出しでは `ToString()` の割り当てのみで済むようになります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="85ffb-152">`StringBuilder` に関するもう 1 つの問題は、戻り値のバッファーが常に最初の null までコピーされることです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="85ffb-153">渡された文字列が null で終了していない場合、または null 終端文字列が 2 つある場合、よくても P/Invoke は不正確になります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="85ffb-154">`StringBuilder` を "*使用する*" 場合、最後の問題は、相互運用のために常に考慮される非表示の null が容量に "**含まれない**" ことです。ます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="85ffb-155">ほとんどの API はバッファー サイズに null が "*含まれる*" ことを想定しているため、これを誤りと考えられることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="85ffb-156">その結果、無駄な、または不要な割り当てが行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="85ffb-157">さらに、この問題により、ランタイムでコピーを最小化する `StringBuilder` のマーシャリングを最適化できなくなります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshalling to minimize copies.</span></span>

<span data-ttu-id="85ffb-158">**✔️ 推奨**: `ArrayPool` から `char[]` を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="85ffb-159">文字列のマーシャリングの詳細については、「[文字列に対する既定のマーシャリング](../../framework/interop/default-marshaling-for-strings.md)」と「[Customizing string marshalling (文字列のマーシャリングのカスタマイズ)](customize-parameter-marshalling.md#customizing-string-parameters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-159">For more information on string marshalling, see [Default Marshalling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshalling](customize-parameter-marshalling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="85ffb-160">__Windows 固有__</span><span class="sxs-lookup"><span data-stu-id="85ffb-160">__Windows Specific__</span></span>  
> <span data-ttu-id="85ffb-161">`[Out]` 文字列の場合、CLR は文字列を解放するために既定で `CoTaskMemFree` を使用します。また、`UnmanagedType.BSTR` とマークされている文字列の場合は `SysStringFree` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="85ffb-162">**出力文字列バッファーがあるほとんどの API の場合:**</span><span class="sxs-lookup"><span data-stu-id="85ffb-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="85ffb-163">渡される文字数には、常に null が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85ffb-163">The passed in character count must include the null.</span></span> <span data-ttu-id="85ffb-164">返された値が、渡された文字数より少ない場合、呼び出しは成功し、値は末尾の null を "*除いた*" 文字数になります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="85ffb-165">それ以外の場合、カウントは null 文字を "*含む*" バッファーの必要なサイズになります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="85ffb-166">5 を渡し、4 を受け取る:文字列の長さは 4 文字であり、末尾に null が付きます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="85ffb-167">5 を渡し、6 を受け取る:文字列の長さは 5 文字であり、null を保持するために 6 文字のバッファーが必要です。</span><span class="sxs-lookup"><span data-stu-id="85ffb-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="85ffb-168">Windows の文字列のデータ型</span><span class="sxs-lookup"><span data-stu-id="85ffb-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="85ffb-169">ブール型のパラメーターとフィールド</span><span class="sxs-lookup"><span data-stu-id="85ffb-169">Boolean parameters and fields</span></span>

<span data-ttu-id="85ffb-170">ブール値は混乱しやすいものです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="85ffb-171">既定では、.NET の `bool` は Windows の `BOOL` にマーシャリングされます。これは 4 バイトの値です。</span><span class="sxs-lookup"><span data-stu-id="85ffb-171">By default, a .NET `bool` is marshalled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="85ffb-172">一方、C および C++ の `_Bool` 型と `bool` 型は "*シングル*" バイトです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="85ffb-173">これは、戻り値の半分が破棄されると、結果のみが変わる "*可能性*" があるので、バグの追跡が困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="85ffb-174">.NET の `bool` 値を C または C++ の `bool` 型にマーシャリングする方法の詳細については、[ブール値フィールドのマーシャリングのカスタマイズ](customize-struct-marshalling.md#customizing-boolean-field-marshalling)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-174">For more for information on marshalling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshalling](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span></span>

## <a name="guids"></a><span data-ttu-id="85ffb-175">GUID</span><span class="sxs-lookup"><span data-stu-id="85ffb-175">GUIDs</span></span>

<span data-ttu-id="85ffb-176">GUID はシグネチャに直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="85ffb-177">多くの Windows API は、`REFIID` のような `GUID&` 型のエイリアスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="85ffb-178">参照渡しするときに、`ref` で渡すか、`[MarshalAs(UnmanagedType.LPStruct)]` 属性を使用して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="85ffb-179">GUID</span><span class="sxs-lookup"><span data-stu-id="85ffb-179">GUID</span></span> | <span data-ttu-id="85ffb-180">参照渡しの GUID</span><span class="sxs-lookup"><span data-stu-id="85ffb-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="85ffb-181">**❌ 禁止**: `ref` GUID パラメーター以外に `[MarshalAs(UnmanagedType.LPStruct)]` を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="85ffb-182">blittable 型</span><span class="sxs-lookup"><span data-stu-id="85ffb-182">Blittable types</span></span>

<span data-ttu-id="85ffb-183">blittable 型は、マネージド コードとネイティブ コードで同じビット レベルの表現を持つ型です。</span><span class="sxs-lookup"><span data-stu-id="85ffb-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="85ffb-184">そのため、ネイティブ コードとの間でマーシャリングするために別の形式に変換する必要はなく、パフォーマンスが向上するため、推奨されます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-184">As such they do not need to be converted to another format to be marshalled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="85ffb-185">**blittable 型:**</span><span class="sxs-lookup"><span data-stu-id="85ffb-185">**Blittable types:**</span></span>

- <span data-ttu-id="85ffb-186">`byte`、`sbyte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`single`、`double`</span><span class="sxs-lookup"><span data-stu-id="85ffb-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="85ffb-187">blittable 型の入れ子になっていない 1 次元配列 (たとえば `int[]`)</span><span class="sxs-lookup"><span data-stu-id="85ffb-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="85ffb-188">インスタンス フィールドに対して blittable 値型のみを持つ固定レイアウトの構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="85ffb-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="85ffb-189">固定レイアウトには `[StructLayout(LayoutKind.Sequential)]` または `[StructLayout(LayoutKind.Explicit)]` が必要です</span><span class="sxs-lookup"><span data-stu-id="85ffb-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="85ffb-190">構造体は既定で `LayoutKind.Sequential` であり、クラスは `LayoutKind.Auto` です</span><span class="sxs-lookup"><span data-stu-id="85ffb-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="85ffb-191">**blittable ではない:**</span><span class="sxs-lookup"><span data-stu-id="85ffb-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="85ffb-192">**blittable の場合がある:**</span><span class="sxs-lookup"><span data-stu-id="85ffb-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="85ffb-193">`char`、 `string`</span><span class="sxs-lookup"><span data-stu-id="85ffb-193">`char`, `string`</span></span>

<span data-ttu-id="85ffb-194">blittable 型が参照渡しされると、中間バッファーにコピーされるのではなく、マーシャラーによって単純に固定されます</span><span class="sxs-lookup"><span data-stu-id="85ffb-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="85ffb-195">(クラスは本質的に参照渡しされ、構造体は `ref` または `out` と共に使用されるときに参照渡しされます)。</span><span class="sxs-lookup"><span data-stu-id="85ffb-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="85ffb-196">1 次元配列、"**または**" `CharSet = CharSet.Unicode` が指定された `[StructLayout]` で明示的にマークされている型の一部である場合、`char`は blittable です。</span><span class="sxs-lookup"><span data-stu-id="85ffb-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="85ffb-197">別の型に含まれておらず、`[MarshalAs(UnmanagedType.LPWStr)]` でマークされた引数として渡される場合、または `[DllImport]` に `CharSet = CharSet.Unicode` が設定されている場合、`string` は blittable です。</span><span class="sxs-lookup"><span data-stu-id="85ffb-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="85ffb-198">固定された `GCHandle` を作成しようとすることで、型が blittable かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="85ffb-199">型が文字列ではない場合、または blittable と見なされる場合、`GCHandle.Alloc` は `ArgumentException` をスローします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="85ffb-200">**✔️ 実行**: 可能な限り、構造体を blittable にします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="85ffb-201">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="85ffb-201">For more information, see:</span></span>

- [<span data-ttu-id="85ffb-202">Blittable 型と非 Blittable 型</span><span class="sxs-lookup"><span data-stu-id="85ffb-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="85ffb-203">型のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="85ffb-203">Type Marshalling</span></span>](type-marshalling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="85ffb-204">マネージド オブジェクトのキープ アライブ</span><span class="sxs-lookup"><span data-stu-id="85ffb-204">Keeping managed objects alive</span></span>

<span data-ttu-id="85ffb-205">`GC.KeepAlive()` で、KeepAlive メソッドがヒットするまでオブジェクトをスコープ内に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="85ffb-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) を使用すると、マーシャラーは P/Invoke の期間、オブジェクトの有効性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="85ffb-207">メソッドのシグネチャで `IntPtr` の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="85ffb-208">事実上、`SafeHandle` によってこのクラスは置き換えられるため、代わりに使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="85ffb-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) を使用すると、マネージド オブジェクトを固定し、そのオブジェクトへのネイティブ ポインターを取得できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="85ffb-210">次に基本的なパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="85ffb-211">固定は `GCHandle` の既定ではありません。</span><span class="sxs-lookup"><span data-stu-id="85ffb-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="85ffb-212">もう 1 つの主なパターンは、ネイティブ コードを介してマネージド オブジェクトへの参照を渡し、(通常はコールバックを使用して) マネージド コードに戻すことです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="85ffb-213">パターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="85ffb-214">メモリ リークを防ぐために、`GCHandle` を明示的に解放する必要があることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="85ffb-215">一般的な Windows のデータ型</span><span class="sxs-lookup"><span data-stu-id="85ffb-215">Common Windows data types</span></span>

<span data-ttu-id="85ffb-216">Windows API で一般的に使用されるデータ型と、Windows コードを呼び出すときに使用する C# 型の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-216">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="85ffb-217">次の型は、32 ビット版と 64 ビット版の Windows でサイズは同じですが、名前は異なります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="85ffb-218">幅</span><span class="sxs-lookup"><span data-stu-id="85ffb-218">Width</span></span> | <span data-ttu-id="85ffb-219">Windows</span><span class="sxs-lookup"><span data-stu-id="85ffb-219">Windows</span></span>          | <span data-ttu-id="85ffb-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="85ffb-220">C (Windows)</span></span>          | <span data-ttu-id="85ffb-221">C#</span><span class="sxs-lookup"><span data-stu-id="85ffb-221">C#</span></span>       | <span data-ttu-id="85ffb-222">代替</span><span class="sxs-lookup"><span data-stu-id="85ffb-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="85ffb-223">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="85ffb-224">8</span><span class="sxs-lookup"><span data-stu-id="85ffb-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="85ffb-225">8</span><span class="sxs-lookup"><span data-stu-id="85ffb-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="85ffb-226">8</span><span class="sxs-lookup"><span data-stu-id="85ffb-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="85ffb-227">8</span><span class="sxs-lookup"><span data-stu-id="85ffb-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="85ffb-228">16</span><span class="sxs-lookup"><span data-stu-id="85ffb-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="85ffb-229">16</span><span class="sxs-lookup"><span data-stu-id="85ffb-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="85ffb-230">16</span><span class="sxs-lookup"><span data-stu-id="85ffb-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="85ffb-231">16</span><span class="sxs-lookup"><span data-stu-id="85ffb-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="85ffb-232">16</span><span class="sxs-lookup"><span data-stu-id="85ffb-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="85ffb-233">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="85ffb-234">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="85ffb-235">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="85ffb-236">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="85ffb-237">64</span><span class="sxs-lookup"><span data-stu-id="85ffb-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="85ffb-238">64</span><span class="sxs-lookup"><span data-stu-id="85ffb-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="85ffb-239">64</span><span class="sxs-lookup"><span data-stu-id="85ffb-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="85ffb-240">64</span><span class="sxs-lookup"><span data-stu-id="85ffb-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="85ffb-241">64</span><span class="sxs-lookup"><span data-stu-id="85ffb-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="85ffb-242">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="85ffb-243">32</span><span class="sxs-lookup"><span data-stu-id="85ffb-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |

<span data-ttu-id="85ffb-244">ポインターである次の型は、プラットフォームの幅に従います。</span><span class="sxs-lookup"><span data-stu-id="85ffb-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="85ffb-245">このような場合は `IntPtr`/`UIntPtr` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="85ffb-246">符号付きのポインター型 (`IntPtr` を使用)</span><span class="sxs-lookup"><span data-stu-id="85ffb-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="85ffb-247">符号なしのポインター型 (`UIntPtr` を使用)</span><span class="sxs-lookup"><span data-stu-id="85ffb-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="85ffb-248">C `void*` である Windows `PVOID` は `IntPtr` または `UIntPtr` のいずれかとしてマーシャリングできますが、可能であれば `void*` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="85ffb-249">Windows のデータ型</span><span class="sxs-lookup"><span data-stu-id="85ffb-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="85ffb-250">データ型の範囲</span><span class="sxs-lookup"><span data-stu-id="85ffb-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="85ffb-251">構造体</span><span class="sxs-lookup"><span data-stu-id="85ffb-251">Structs</span></span>

<span data-ttu-id="85ffb-252">マネージド構造体はスタックに対して作成され、メソッドから返されるまで削除されません。</span><span class="sxs-lookup"><span data-stu-id="85ffb-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="85ffb-253">定義上、これらは "固定" されます (GC によって移動されません)。</span><span class="sxs-lookup"><span data-stu-id="85ffb-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="85ffb-254">ネイティブ コードが、現在のメソッドの終わりを越えてポインターを使用しない場合は、アンセーフ コード ブロックで単にアドレスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="85ffb-255">blittable 型の構造体は、マーシャリング層から直接使用されるため、はるかに高パフォーマンスです。</span><span class="sxs-lookup"><span data-stu-id="85ffb-255">Blittable structs are much more performant as they can simply be used directly by the marshalling layer.</span></span> <span data-ttu-id="85ffb-256">できれば構造体を blittable 型にしてください (たとえば、`bool` を避けます)。</span><span class="sxs-lookup"><span data-stu-id="85ffb-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="85ffb-257">詳細については、「[Blittable Types (blittable 型)](#blittable-types)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="85ffb-258">構造体が blittable 型の "*場合*"、パフォーマンスを向上するために `Marshal.SizeOf<MyStruct>()` ではなく `sizeof()` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="85ffb-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="85ffb-259">前述のように、固定された `GCHandle` を作成しようとすることで、型が blittable であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="85ffb-260">型が文字列ではない場合、または blittable と見なされる場合、`GCHandle.Alloc` は `ArgumentException` をスローします。</span><span class="sxs-lookup"><span data-stu-id="85ffb-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="85ffb-261">定義内の構造体へのポインターは、`ref` で渡すか、`unsafe` と `*` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="85ffb-262">**✔️ 実行**: マネージド構造体を、公式のプラットフォーム ドキュメントまたはヘッダーで使用されているシェイプと名前にできるだけ厳密に一致させます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="85ffb-263">**✔️ 実行**: パフォーマンスを向上するには、blittable 型の構造体に `Marshal.SizeOf<MyStruct>()` ではなく C# の `sizeof()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ffb-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="85ffb-264">`INT_PTR Reserved1[2]` のような配列は、2 つの `IntPtr` フィールド、`Reserved1a` と `Reserved1b` にマーシャリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="85ffb-265">ネイティブ配列がプリミティブ型の場合、`fixed` キーワードを使用すると、もう少しわかりやすく記述できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="85ffb-266">たとえば、ネイティブ ヘッダーでは `SYSTEM_PROCESS_INFORMATION` は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="85ffb-267">C# では、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="85ffb-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="85ffb-268">ただし、固定バッファーに関する問題がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="85ffb-269">blittable ではない型の固定バッファーは正しくマーシャリングされないので、インプレース配列は複数の個々のフィールドに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ffb-269">Fixed buffers of non-blittable types won't be correctly marshalled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="85ffb-270">さらに、3.0 より前の .NET Framework および .NET Core では、固定バッファー フィールドを含む構造体が blittable 型ではない構造体内に入れ子にされている場合、固定バッファー フィールドはネイティブ コードに正しくマーシャリングされません。</span><span class="sxs-lookup"><span data-stu-id="85ffb-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshalled to native code.</span></span>

---
title: パラメーターのマーシャリングのカスタマイズ - .NET
description: .NET でパラメーターをネイティブ表現にマーシャリングする方法をカスタマイズする手順について説明します。
ms.date: 01/18/2019
ms.openlocfilehash: ff646ad942cf051ce90cd75b24c8562e536182d9
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159612"
---
# <a name="customizing-parameter-marshaling"></a><span data-ttu-id="63ccb-103">パラメーターのマーシャリングのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="63ccb-103">Customizing parameter marshaling</span></span>

<span data-ttu-id="63ccb-104">.NET ランタイムの既定のパラメーター マーシャリング動作が意図したとおりに動作しない場合は、<xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 属性を使用してパラメーターのマーシャリング方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-104">When the .NET runtime's default parameter marshaling behavior doesn't do what you want, use can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute to customize how your parameters are marshaled.</span></span>

## <a name="customizing-string-parameters"></a><span data-ttu-id="63ccb-105">文字列パラメーターのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="63ccb-105">Customizing string parameters</span></span>

<span data-ttu-id="63ccb-106">.NET には、文字列をマーシャリングするためのさまざまな形式があります。</span><span class="sxs-lookup"><span data-stu-id="63ccb-106">.NET has a variety of formats for marshaling strings.</span></span> <span data-ttu-id="63ccb-107">これらのメソッドは、C スタイルの文字列と Windows 中心の文字列の形式に関する別のセクションに分割されています。</span><span class="sxs-lookup"><span data-stu-id="63ccb-107">These methods are split into distinct sections on C-style strings and Windows-centric string formats.</span></span>

### <a name="c-style-strings"></a><span data-ttu-id="63ccb-108">C スタイルの文字列</span><span class="sxs-lookup"><span data-stu-id="63ccb-108">C-Style strings</span></span>

<span data-ttu-id="63ccb-109">これらの各形式では、null で終わる文字列をネイティブ コードに渡します。</span><span class="sxs-lookup"><span data-stu-id="63ccb-109">Each of these formats passes a null-terminated string to native code.</span></span> <span data-ttu-id="63ccb-110">これらはネイティブ文字列のエンコードが異なります。</span><span class="sxs-lookup"><span data-stu-id="63ccb-110">They differ by the encoding of the native string.</span></span>

| <span data-ttu-id="63ccb-111">`System.Runtime.InteropServices.UnmanagedType` 値</span><span class="sxs-lookup"><span data-stu-id="63ccb-111">`System.Runtime.InteropServices.UnmanagedType` value</span></span> | <span data-ttu-id="63ccb-112">エンコード</span><span class="sxs-lookup"><span data-stu-id="63ccb-112">Encoding</span></span> |
|------------------------------------------------------|----------|
| <span data-ttu-id="63ccb-113">LPStr</span><span class="sxs-lookup"><span data-stu-id="63ccb-113">LPStr</span></span> | <span data-ttu-id="63ccb-114">ANSI</span><span class="sxs-lookup"><span data-stu-id="63ccb-114">ANSI</span></span> |
| <span data-ttu-id="63ccb-115">LPUTF8Str</span><span class="sxs-lookup"><span data-stu-id="63ccb-115">LPUTF8Str</span></span> | <span data-ttu-id="63ccb-116">UTF-8</span><span class="sxs-lookup"><span data-stu-id="63ccb-116">UTF-8</span></span> |
| <span data-ttu-id="63ccb-117">LPWStr</span><span class="sxs-lookup"><span data-stu-id="63ccb-117">LPWStr</span></span> | <span data-ttu-id="63ccb-118">UTF-16</span><span class="sxs-lookup"><span data-stu-id="63ccb-118">UTF-16</span></span> |
| <span data-ttu-id="63ccb-119">LPTStr</span><span class="sxs-lookup"><span data-stu-id="63ccb-119">LPTStr</span></span> | <span data-ttu-id="63ccb-120">UTF-16</span><span class="sxs-lookup"><span data-stu-id="63ccb-120">UTF-16</span></span> |

<span data-ttu-id="63ccb-121"><xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> 形式は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="63ccb-121">The <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> format is slightly different.</span></span> <span data-ttu-id="63ccb-122">`LPWStr` と同様に、文字列を UTF-16 でエンコードされたネイティブの C スタイルの文字列にマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="63ccb-122">Like `LPWStr`, it marshals the string to a native C-style string encoded in UTF-16.</span></span> <span data-ttu-id="63ccb-123">ただし、マネージド シグネチャは参照で文字列を渡し、一致するネイティブ シグネチャは値で文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="63ccb-123">However, the managed signature has you pass in the string by reference and the matching native signature takes the string by value.</span></span> <span data-ttu-id="63ccb-124">この違いがあるため、`StringBuilder` を使用しなくても、文字列を値で受け取り、その場で変更するネイティブ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-124">This distinction allows you to use a native API that takes a string by value and modifies it in-place without having to use a `StringBuilder`.</span></span> <span data-ttu-id="63ccb-125">一致しないネイティブ シグネチャとマネージド シグネチャは混乱しやすいため、手動でこの形式を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="63ccb-125">We recommend against manually using this format since it's prone to cause confusion with the mismatching native and managed signatures.</span></span>

### <a name="windows-centric-string-formats"></a><span data-ttu-id="63ccb-126">Windows 中心の文字列形式</span><span class="sxs-lookup"><span data-stu-id="63ccb-126">Windows-centric string formats</span></span>

<span data-ttu-id="63ccb-127">COM または OLE インターフェイスとやり取りするときに、ネイティブ関数が文字列を `BSTR` 引数として受け取ることに気づかれるのではないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="63ccb-127">When interacting with COM or OLE interfaces, you'll likely find that the native functions take strings as `BSTR` arguments.</span></span> <span data-ttu-id="63ccb-128"><xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> アンマネージド型を使用して、文字列を `BSTR` としてマーシャリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-128">You can use the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> unmanaged type to marshal a string as a `BSTR`.</span></span>

<span data-ttu-id="63ccb-129">WinRT API とやり取りしている場合は、<xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> 形式を使用して文字列を `HSTRING` としてマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-129">If you're interacting with WinRT APIs, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> format to marshal a string as an `HSTRING`.</span></span>

## <a name="customizing-array-parameters"></a><span data-ttu-id="63ccb-130">配列パラメーターのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="63ccb-130">Customizing array parameters</span></span>

<span data-ttu-id="63ccb-131">.NET には、配列パラメーターをマーシャリングする方法が複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="63ccb-131">.NET also provides you multiple ways to marshal array parameters.</span></span> <span data-ttu-id="63ccb-132">C スタイルの配列を受け取る API を呼び出す場合は、<xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> アンマネージド型を使用します。</span><span class="sxs-lookup"><span data-stu-id="63ccb-132">If you're calling an API that takes a C-style array, use the <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="63ccb-133">配列内の値にカスタマイズされたマーシャリングが必要な場合は、そのために <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> 属性に対して `[MarshalAs]` フィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-133">If the values in the array need customized marshaling, you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> field on the `[MarshalAs]` attribute for that.</span></span>

<span data-ttu-id="63ccb-134">COM API を使用している場合は、おそらく配列パラメーターを `SAFEARRAY*` としてマーシャリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ccb-134">If you're using COM APIs, you'll likely have to marshal your array parameters as `SAFEARRAY*`s.</span></span> <span data-ttu-id="63ccb-135">そのためには、<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> アンマネージド型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-135">To do so, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="63ccb-136">`SAFEARRAY` の要素の既定の種類については、[`object` フィールドのカスタマイズ](./customize-struct-marshaling.md#marshaling-systemobjects)の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ccb-136">The default type of the elements of the `SAFEARRAY` can be seen in the table on [customizing `object` fields](./customize-struct-marshaling.md#marshaling-systemobjects).</span></span> <span data-ttu-id="63ccb-137"><xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> および <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> フィールドを使用すると、`SAFEARRAY` の正確な要素の種類をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-137">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

## <a name="customizing-boolean-or-decimal-parameters"></a><span data-ttu-id="63ccb-138">ブールまたは 10 進数パラメーターのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="63ccb-138">Customizing boolean or decimal parameters</span></span>

<span data-ttu-id="63ccb-139">ブールまたは 10 進数パラメーターのマーシャリングについては、「[構造体のマーシャリングのカスタマイズ](customize-struct-marshaling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ccb-139">For information on marshaling boolean or decimal parameters, see [Customizing structure marshaling](customize-struct-marshaling.md).</span></span>

## <a name="customizing-object-parameters-windows-only"></a><span data-ttu-id="63ccb-140">オブジェクト パラメーターのカスタマイズ (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="63ccb-140">Customizing object parameters (Windows-only)</span></span>

<span data-ttu-id="63ccb-141">Windows 上の .NET ランタイムには、オブジェクト パラメーターをネイティブ コードにマーシャリングするさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="63ccb-141">On Windows, the .NET runtime provides a number of different ways to marshal object parameters to native code.</span></span>

### <a name="marshaling-as-specific-com-interfaces"></a><span data-ttu-id="63ccb-142">特定の COM インターフェイスとしてのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="63ccb-142">Marshaling as specific COM interfaces</span></span>

<span data-ttu-id="63ccb-143">API が COM オブジェクトへのポインターを受け取る場合、`UnmanagedType` 型のパラメーターに次の `object` 形式のいずれかを使用して、以下のような特定のインターフェイスとしてマーシャリングするように .NET に指示できます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-143">If your API takes a pointer to a COM object, you can use any of the following `UnmanagedType` formats on an `object`-typed parameter to tell .NET to marshal as these specific interfaces:</span></span>

- `IUnknown`
- `IDispatch`
- `IInspectable`

<span data-ttu-id="63ccb-144">さらに、型が `[ComVisible(true)]` とマークされている場合、または `object` 型をマーシャリングする場合は、<xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> 形式を使用して、オブジェクトをその型の COM ビューの COM 呼び出し可能ラッパーとしてマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-144">Additionally, if your type is marked `[ComVisible(true)]` or you're marshaling the `object` type, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> format to marshal your object as a COM callable wrapper for the COM view of your type.</span></span>

### <a name="marshaling-to-a-variant"></a><span data-ttu-id="63ccb-145">`VARIANT` へのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="63ccb-145">Marshaling to a `VARIANT`</span></span>

<span data-ttu-id="63ccb-146">ネイティブ API が Win32 `VARIANT` を受け取る場合、<xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> パラメーターに `object` 形式を使用してオブジェクトを `VARIANT` としてマーシャリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-146">If your native API takes a Win32 `VARIANT`, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> format on your `object` parameter to marshal your objects as `VARIANT`s.</span></span> <span data-ttu-id="63ccb-147">.NET 型と [ 型の間のマッピングについては、`object`](customize-struct-marshaling.md#marshaling-systemobjects) フィールドのカスタマイズ`VARIANT`に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ccb-147">See the documentation on [customizing `object` fields](customize-struct-marshaling.md#marshaling-systemobjects) for a mapping between .NET types and `VARIANT` types.</span></span>

### <a name="custom-marshalers"></a><span data-ttu-id="63ccb-148">カスタム マーシャラー</span><span class="sxs-lookup"><span data-stu-id="63ccb-148">Custom marshalers</span></span>

<span data-ttu-id="63ccb-149">ネイティブ COM インターフェイスを別のマネージ型にプロジェクションする場合は、`UnmanagedType.CustomMarshaler` 形式と <xref:System.Runtime.InteropServices.ICustomMarshaler> の実装を使用して独自のカスタム マーシャリング コードを用意できます。</span><span class="sxs-lookup"><span data-stu-id="63ccb-149">If you want to project a native COM interface into a different managed type, you can use the `UnmanagedType.CustomMarshaler` format and an implementation of <xref:System.Runtime.InteropServices.ICustomMarshaler> to provide your own custom marshaling code.</span></span>

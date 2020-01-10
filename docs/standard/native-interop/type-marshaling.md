---
title: 型のマーシャリング - .NET
description: .NET が型をネイティブ表現にマーシャリングする方法について説明します。
ms.date: 01/18/2019
ms.openlocfilehash: 91b8f3d6cb53fd7a0adea7ea9669e7459e81445f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706267"
---
# <a name="type-marshaling"></a><span data-ttu-id="93e77-103">型のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="93e77-103">Type marshaling</span></span>

<span data-ttu-id="93e77-104">**マーシャリング**とは、マネージド コードとネイティブ コードの間でやり取りする必要がある場合に型を変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="93e77-104">**Marshaling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="93e77-105">マネージド コードとアンマネージド コード内の型は異なるため、マーシャリングが必要です。</span><span class="sxs-lookup"><span data-stu-id="93e77-105">Marshaling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="93e77-106">マネージコードでは、たとえば、`String`があり、アンマネージ環境の文字列には Unicode ("ワイド")、非 Unicode、null 終端、ASCII などがあります。既定では、P/Invoke サブシステムは、この記事で説明されている既定の動作に基づいて、適切な処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="93e77-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="93e77-107">しかし、追加の制御が必要な状況では、[MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) 属性を採用して、アンマネージ側で期待する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="93e77-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="93e77-108">たとえば、文字列を null で終わる ANSI 文字列として送信させる場合は、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="93e77-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a><span data-ttu-id="93e77-109">共通型をマーシャリングする場合の既定の規則</span><span class="sxs-lookup"><span data-stu-id="93e77-109">Default rules for marshaling common types</span></span>

<span data-ttu-id="93e77-110">一般的に、ランタイムは、マーシャリングするときにユーザーの必要な作業量が最小限になるように "適切な処理" を実行しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="93e77-110">Generally, the runtime tries to do the "right thing" when marshaling to require the least amount of work from you.</span></span> <span data-ttu-id="93e77-111">次の表は、パラメーターまたはフィールドで使用されるときに、各型が既定でどのようにマーシャリングされるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="93e77-111">The following tables describe how each type is marshaled by default when used in a parameter or field.</span></span> <span data-ttu-id="93e77-112">次の表がすべてのプラットフォームで正しくなるように、C99/C++ 11 固定幅の整数と文字型が使用されています。</span><span class="sxs-lookup"><span data-stu-id="93e77-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="93e77-113">このような型と同じ配置とサイズの要件を持つ任意のネイティブ型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="93e77-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="93e77-114">この最初の表は、マーシャリングが P/Invoke とフィールド マーシャリングの両方で同じであるさまざまな型のマッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="93e77-114">This first table describes the mappings for various types for whom the marshaling is the same for both P/Invoke and field marshaling.</span></span>

| <span data-ttu-id="93e77-115">.NET 型</span><span class="sxs-lookup"><span data-stu-id="93e77-115">.NET Type</span></span> | <span data-ttu-id="93e77-116">ネイティブ型</span><span class="sxs-lookup"><span data-stu-id="93e77-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="93e77-117">P/Invoke または構造体の `CharSet` に応じて、`char` または `char16_t` のいずれか。</span><span class="sxs-lookup"><span data-stu-id="93e77-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="93e77-118">[文字セットのドキュメント](charset.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93e77-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="93e77-119">P/Invoke または構造体の `CharSet` に応じて、`char*` または `char16_t*` のいずれか。</span><span class="sxs-lookup"><span data-stu-id="93e77-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="93e77-120">[文字セットのドキュメント](charset.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93e77-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="93e77-121">.NET ポインター型 (例:</span><span class="sxs-lookup"><span data-stu-id="93e77-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="93e77-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="93e77-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="93e77-123">`System.Runtime.InteropServices.SafeHandle` の派生型</span><span class="sxs-lookup"><span data-stu-id="93e77-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="93e77-124">`System.Runtime.InteropServices.CriticalHandle` の派生型</span><span class="sxs-lookup"><span data-stu-id="93e77-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="93e77-125">Win32 `BOOL` 型</span><span class="sxs-lookup"><span data-stu-id="93e77-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="93e77-126">COM `DECIMAL` 構造体</span><span class="sxs-lookup"><span data-stu-id="93e77-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="93e77-127">.NET デリゲート</span><span class="sxs-lookup"><span data-stu-id="93e77-127">.NET Delegate</span></span> | <span data-ttu-id="93e77-128">ネイティブ関数ポインター</span><span class="sxs-lookup"><span data-stu-id="93e77-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="93e77-129">Win32 `DATE` 型</span><span class="sxs-lookup"><span data-stu-id="93e77-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="93e77-130">Win32 `GUID` 型</span><span class="sxs-lookup"><span data-stu-id="93e77-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="93e77-131">パラメーターまたは構造体としてマーシャリングする場合、マーシャリングの一部のカテゴリでは既定が異なります。</span><span class="sxs-lookup"><span data-stu-id="93e77-131">A few categories of marshaling have different defaults if you're marshaling as a parameter or structure.</span></span>

| <span data-ttu-id="93e77-132">.NET 型</span><span class="sxs-lookup"><span data-stu-id="93e77-132">.NET Type</span></span> | <span data-ttu-id="93e77-133">ネイティブ型 (パラメーター)</span><span class="sxs-lookup"><span data-stu-id="93e77-133">Native Type (Parameter)</span></span> | <span data-ttu-id="93e77-134">ネイティブ型 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="93e77-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="93e77-135">.NET 配列</span><span class="sxs-lookup"><span data-stu-id="93e77-135">.NET array</span></span> | <span data-ttu-id="93e77-136">配列要素のネイティブ表現の配列の先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="93e77-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="93e77-137">使用するには `[MarshalAs]` 属性が必要です</span><span class="sxs-lookup"><span data-stu-id="93e77-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="93e77-138">`LayoutKind` が `Sequential` または `Explicit` のクラス</span><span class="sxs-lookup"><span data-stu-id="93e77-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="93e77-139">クラスのネイティブ表現へのポインター</span><span class="sxs-lookup"><span data-stu-id="93e77-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="93e77-140">クラスのネイティブ表現</span><span class="sxs-lookup"><span data-stu-id="93e77-140">The native representation of the class</span></span> |

<span data-ttu-id="93e77-141">次の表には、Windows のみの既定のマーシャリング規則が含まれています。</span><span class="sxs-lookup"><span data-stu-id="93e77-141">The following table includes the default marshaling rules that are Windows-only.</span></span> <span data-ttu-id="93e77-142">Windows 以外のプラットフォームでは、このような型をマーシャリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93e77-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="93e77-143">.NET 型</span><span class="sxs-lookup"><span data-stu-id="93e77-143">.NET Type</span></span> | <span data-ttu-id="93e77-144">ネイティブ型 (パラメーター)</span><span class="sxs-lookup"><span data-stu-id="93e77-144">Native Type (Parameter)</span></span> | <span data-ttu-id="93e77-145">ネイティブ型 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="93e77-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="93e77-146">COM インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93e77-146">COM interface</span></span> | <span data-ttu-id="93e77-147">使用するには `[MarshalAs]` 属性が必要です</span><span class="sxs-lookup"><span data-stu-id="93e77-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="93e77-148">許可しない</span><span class="sxs-lookup"><span data-stu-id="93e77-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="93e77-149">許可しない</span><span class="sxs-lookup"><span data-stu-id="93e77-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="93e77-150">許可しない</span><span class="sxs-lookup"><span data-stu-id="93e77-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="93e77-151">1601 年 1 月 1 日午前 0 時以降のティック数を表す `int64_t`</span><span class="sxs-lookup"><span data-stu-id="93e77-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="93e77-152">1601 年 1 月 1 日午前 0 時以降のティック数を表す `int64_t`</span><span class="sxs-lookup"><span data-stu-id="93e77-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="93e77-153">一部の型は、フィールドとしてではなくパラメーターとしてのみマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="93e77-153">Some types can only be marshaled as parameters and not as fields.</span></span> <span data-ttu-id="93e77-154">このような型の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="93e77-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="93e77-155">.NET 型</span><span class="sxs-lookup"><span data-stu-id="93e77-155">.NET Type</span></span> | <span data-ttu-id="93e77-156">ネイティブ型 (パラメーターのみ)</span><span class="sxs-lookup"><span data-stu-id="93e77-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="93e77-157">P/Invoke の `CharSet` に応じて、`char*` または `char16_t*` のいずれか。</span><span class="sxs-lookup"><span data-stu-id="93e77-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="93e77-158">[文字セットのドキュメント](charset.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93e77-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="93e77-159">`va_list` (Windows x86/x64/arm64 のみ)</span><span class="sxs-lookup"><span data-stu-id="93e77-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="93e77-160">これらの既定値が目的と合わない場合は、パラメーターのマーシャリング方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="93e77-160">If these defaults don't do exactly what you want, you can customize how parameters are marshaled.</span></span> <span data-ttu-id="93e77-161">[パラメーターのマーシャリング](customize-parameter-marshaling.md)の記事では、さまざまなパラメーターの型をマーシャリングする方法のカスタマイズ手順について説明しています。</span><span class="sxs-lookup"><span data-stu-id="93e77-161">The [parameter marshaling](customize-parameter-marshaling.md) article walks you through how to customize how different parameter types are marshaled.</span></span>

## <a name="default-marshaling-in-com-scenarios"></a><span data-ttu-id="93e77-162">COM シナリオでの既定のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="93e77-162">Default marshaling in COM scenarios</span></span>

<span data-ttu-id="93e77-163">.NET で COM オブジェクトのメソッドを呼び出している場合、.NET ランタイムによって共通の COM セマンティクスを満たすように、既定のマーシャリング ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="93e77-163">When you are calling methods on COM objects in .NET, the .NET runtime changes the default marshaling rules to match common COM semantics.</span></span> <span data-ttu-id="93e77-164">次の表では、COM シナリオで .NET ランタイムによって使用される規則が一覧にされます。</span><span class="sxs-lookup"><span data-stu-id="93e77-164">The following table lists the rules that .NET runtimes uses in COM scenarios:</span></span>

| <span data-ttu-id="93e77-165">.NET 型</span><span class="sxs-lookup"><span data-stu-id="93e77-165">.NET Type</span></span> | <span data-ttu-id="93e77-166">ネイティブ型 (COM メソッドの呼び出し)</span><span class="sxs-lookup"><span data-stu-id="93e77-166">Native Type (COM method calls)</span></span> |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| <span data-ttu-id="93e77-167">デリゲート型</span><span class="sxs-lookup"><span data-stu-id="93e77-167">Delegate types</span></span> | <span data-ttu-id="93e77-168">.NET Framework では `_Delegate*`。</span><span class="sxs-lookup"><span data-stu-id="93e77-168">`_Delegate*` in .NET Framework.</span></span> <span data-ttu-id="93e77-169">.NET Core では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="93e77-169">Disallowed in .NET Core.</span></span> |
| `System.Drawing.Color` | `OLECOLOR`        |
| <span data-ttu-id="93e77-170">.NET 配列</span><span class="sxs-lookup"><span data-stu-id="93e77-170">.NET array</span></span> | `SAFEARRAY`                   |
| `string[]` | <span data-ttu-id="93e77-171">`BSTR` の `SAFEARRAY`</span><span class="sxs-lookup"><span data-stu-id="93e77-171">`SAFEARRAY` of `BSTR`s</span></span>        |

## <a name="marshaling-classes-and-structs"></a><span data-ttu-id="93e77-172">クラスと構造体のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="93e77-172">Marshaling classes and structs</span></span>

<span data-ttu-id="93e77-173">型のマーシャリングの別の側面は、構造体をアンマネージ メソッドに渡す方法です。</span><span class="sxs-lookup"><span data-stu-id="93e77-173">Another aspect of type marshaling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="93e77-174">たとえば、一部のアンマネージ メソッドでは、パラメーターとして構造体が必要です。</span><span class="sxs-lookup"><span data-stu-id="93e77-174">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="93e77-175">このような場合、環境のマネージド部分に対応する構造体またはクラスを作成し、それをパラメーターとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e77-175">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="93e77-176">ただし、クラスを定義するだけでは不十分で、マーシャラーに、クラス内のフィールドをアンマネージ構造体にマップする方法を指示する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="93e77-176">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="93e77-177">ここで `StructLayout` 属性が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="93e77-177">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="93e77-178">上のコードは、`GetSystemTime()` 関数を呼び出す簡単な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="93e77-178">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="93e77-179">興味深いビットは 4 行目にあります。</span><span class="sxs-lookup"><span data-stu-id="93e77-179">The interesting bit is on line 4.</span></span> <span data-ttu-id="93e77-180">この属性は、他方 (アンマネージ) の側でクラスのフィールドを構造体に順番にマップする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="93e77-180">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="93e77-181">このことは、次の例に示すアンマネージ構造体に対応する必要があるため、フィールドの名前付けは重要でなく、それらの順番だけが重要であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="93e77-181">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="93e77-182">構造体の既定のマーシャリングでは、必要な処理が実行されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="93e77-182">Sometimes the default marshaling for your structure doesn't do what you need.</span></span> <span data-ttu-id="93e77-183">「[構造体のマーシャリングのカスタマイズ](./customize-struct-marshaling.md)」の記事では、構造体のマーシャリング方法をカスタマイズする手順が説明されています。</span><span class="sxs-lookup"><span data-stu-id="93e77-183">The [Customizing structure marshaling](./customize-struct-marshaling.md) article teaches you how to customize how your structure is marshaled.</span></span>

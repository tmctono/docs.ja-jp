---
title: 文字列に対する既定のマーシャリング
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d39d4dfd5413b95300b70f27437bd27ca2d67a20
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452387"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="6c251-102">文字列に対する既定のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="6c251-102">Default Marshaling for Strings</span></span>

<span data-ttu-id="6c251-103"><xref:System.String?displayProperty=nameWithType> と <xref:System.Text.StringBuilder?displayProperty=nameWithType> クラスのマーシャリング動作は類似しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="6c251-104">文字列は、COM スタイル `BSTR` 型または null で終わる文字列 (null 文字で終わる文字配列) としてマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="6c251-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="6c251-105">文字列内の文字は、Unicode (Windows システムでの既定値) または ANSI としてマーシャリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c251-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="6c251-106">インターフェイスで使用される文字列</span><span class="sxs-lookup"><span data-stu-id="6c251-106">Strings Used in Interfaces</span></span>

<span data-ttu-id="6c251-107">次の表は、アンマネージ コードへのメソッド引数としてマーシャリングするときの、文字列データ型のマーシャリングのオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-107">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="6c251-108"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は、COM インターフェイスへの文字列をマーシャリングする <xref:System.Runtime.InteropServices.UnmanagedType> 列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c251-108">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="6c251-109">列挙型</span><span class="sxs-lookup"><span data-stu-id="6c251-109">Enumeration type</span></span>|<span data-ttu-id="6c251-110">アンマネージ形式の説明</span><span class="sxs-lookup"><span data-stu-id="6c251-110">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="6c251-111">`UnmanagedType.BStr` (既定値)</span><span class="sxs-lookup"><span data-stu-id="6c251-111">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="6c251-112">長さと Unicode 文字がプレフィックスされた COM スタイル `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="6c251-112">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="6c251-113">ANSI 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-113">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c251-114">Unicode 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-114">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="6c251-115">この表は <xref:System.String> に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c251-115">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="6c251-116"><xref:System.Text.StringBuilder> の場合、許可される唯一のオプションは `UnmanagedType.LPStr` と `UnmanagedType.LPWStr` です。</span><span class="sxs-lookup"><span data-stu-id="6c251-116">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="6c251-117">以下の例では、`IStringWorker` インターフェイスで宣言された文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="6c251-117">The following example shows strings declared in the `IStringWorker` interface.</span></span>

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

<span data-ttu-id="6c251-118">以下の例では、タイプ ライブラリに記述された対応するインターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="6c251-118">The following example shows the corresponding interface described in a type library.</span></span>

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="6c251-119">プラットフォーム呼び出しで使用される文字列</span><span class="sxs-lookup"><span data-stu-id="6c251-119">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="6c251-120">プラットフォーム呼び出しは、文字列の引数を、.NET Framework 形式 (Unicode) から、プラットフォーム アンマネージ形式に変換してコピーします。</span><span class="sxs-lookup"><span data-stu-id="6c251-120">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="6c251-121">文字列は不変であり、呼び出しが戻るときに、アンマネージド メモリから元のマネージド メモリにコピーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c251-121">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="6c251-122">次の表は、文字列をプラットフォーム呼び出しのメソッド引数としてマーシャリングする際のマーシャリング オプションをリストしています。</span><span class="sxs-lookup"><span data-stu-id="6c251-122">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="6c251-123"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は、文字列をマーシャリングする <xref:System.Runtime.InteropServices.UnmanagedType> 列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c251-123">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="6c251-124">列挙型</span><span class="sxs-lookup"><span data-stu-id="6c251-124">Enumeration type</span></span>|<span data-ttu-id="6c251-125">アンマネージ形式の説明</span><span class="sxs-lookup"><span data-stu-id="6c251-125">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="6c251-126">長さと ANSI 文字がプレフィックスされた COM スタイル `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="6c251-126">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="6c251-127">長さと Unicode 文字がプレフィックスされた COM スタイル `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="6c251-127">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="6c251-128">`UnmanagedType.LPStr` (既定値)</span><span class="sxs-lookup"><span data-stu-id="6c251-128">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="6c251-129">ANSI 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-129">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="6c251-130">プラットフォーム依存文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-130">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="6c251-131">UTF-8 でエンコードされた文字の NULL で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-131">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c251-132">Unicode 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-132">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="6c251-133">長さとプラットフォーム依存文字がプレフィックスされた COM スタイル `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="6c251-133">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="6c251-134">Visual Basic .NET で、アンマネージド コードの文字列を変更し、結果をマネージド コードに反映できるようにする値。</span><span class="sxs-lookup"><span data-stu-id="6c251-134">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="6c251-135">この値は、プラットフォーム呼び出しでだけサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6c251-135">This value is supported only for platform invoke.</span></span> <span data-ttu-id="6c251-136">これは、`ByVal` 文字列に対する Visual Basic の既定値です。</span><span class="sxs-lookup"><span data-stu-id="6c251-136">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="6c251-137">この表は <xref:System.String> に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c251-137">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="6c251-138"><xref:System.Text.StringBuilder> の場合、許可される唯一のオプションは `LPStr`、`LPTStr`、および `LPWStr` です。</span><span class="sxs-lookup"><span data-stu-id="6c251-138">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="6c251-139">次の型定義は、プラットフォーム呼び出しで `MarshalAsAttribute` を使用するための正しい方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-139">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a><span data-ttu-id="6c251-140">構造体で使用される文字列</span><span class="sxs-lookup"><span data-stu-id="6c251-140">Strings Used in Structures</span></span>

<span data-ttu-id="6c251-141">文字列は構造体の有効なメンバーです。ただし、<xref:System.Text.StringBuilder> バッファーは構造体では無効です。</span><span class="sxs-lookup"><span data-stu-id="6c251-141">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="6c251-142">次の表は、型をフィールドとしてマーシャリングするときの、<xref:System.String> データ型のマーシャリングのオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-142">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="6c251-143"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は、文字列をフィールドにマーシャリングする <xref:System.Runtime.InteropServices.UnmanagedType> 列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c251-143">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="6c251-144">列挙型</span><span class="sxs-lookup"><span data-stu-id="6c251-144">Enumeration type</span></span>|<span data-ttu-id="6c251-145">アンマネージ形式の説明</span><span class="sxs-lookup"><span data-stu-id="6c251-145">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="6c251-146">長さと Unicode 文字がプレフィックスされた COM スタイル `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="6c251-146">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="6c251-147">`UnmanagedType.LPStr` (既定値)</span><span class="sxs-lookup"><span data-stu-id="6c251-147">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="6c251-148">ANSI 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-148">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="6c251-149">プラットフォーム依存文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-149">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="6c251-150">UTF-8 でエンコードされた文字の NULL で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-150">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c251-151">Unicode 文字の null で終わる配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c251-151">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="6c251-152">固定長の文字配列。配列の型は、包含構造体の文字セットによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6c251-152">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="6c251-153">`ByValTStr` 型は、構造体に定義されているインライン固定長文字配列で使用します。</span><span class="sxs-lookup"><span data-stu-id="6c251-153">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="6c251-154">その他の型は、文字列へのポインターを含む構造体に含まれている文字列参照に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c251-154">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="6c251-155">包含構造体に適用される <xref:System.Runtime.InteropServices.StructLayoutAttribute> の `CharSet` 引数によって、構造体内の文字列の文字形式が決まります。</span><span class="sxs-lookup"><span data-stu-id="6c251-155">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="6c251-156">以下の構造体の例には、文字列参照とインライン文字列、そして ANSI、Unicode、およびプラットフォーム依存文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c251-156">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="6c251-157">タイプ ライブラリ内のこれらの構造体の表現を次の C++ コードに示します。</span><span class="sxs-lookup"><span data-stu-id="6c251-157">The representation of these structures in a type library is shown in the following C++ code:</span></span>

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

<span data-ttu-id="6c251-158">次の例は、<xref:System.Runtime.InteropServices.MarshalAsAttribute> を使用して、同一の構造体を複数の異なる形式で定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-158">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

```vb
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _
Structure StringInfoA
    <MarshalAs(UnmanagedType.LPStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _
Structure StringInfoW
    <MarshalAs(UnmanagedType.LPWStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
<MarshalAs(UnmanagedType.BStr)> Public f3 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _
Structure StringInfoT
    <MarshalAs(UnmanagedType.LPTStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure
```

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="6c251-159">固定長文字列バッファー</span><span class="sxs-lookup"><span data-stu-id="6c251-159">Fixed-Length String Buffers</span></span>

<span data-ttu-id="6c251-160">状況によっては、固定長の文字列バッファーを、操作するためにアンマネージ コードに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c251-160">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="6c251-161">この場合、呼び出し先は渡されたバッファーの内容を修正できないので、単に文字列を渡すだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="6c251-161">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="6c251-162">文字列が参照によって渡された場合でも、バッファーを特定のサイズに初期化する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="6c251-162">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="6c251-163">この解決策は、<xref:System.Text.StringBuilder> バッファーを <xref:System.String> ではなく引数として渡すことです。</span><span class="sxs-lookup"><span data-stu-id="6c251-163">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="6c251-164">呼び出し先は、`StringBuilder` の容量を超えない範囲で、`StringBuilder` を逆参照したり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c251-164">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6c251-165">また、固定長に初期化することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c251-165">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="6c251-166">たとえば、`StringBuilder` バッファーを初期化してその容量を `N` にする場合、マーシャラーは (`N`+1) 文字のサイズのバッファーを提供します。</span><span class="sxs-lookup"><span data-stu-id="6c251-166">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="6c251-167">+1 は、アンマネージ文字列に null 終了文字があることをしめしています。`StringBuilder` にはそれがありません。</span><span class="sxs-lookup"><span data-stu-id="6c251-167">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="6c251-168">たとえば、Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API 関数 (*winuser.h* で定義されています) では、関数からウィンドウのテキストが出力される固定長の文字バッファーを呼び出し元が渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c251-168">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="6c251-169">`LpString` は、呼び出し元が割り当てたサイズ `nMaxCount` のバッファーを示します。</span><span class="sxs-lookup"><span data-stu-id="6c251-169">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="6c251-170">呼び出し元は、バッファーを割り当てて、`nMaxCount` 引数を割り当てられたバッファーのサイズに設定することが期待されています。</span><span class="sxs-lookup"><span data-stu-id="6c251-170">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="6c251-171">次の例は、*winuser.h* で定義されている `GetWindowText` 関数宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-171">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="6c251-172">呼び出し先は、`StringBuilder` の容量を超えない範囲で、`StringBuilder` を逆参照したり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c251-172">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6c251-173">次のコード例は、`StringBuilder` を固定長に初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c251-173">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a><span data-ttu-id="6c251-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c251-174">See also</span></span>

- [<span data-ttu-id="6c251-175">既定のマーシャリング動作</span><span class="sxs-lookup"><span data-stu-id="6c251-175">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="6c251-176">マーシャリング (文字列の)</span><span class="sxs-lookup"><span data-stu-id="6c251-176">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="6c251-177">Blittable 型と非 Blittable 型</span><span class="sxs-lookup"><span data-stu-id="6c251-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="6c251-178">[方向属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6c251-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="6c251-179">コピーと固定</span><span class="sxs-lookup"><span data-stu-id="6c251-179">Copying and Pinning</span></span>](copying-and-pinning.md)

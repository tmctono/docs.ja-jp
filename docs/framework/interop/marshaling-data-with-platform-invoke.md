---
title: プラットフォーム呼び出しによるデータのマーシャリング
description: .NET でプラットフォーム呼び出しを使用してデータをマーシャリングします。 Windows API および C スタイルの関数で使用されるデータ型の一覧を参照し、対応する .NET マネージド型を検索します。
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
ms.openlocfilehash: 27045790780c1eef9537bdf7e52deb579e2b467c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904105"
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="6d462-104">プラットフォーム呼び出しによるデータのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="6d462-104">Marshaling Data with Platform Invoke</span></span>

<span data-ttu-id="6d462-105">アンマネージド ライブラリからエクスポートされた関数を呼び出すには、.NET Framework アプリケーションで、マネージド コード内にアンマネージド 関数を表す関数プロトタイプが必要です。</span><span class="sxs-lookup"><span data-stu-id="6d462-105">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="6d462-106">プラットフォーム呼び出しがデータを正しくマーシャリングできるようにするプロトタイプを作成するには、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d462-106">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>

- <span data-ttu-id="6d462-107"><xref:System.Runtime.InteropServices.DllImportAttribute> 属性をマネージド コード内の静的関数またはメソッドに適用します。</span><span class="sxs-lookup"><span data-stu-id="6d462-107">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>

- <span data-ttu-id="6d462-108">アンマネージド データ型をマネージド データ型に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6d462-108">Substitute managed data types for unmanaged data types.</span></span>

<span data-ttu-id="6d462-109">アンマネージド 関数に付属のドキュメントを使用して、属性とその省略可能なフィールドを適用し、アンマネージド型をマネージド データ型に置き換えることによって、同等のマネージド プロトタイプを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d462-109">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="6d462-110"><xref:System.Runtime.InteropServices.DllImportAttribute> を適用する方法の詳細については、「[アンマネージ DLL 関数の処理](consuming-unmanaged-dll-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d462-110">For instructions about how to apply the <xref:System.Runtime.InteropServices.DllImportAttribute>, see [Consuming Unmanaged DLL Functions](consuming-unmanaged-dll-functions.md).</span></span>

<span data-ttu-id="6d462-111">このセクションでは、アンマネージド ライブラリによってエクスポートされた関数に引数を渡し、その関数からの戻り値を受け取るための、マネージド関数のプロトタイプを作成する方法を示すサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="6d462-111">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="6d462-112">サンプルではまた、いつ <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性と <xref:System.Runtime.InteropServices.Marshal> クラスを使用して明示的にデータをマーシャリングするかをも示しています。</span><span class="sxs-lookup"><span data-stu-id="6d462-112">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>

## <a name="platform-invoke-data-types"></a><span data-ttu-id="6d462-113">プラットフォーム呼び出しのデータ型</span><span class="sxs-lookup"><span data-stu-id="6d462-113">Platform invoke data types</span></span>

<span data-ttu-id="6d462-114">次の表は、Windows API と C スタイルの関数で使用されるデータ型を一覧で示しています。</span><span class="sxs-lookup"><span data-stu-id="6d462-114">The following table lists data types used in the Windows APIs and C-style functions.</span></span> <span data-ttu-id="6d462-115">多くのアンマネージ ライブラリには、これらのデータ型をパラメーターや戻り値として渡す関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d462-115">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="6d462-116">3 番目の列には、マネージド コードで使用する、対応する .NET Framework の組み込みの値型またはクラスを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="6d462-116">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="6d462-117">場合によっては、表にリストされた型を、同じサイズの型に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="6d462-117">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>

|<span data-ttu-id="6d462-118">Windows API でのアンマネージ型</span><span class="sxs-lookup"><span data-stu-id="6d462-118">Unmanaged type in Windows APIs</span></span>|<span data-ttu-id="6d462-119">アンマネージ C 言語型</span><span class="sxs-lookup"><span data-stu-id="6d462-119">Unmanaged C language type</span></span>|<span data-ttu-id="6d462-120">マネージド型</span><span class="sxs-lookup"><span data-stu-id="6d462-120">Managed type</span></span>|<span data-ttu-id="6d462-121">説明</span><span class="sxs-lookup"><span data-stu-id="6d462-121">Description</span></span>|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|<span data-ttu-id="6d462-122">値を返さない関数に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d462-122">Applied to a function that does not return a value.</span></span>|
|`HANDLE`|`void *`|<span data-ttu-id="6d462-123"><xref:System.IntPtr?displayProperty=nameWithType> または <xref:System.UIntPtr?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-123"><xref:System.IntPtr?displayProperty=nameWithType> or <xref:System.UIntPtr?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-124">32 ビット Windows オペレーティング システム、64 ビット Windows オペレーティング システムで 64 ビットに 32 ビットです。</span><span class="sxs-lookup"><span data-stu-id="6d462-124">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="6d462-125">8 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-125">8 bits</span></span>|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="6d462-126">16 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-126">16 bits</span></span>|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="6d462-127">16 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-127">16 bits</span></span>|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="6d462-128">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-128">32 bits</span></span>|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6d462-129">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-129">32 bits</span></span>|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="6d462-130">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-130">32 bits</span></span>|
|`BOOL`|`long`|<span data-ttu-id="6d462-131"><xref:System.Boolean?displayProperty=nameWithType> または <xref:System.Int32?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-131"><xref:System.Boolean?displayProperty=nameWithType> or <xref:System.Int32?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-132">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-132">32 bits</span></span>|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6d462-133">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-133">32 bits</span></span>|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6d462-134">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-134">32 bits</span></span>|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="6d462-135">ANSI で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-135">Decorate with ANSI.</span></span>|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="6d462-136">Unicode で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-136">Decorate with Unicode.</span></span>|
|`LPSTR`|`char *`|<span data-ttu-id="6d462-137"><xref:System.String?displayProperty=nameWithType> または <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-137"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-138">ANSI で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-138">Decorate with ANSI.</span></span>|
|`LPCSTR`|`const char *`|<span data-ttu-id="6d462-139"><xref:System.String?displayProperty=nameWithType> または <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-139"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-140">ANSI で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-140">Decorate with ANSI.</span></span>|
|`LPWSTR`|`wchar_t *`|<span data-ttu-id="6d462-141"><xref:System.String?displayProperty=nameWithType> または <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-141"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-142">Unicode で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-142">Decorate with Unicode.</span></span>|
|`LPCWSTR`|`const wchar_t *`|<span data-ttu-id="6d462-143"><xref:System.String?displayProperty=nameWithType> または <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6d462-143"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="6d462-144">Unicode で装飾します。</span><span class="sxs-lookup"><span data-stu-id="6d462-144">Decorate with Unicode.</span></span>|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="6d462-145">32 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-145">32 bits</span></span>|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="6d462-146">64 ビット</span><span class="sxs-lookup"><span data-stu-id="6d462-146">64 bits</span></span>|

<span data-ttu-id="6d462-147">Visual Basic、C#、および C++ での対応する型については、「[.NET Framework クラス ライブラリの概要](../../standard/class-library-overview.md#system-namespace)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d462-147">For corresponding types in Visual Basic, C#, and C++, see the [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace).</span></span>

## <a name="pinvokelibdll"></a><span data-ttu-id="6d462-148">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="6d462-148">PinvokeLib.dll</span></span>

<span data-ttu-id="6d462-149">次のコードでは、Pinvoke.dll によって提供されるライブラリ関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="6d462-149">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="6d462-150">このセクションで説明される多くのサンプルでは、このライブラリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6d462-150">Many samples described in this section call this library.</span></span>

### <a name="example"></a><span data-ttu-id="6d462-151">例</span><span class="sxs-lookup"><span data-stu-id="6d462-151">Example</span></span>

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]

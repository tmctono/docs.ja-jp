---
title: クラス、構造体、および共用体のマーシャリング
description: クラス、構造体、および共用体をマーシャリングする方法を確認します。 クラス、入れ子になった構造体を含む構造体、構造体の配列、および共用体のマーシャリング サンプルを表示します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 5e616b5bb513939cadd8fe5c72675ba0b6e070a3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621523"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="0f3e1-104">クラス、構造体、および共用体のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="0f3e1-104">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="0f3e1-105">クラスと構造体は、.NET Framework では類似しています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-105">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="0f3e1-106">どちらもフィールド、プロパティ、およびイベントを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-106">Both can have fields, properties, and events.</span></span> <span data-ttu-id="0f3e1-107">静的メソッドと非静的メソッドを持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-107">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="0f3e1-108">1 つの重要な違いは、構造体は値型でクラスは参照型であることです。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-108">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="0f3e1-109">次の表は、クラス、構造体、および共用体のマーシャリング オプションをリストし、それぞれの使用方法を説明し、対応するプラットフォーム呼び出しサンプルへのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-109">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="0f3e1-110">種類</span><span class="sxs-lookup"><span data-stu-id="0f3e1-110">Type</span></span>|<span data-ttu-id="0f3e1-111">説明</span><span class="sxs-lookup"><span data-stu-id="0f3e1-111">Description</span></span>|<span data-ttu-id="0f3e1-112">サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-112">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="0f3e1-113">値によるクラス。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-113">Class by value.</span></span>|<span data-ttu-id="0f3e1-114">整数のメンバーを含むクラスは、管理対象クラスと同じように、In/Out パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-114">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="0f3e1-115">SysTime サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-115">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="0f3e1-116">値による構造体。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-116">Structure by value.</span></span>|<span data-ttu-id="0f3e1-117">In パラメーターとして構造体を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-117">Passes structures as In parameters.</span></span>|[<span data-ttu-id="0f3e1-118">構造体サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-118">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="0f3e1-119">参照による構造体</span><span class="sxs-lookup"><span data-stu-id="0f3e1-119">Structure by reference.</span></span>|<span data-ttu-id="0f3e1-120">In/Out パラメーターとして構造体を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-120">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="0f3e1-121">[OSInfo サンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f3e1-121">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="0f3e1-122">入れ子になった構造体を含む構造体 (フラット化)。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-122">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="0f3e1-123">アンマネージ関数で入れ子になった構造体を含む構造体を表すクラスを渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-123">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="0f3e1-124">マネージド プロトタイプで構造体は 1 つの大きな構造体にフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-124">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="0f3e1-125">FindFile サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-125">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="0f3e1-126">別の構造体へのポインターを持つ構造体。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-126">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="0f3e1-127">2 番目の構造体へのポインターをメンバーとして含む構造体を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-127">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="0f3e1-128">構造体サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-128">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="0f3e1-129">値による整数のある構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-129">Array of structures with integers by value.</span></span>|<span data-ttu-id="0f3e1-130">In/Out パラメーターとして整数のみを含む構造体の配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-130">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="0f3e1-131">配列のメンバーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-131">Members of the array can be changed.</span></span>|[<span data-ttu-id="0f3e1-132">配列サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-132">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="0f3e1-133">参照による整数と文字列のある構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-133">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="0f3e1-134">Out パラメーターとして整数と文字列を含む構造体の配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-134">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="0f3e1-135">呼び出された関数は、配列のメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-135">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="0f3e1-136">OutArrayOfStructs サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-136">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="0f3e1-137">値型の共用体。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-137">Unions with value types.</span></span>|<span data-ttu-id="0f3e1-138">値型 (整数および倍精度) の共用体を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-138">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="0f3e1-139">Unions サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-139">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="0f3e1-140">混合型の共用体。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-140">Unions with mixed types.</span></span>|<span data-ttu-id="0f3e1-141">混合型 (整数および文字列) の共用体を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-141">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="0f3e1-142">Unions サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-142">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="0f3e1-143">プラットフォーム固有のレイアウトを持つ構造体。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-143">Struct with platform-specific layout.</span></span>|<span data-ttu-id="0f3e1-144">ネイティブ パッキング定義を持つ型を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-144">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="0f3e1-145">プラットフォームのサンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-145">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="0f3e1-146">構造体の null 値。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-146">Null values in structure.</span></span>|<span data-ttu-id="0f3e1-147">値型への参照の代わりに null 参照 (Visual Basic では **Nothing**) を渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-147">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="0f3e1-148">[HandleRef サンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0f3e1-148">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="0f3e1-149">構造体のサンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-149">Structures sample</span></span>

<span data-ttu-id="0f3e1-150">このサンプルでは、2 番目の構造体を指す構造体を渡す方法、埋め込み構造体のある構造体を渡す方法、および埋め込み配列のある構造体を渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-150">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="0f3e1-151">Structs のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-151">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="0f3e1-152">PinvokeLib.dll からエクスポートされる **TestStructInStruct**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-152">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="0f3e1-153">PinvokeLib.dll からエクスポートされる **TestStructInStruct3**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-153">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="0f3e1-154">PinvokeLib.dll からエクスポートされる **TestArrayInStruct**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-154">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="0f3e1-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) はカスタム アンマネージ ライブラリであり、上記の関数および 4 つの構造体(**MYPERSON**、**MYPERSON2**、**MYPERSON3**、**MYARRAYSTRUCT**) に関する実装を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="0f3e1-156">これらの構造体には次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-156">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="0f3e1-157">マネージド `MyPerson`、`MyPerson2`、`MyPerson3`、および `MyArrayStruct` 構造体には、以下の特性があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-157">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="0f3e1-158">`MyPerson` には文字列メンバーだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-158">`MyPerson` contains only string members.</span></span> <span data-ttu-id="0f3e1-159">[CharSet](specifying-a-character-set.md) フィールドは、アンマネージ関数に渡されるとき、文字列を ANSI 形式に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-159">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="0f3e1-160">`MyPerson2` には、`MyPerson` 構造体への **IntPtr** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-160">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="0f3e1-161">コードが **unsafe** とマークされている場合を除いて、.NET Framework アプリケーションではポインターを使用しないため、**IntPtr** 型は元のポインターをアンマネージ構造体に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-161">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="0f3e1-162">`MyPerson3` には `MyPerson` が埋め込み構造体として含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-162">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="0f3e1-163">別の構造体に埋め込まれた構造体は、埋め込み構造体の要素をメインの構造体に直接配置することでフラット化することができます。またはこのサンプルのように、埋め込み構造体のままにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-163">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="0f3e1-164">`MyArrayStruct` には整数の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-164">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="0f3e1-165"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は <xref:System.Runtime.InteropServices.UnmanagedType> 列挙値を **ByValArray** に設定します。これは配列内の要素の数を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-165">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="0f3e1-166">このサンプル内のすべての構造体で、各メンバーが出現する順番でメモリ内に順次配列されることを保証するために、<xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性が適用されています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-166">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="0f3e1-167">`NativeMethods` クラスには、`App` クラスによって呼び出される `TestStructInStruct`、`TestStructInStruct3`、および `TestArrayInStruct` メソッドのマネージド プロトタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-167">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="0f3e1-168">各プロトタイプは、1 つのパラメーターを以下のように宣言します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-168">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="0f3e1-169">`TestStructInStruct` は型 `MyPerson2` への参照をそのパラメーターとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-169">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="0f3e1-170">`TestStructInStruct3` は型 `MyPerson3` をそのパラメーターとして宣言し、パラメーターを値によって渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-170">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="0f3e1-171">`TestArrayInStruct` は型 `MyArrayStruct` への参照をそのパラメーターとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-171">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="0f3e1-172">メソッドへの引数としての構造体は、パラメーターに **ref** (Visual Basic では **ByRef**) キーワードが含まれない限り、値によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-172">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="0f3e1-173">たとえば、`TestStructInStruct` メソッドは型 `MyPerson2` のオブジェクトへの参照 (アドレスの値) をアンマネージ コードに渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-173">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="0f3e1-174">`MyPerson2` が指定する構造体を操作するために、サンプルは指定したサイズのバッファーを作成し、<xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> と <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> のメソッドを結合することでそのアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-174">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="0f3e1-175">次に、サンプルはマネージド構造体の内容をアンマネージド バッファーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-175">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="0f3e1-176">最後に、サンプルは <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> メソッドを使用してアンマネージド バッファーからマネージド オブジェクトにデータをマーシャリングし、<xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> メソッドを使用してメモリのアンマネージド ブロックを解放します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-176">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="0f3e1-177">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="0f3e1-177">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="0f3e1-178">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f3e1-178">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="0f3e1-179">FindFile サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-179">FindFile sample</span></span>

<span data-ttu-id="0f3e1-180">このサンプルでは、2 番目の埋め込み構造体を含む構造体をアンマネージ関数に渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-180">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="0f3e1-181">また、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して構造体内に固定長配列を宣言する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-181">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="0f3e1-182">このサンプルでは、埋め込み構造体の要素が親の構造体に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-182">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="0f3e1-183">フラット化しない埋め込み構造体のサンプルについては、「[構造体のサンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-183">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="0f3e1-184">FindFile のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-184">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="0f3e1-185">Kernel32.dll からエクスポートされる **FindFirstFile**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-185">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="0f3e1-186">関数に渡された元の構造体には、次に示す要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-186">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="0f3e1-187">このサンプルでは、`FindData` クラスに、元の構造体と埋め込み構造体の各要素に対応するデータ メンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-187">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="0f3e1-188">このクラスは、元の 2 つの文字バッファーを文字列に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-188">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="0f3e1-189">**MarshalAsAttribute** は <xref:System.Runtime.InteropServices.UnmanagedType> 列挙を **ByValTStr** に設定します。これは、アンマネージ構造体に出現するインラインの固定長文字配列を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-189">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="0f3e1-190">`NativeMethods` クラスには `FindFirstFile` メソッドのマネージド プロトタイプが含まれます。このメソッドは `FindData` クラスをパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-190">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="0f3e1-191">参照型のクラスは既定では In パラメーターとして渡されるため、パラメーターは <xref:System.Runtime.InteropServices.InAttribute> と <xref:System.Runtime.InteropServices.OutAttribute> の属性で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-191">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="0f3e1-192">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="0f3e1-192">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="0f3e1-193">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f3e1-193">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="0f3e1-194">Unions サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-194">Unions sample</span></span>

<span data-ttu-id="0f3e1-195">このサンプルでは、値型のみを含む構造体、および値型と文字列を含む構造体を、共用体が予期されているアンマネージ関数のパラメーターとして渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-195">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="0f3e1-196">共用体は、2 つ以上の変数が共有できるメモリ位置を表します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-196">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="0f3e1-197">Unions のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-197">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="0f3e1-198">PinvokeLib.dll からエクスポートされる **TestUnion**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-198">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="0f3e1-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) はカスタム アンマネージ ライブラリであり、上記の関数および 2 つの共用体 **MYUNION** および **MYUNION2** に関する実装を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="0f3e1-200">共用体には以下の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-200">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="0f3e1-201">マネージド コードでは、共用体は構造体として定義されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-201">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="0f3e1-202">`MyUnion` 構造体には、メンバーとして整数と倍精度の 2 つの値型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-202">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="0f3e1-203"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性は、各データ メンバーの正確な位置を制御するために設定されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-203">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="0f3e1-204"><xref:System.Runtime.InteropServices.FieldOffsetAttribute> 属性は、共用体のアンマネージ表現内に、フィールドの物理的な位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-204">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="0f3e1-205">両方のメンバーに同じオフセット値があるので、メンバーはメモリの同じ部分を定義できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-205">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="0f3e1-206">`MyUnion2_1` と `MyUnion2_2` には、それぞれ値型 (整数) と文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-206">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="0f3e1-207">マネージド コードでは、値型と参照型が重複することは許可されません。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-207">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="0f3e1-208">このサンプルでは、同じアンマネージ関数を呼び出すときに呼び出し元が両方の型を使用できるようにするため、メソッドのオーバーロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-208">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="0f3e1-209">`MyUnion2_1` のレイアウトは明示的で、正確なオフセット値を持っています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-209">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="0f3e1-210">これに対し、`MyUnion2_2` にはシーケンシャル レイアウトがあります。参照型では明示的なレイアウトが許可されていないためです。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-210">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="0f3e1-211"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は <xref:System.Runtime.InteropServices.UnmanagedType> 列挙を **ByValTStr** に設定します。これは、共用体のアンマネージ表現に出現するインラインの固定長文字配列を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-211">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="0f3e1-212">`NativeMethods` クラスには、`TestUnion` と `TestUnion2` メソッドのプロトタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-212">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="0f3e1-213">`TestUnion2` は `MyUnion2_1` または `MyUnion2_2` をパラメーターとして宣言するためにオーバーロードされています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-213">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="0f3e1-214">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="0f3e1-214">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="0f3e1-215">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f3e1-215">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="0f3e1-216">プラットフォームのサンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-216">Platform sample</span></span>

<span data-ttu-id="0f3e1-217">シナリオによっては、`struct` と `union` のレイアウトが、対象となるプラットフォームによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-217">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="0f3e1-218">たとえば、COM シナリオで定義された [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) 型について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-218">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="0f3e1-219">上の `struct` は、型のメモリ レイアウトに影響を与える Windows のヘッダーを使用して宣言されています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-219">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="0f3e1-220">マネージド環境で定義されている場合、ネイティブ コードと適切に相互運用するには、これらのレイアウトの詳細が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-220">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="0f3e1-221">32 ビット プロセスでのこの型の正しいマネージド定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-221">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="0f3e1-222">64 ビット プロセスでは、サイズとフィールドの "*両方の*" オフセットが異なります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-222">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="0f3e1-223">正しいレイアウトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-223">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="0f3e1-224">相互運用シナリオでネイティブ レイアウトを適切に考慮しないと、ランダムなクラッシュや、場合によっては不適切な計算が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-224">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="0f3e1-225">既定では、.NET アセンブリは .NET ランタイムの 32 ビット バージョンと 64 ビット バージョンの両方で実行できます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-225">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="0f3e1-226">アプリは、実行時まで待機して、前のどの定義を使用するかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-226">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="0f3e1-227">次のコード スニペットは、実行時に 32 ビットと 64 ビットの定義をどのようにして選択するかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-227">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="0f3e1-228">SysTime サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-228">SysTime sample</span></span>

<span data-ttu-id="0f3e1-229">このサンプルでは、構造体へのポインターを要求する、クラスへのポインターをアンマネージ関数に渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-229">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="0f3e1-230">SysTime のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-230">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="0f3e1-231">Kernel32.dll からエクスポートされる **GetSystemTime**。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-231">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="0f3e1-232">関数に渡された元の構造体には、次に示す要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-232">The original structure passed to the function contains the following elements:</span></span>

```cpp
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

<span data-ttu-id="0f3e1-233">このサンプルでは、`SystemTime` クラスの中には、クラス メンバーとして表される、元の構造体の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-233">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="0f3e1-234">各メンバーが出現する順番でメモリ内に順次配列されることを保証するために、 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-234">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="0f3e1-235">`NativeMethods` クラスには `GetSystemTime` メソッドのマネージド プロトタイプが含まれます。このメソッドは既定では `SystemTime` クラスを In/Out パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-235">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="0f3e1-236">参照型のクラスは既定では In パラメーターとして渡されるため、パラメーターは <xref:System.Runtime.InteropServices.InAttribute> と <xref:System.Runtime.InteropServices.OutAttribute> の属性で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-236">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="0f3e1-237">呼び出し元が結果を受け取るには、これらの[方向属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))を明示的に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-237">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="0f3e1-238">`App` クラスは、`SystemTime` クラスの新しいインスタンスを作成して、そのデータ フィールドにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-238">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="0f3e1-239">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-239">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="0f3e1-240">OutArrayOfStructs サンプル</span><span class="sxs-lookup"><span data-stu-id="0f3e1-240">OutArrayOfStructs sample</span></span>

<span data-ttu-id="0f3e1-241">このサンプルでは、整数および文字列をアンマネージ関数への Out パラメーターとして含む構造体の配列を渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-241">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="0f3e1-242">このサンプルでは、<xref:System.Runtime.InteropServices.Marshal> クラスを使用することにより、およびアンセーフ コードを使用することにより、ネイティブ関数を呼び出す方法を例示します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-242">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="0f3e1-243">このサンプルでは、[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) で定義されていて、ソース ファイルにも含まれている、ラッパー関数とプラットフォーム呼び出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-243">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="0f3e1-244">これは `TestOutArrayOfStructs` 関数および `MYSTRSTRUCT2` 構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-244">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="0f3e1-245">構造体には次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-245">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="0f3e1-246">`MyStruct` クラスには ANSI 文字の文字列オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-246">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="0f3e1-247"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> フィールドは ANSI 形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-247">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="0f3e1-248">`MyUnsafeStruct` は、文字列の代わりに <xref:System.IntPtr> 型を含む構造体です。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-248">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="0f3e1-249">`NativeMethods` クラスには、オーバーロードされた `TestOutArrayOfStructs` プロトタイプ メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-249">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="0f3e1-250">メソッドでポインターをパラメーターとして宣言している場合、クラスには `unsafe` キーワードでマークを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-250">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="0f3e1-251">Visual Basic ではアンセーフ コードを使用できないので、オーバーロードされたメソッド、unsafe 修飾子、および `MyUnsafeStruct` 構造体は不要です。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-251">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="0f3e1-252">`App` クラスは、配列を渡すために必要なすべてのタスクを実行する、`UsingMarshaling` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-252">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="0f3e1-253">配列には、データが呼び出し先から呼び出し元に渡されることを示すため、`out` (Visual Basic では `ByRef`) キーワードでマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-253">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="0f3e1-254">実装は、以下の <xref:System.Runtime.InteropServices.Marshal> クラス メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-254">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="0f3e1-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> は、アンマネージド バッファーからマネージド オブジェクトにデータをマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="0f3e1-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> は、構造体で文字列用に予約されていたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="0f3e1-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> は、配列用に予約されていたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="0f3e1-258">前述のとおり、C# にはアンセーフ コードを使用できますが、Visual Basic には使用できません。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-258">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="0f3e1-259">C# サンプルで、`UsingUnsafePointer` は、<xref:System.Runtime.InteropServices.Marshal> クラスの代わりにポインターを使用して `MyUnsafeStruct` 構造体を含む配列を戻す、代替のメソッドの実装です。</span><span class="sxs-lookup"><span data-stu-id="0f3e1-259">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="0f3e1-260">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="0f3e1-260">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="0f3e1-261">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f3e1-261">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="0f3e1-262">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f3e1-262">See also</span></span>

- [<span data-ttu-id="0f3e1-263">プラットフォーム呼び出しによるデータのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="0f3e1-263">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="0f3e1-264">マーシャリング (文字列の)</span><span class="sxs-lookup"><span data-stu-id="0f3e1-264">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="0f3e1-265">さまざまな型の配列のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="0f3e1-265">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)

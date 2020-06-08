---
title: ユーザー定義型
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415493"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="6c1f5-102">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6c1f5-102">User-Defined Data Type</span></span>

<span data-ttu-id="6c1f5-103">定義した形式でデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-103">Holds data in a format you define.</span></span> <span data-ttu-id="6c1f5-104">`Structure` ステートメントは形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="6c1f5-105">以前のバージョンの Visual Basic はユーザー定義型 (UDT) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="6c1f5-106">現在のバージョンでは、UDT が*構造体*に拡張されています。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="6c1f5-107">構造体は、さまざまなデータ型の 1 つ以上の*メンバー*を連結したものです。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="6c1f5-108">Visual Basic は、構造体を 1 つの単位として扱いますが、そのメンバーに個別にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c1f5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c1f5-109">Remarks</span></span>

<span data-ttu-id="6c1f5-110">さまざまなデータ型を 1 つの単位に結合する必要がある場合、またはニーズに応える基本データ型がない場合は、構造体のデータ型を定義して使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="6c1f5-111">構造体のデータ型の既定値は、各メンバーの既定値の組み合わせで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="6c1f5-112">宣言の形式</span><span class="sxs-lookup"><span data-stu-id="6c1f5-112">Declaration Format</span></span>

<span data-ttu-id="6c1f5-113">構造体宣言は、[Structure ステートメント](../statements/structure-statement.md)で始まり、`End Structure` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-113">A structure declaration starts with the [Structure Statement](../statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="6c1f5-114">`Structure` ステートメントは、構造体の名前を指定します。これは、構造体で定義されるデータ型の識別子でもあります。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="6c1f5-115">コードの他の部分では、この識別子を使用して、この構造体のデータ型の変数、パラメーター、および関数の戻り値を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="6c1f5-116">`Structure` ステートメントと `End Structure` ステートメントの間の宣言では、構造体のメンバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="6c1f5-117">メンバーのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="6c1f5-117">Member Access Levels</span></span>

<span data-ttu-id="6c1f5-118">すべてのメンバーを宣言するには、[Dim ステートメント](../statements/dim-statement.md)を使用するか、[Public](../modifiers/public.md)、[Friend](../modifiers/friend.md)、[Private](../modifiers/private.md) などのアクセス レベルを指定するステートメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-118">You must declare every member using a [Dim Statement](../statements/dim-statement.md) or a statement that specifies access level, such as [Public](../modifiers/public.md), [Friend](../modifiers/friend.md), or [Private](../modifiers/private.md).</span></span> <span data-ttu-id="6c1f5-119">`Dim` ステートメントを使用する場合、アクセス レベルの既定値はパブリックです。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="6c1f5-120">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="6c1f5-120">Programming Tips</span></span>

- <span data-ttu-id="6c1f5-121">**メモリの使用量。**</span><span class="sxs-lookup"><span data-stu-id="6c1f5-121">**Memory Consumption.**</span></span> <span data-ttu-id="6c1f5-122"> 他のすべての複合データ型と同様に、構造体の総メモリ使用量を計算する場合、各メンバーのストレージ割り当ての公称サイズを単に合計しただけでは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="6c1f5-123">さらに、メモリ内に格納される順序が宣言の順序と同じであると仮定するのも安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="6c1f5-124">構造体のストレージ レイアウトを制御する必要がある場合は、<xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性を `Structure` ステートメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="6c1f5-125">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="6c1f5-125">**Interop Considerations.**</span></span> <span data-ttu-id="6c1f5-126">オートメーション オブジェクトや COM オブジェクトのように、.NET Framework 向けに作成されていないコンポーネントとやり取りする場合、他の環境のユーザー定義型は Visual Basic の構造体型と互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="6c1f5-127">**拡大変換。**</span><span class="sxs-lookup"><span data-stu-id="6c1f5-127">**Widening.**</span></span> <span data-ttu-id="6c1f5-128">任意の構造体のデータ型との間で自動変換が行われることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="6c1f5-129">[Operator ステートメント](../statements/operator-statement.md)を使用して構造体に変換演算子を定義できます。また、各変換演算子を `Widening` または `Narrowing` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-129">You can define conversion operators on your structure using the [Operator Statement](../statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="6c1f5-130">**型文字。**</span><span class="sxs-lookup"><span data-stu-id="6c1f5-130">**Type Characters.**</span></span> <span data-ttu-id="6c1f5-131">構造体のデータ型には、リテラルの型文字も識別子の型文字も含まれません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="6c1f5-132">**Framework の型。**</span><span class="sxs-lookup"><span data-stu-id="6c1f5-132">**Framework Type.**</span></span> <span data-ttu-id="6c1f5-133">.NET Framework に対応する型はありません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="6c1f5-134">すべての構造体は .NET Framework クラス <xref:System.ValueType?displayProperty=nameWithType> から継承されますが、<xref:System.ValueType?displayProperty=nameWithType> に対応する個別の構造体はありません。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6c1f5-135">例</span><span class="sxs-lookup"><span data-stu-id="6c1f5-135">Example</span></span>

<span data-ttu-id="6c1f5-136">次のパラダイムは、構造体の宣言のアウトラインを示します。</span><span class="sxs-lookup"><span data-stu-id="6c1f5-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="6c1f5-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c1f5-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="6c1f5-138">データの種類</span><span class="sxs-lookup"><span data-stu-id="6c1f5-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="6c1f5-139">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="6c1f5-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="6c1f5-140">変換の概要</span><span class="sxs-lookup"><span data-stu-id="6c1f5-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="6c1f5-141">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="6c1f5-141">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="6c1f5-142">Widening</span><span class="sxs-lookup"><span data-stu-id="6c1f5-142">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="6c1f5-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="6c1f5-143">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="6c1f5-144">構造体</span><span class="sxs-lookup"><span data-stu-id="6c1f5-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6c1f5-145">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="6c1f5-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

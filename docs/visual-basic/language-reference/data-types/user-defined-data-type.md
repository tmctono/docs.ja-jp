---
title: ユーザー定義データ型 (Visual Basic)
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
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746756"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="4157f-102">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="4157f-102">User-Defined Data Type</span></span>
<span data-ttu-id="4157f-103">定義する形式でデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="4157f-103">Holds data in a format you define.</span></span> <span data-ttu-id="4157f-104">`Structure`ステートメントの形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="4157f-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="4157f-105">以前のバージョンの Visual Basic では、ユーザー定義型 (UDT) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4157f-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="4157f-106">現在のバージョンの展開に UDT を*構造*します。</span><span class="sxs-lookup"><span data-stu-id="4157f-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="4157f-107">構造体は 1 つまたは複数の連結*メンバー*さまざまなデータ型。</span><span class="sxs-lookup"><span data-stu-id="4157f-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="4157f-108">Visual Basic では、個別にそのメンバーをアクセスすることもできます。 ただし、1 つの単位として構造体が扱われます。</span><span class="sxs-lookup"><span data-stu-id="4157f-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4157f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4157f-109">Remarks</span></span>  
 <span data-ttu-id="4157f-110">定義し、構造体のデータ型を使用して、1 つの単位にさまざまなデータ型を結合する必要がある場合、または基本データ型のいずれもニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="4157f-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="4157f-111">構造体のデータ型の既定値は、各メンバーの既定値の組み合わせで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4157f-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="4157f-112">宣言の形式</span><span class="sxs-lookup"><span data-stu-id="4157f-112">Declaration Format</span></span>  
 <span data-ttu-id="4157f-113">構造体の宣言が始まり、 [Structure ステートメント](../../../visual-basic/language-reference/statements/structure-statement.md)で終わると、`End Structure`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="4157f-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="4157f-114">`Structure`ステートメントは、これは、構造体を定義するデータ型の識別子でも構造体の名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="4157f-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="4157f-115">コードの他の部分では、変数、パラメーター、および関数は、この構造体のデータ型の値を返すを宣言するのに、この識別子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4157f-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="4157f-116">宣言、`Structure`と`End Structure`ステートメントでは、構造体のメンバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4157f-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="4157f-117">メンバーのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="4157f-117">Member Access Levels</span></span>  
 <span data-ttu-id="4157f-118">使用してすべてのメンバーを宣言する必要があります、 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)またはなど、アクセス レベルを指定するステートメント[パブリック](../../../visual-basic/language-reference/modifiers/public.md)、[フレンド](../../../visual-basic/language-reference/modifiers/friend.md)、または[プライベート](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="4157f-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="4157f-119">使用する場合、`Dim`ステートメントでは、パブリックにアクセス レベルの既定値。</span><span class="sxs-lookup"><span data-stu-id="4157f-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="4157f-120">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="4157f-120">Programming Tips</span></span>  
  
- <span data-ttu-id="4157f-121">**メモリ使用量。**</span><span class="sxs-lookup"><span data-stu-id="4157f-121">**Memory Consumption.**</span></span> <span data-ttu-id="4157f-122"> 他のすべての複合データ型と同様に、構造体の総メモリ使用量を計算する場合、各メンバーのストレージ割り当ての公称サイズを単に合計しただけでは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="4157f-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="4157f-123">さらに、メモリ内に格納される順序が宣言の順序と同じであると仮定するのも安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="4157f-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="4157f-124">構造体のストレージ レイアウトを制御する必要がある場合は、<xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性を `Structure` ステートメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="4157f-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
- <span data-ttu-id="4157f-125">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="4157f-125">**Interop Considerations.**</span></span> <span data-ttu-id="4157f-126">オートメーションまたは COM オブジェクトなどの .NET Framework 用に作成されていないコンポーネントをやり取りする場合、他の環境でのユーザー定義型は Visual Basic 構造型と互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4157f-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
- <span data-ttu-id="4157f-127">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="4157f-127">**Widening.**</span></span> <span data-ttu-id="4157f-128">任意の構造のデータ型との間の自動変換はありません。</span><span class="sxs-lookup"><span data-stu-id="4157f-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="4157f-129">変換演算子を定義するには構造体を使用して、 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)、するには、各変換演算子を宣言して`Widening`または`Narrowing`します。</span><span class="sxs-lookup"><span data-stu-id="4157f-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
- <span data-ttu-id="4157f-130">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="4157f-130">**Type Characters.**</span></span> <span data-ttu-id="4157f-131">リテラルの型文字または識別子の型文字は、構造体のデータ型はあるありません。</span><span class="sxs-lookup"><span data-stu-id="4157f-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="4157f-132">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="4157f-132">**Framework Type.**</span></span> <span data-ttu-id="4157f-133">.NET Framework では、対応する型はありません。</span><span class="sxs-lookup"><span data-stu-id="4157f-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="4157f-134">すべての構造は、.NET Framework クラスから継承<xref:System.ValueType?displayProperty=nameWithType>に対応する個別の構造体がありませんが、<xref:System.ValueType?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="4157f-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4157f-135">例</span><span class="sxs-lookup"><span data-stu-id="4157f-135">Example</span></span>  
 <span data-ttu-id="4157f-136">構造体の宣言の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4157f-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="4157f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="4157f-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="4157f-138">データの種類</span><span class="sxs-lookup"><span data-stu-id="4157f-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4157f-139">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="4157f-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="4157f-140">変換の概要</span><span class="sxs-lookup"><span data-stu-id="4157f-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="4157f-141">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="4157f-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="4157f-142">Widening</span><span class="sxs-lookup"><span data-stu-id="4157f-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="4157f-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4157f-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="4157f-144">構造体</span><span class="sxs-lookup"><span data-stu-id="4157f-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4157f-145">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="4157f-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

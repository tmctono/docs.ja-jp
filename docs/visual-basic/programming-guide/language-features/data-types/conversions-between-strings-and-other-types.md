---
title: 文字列とその他の型との変換
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: ac2e8ce912080c284d8ba0228830dd6b3ddf5f6e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350134"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="cedf4-102">文字列とその他の型との変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cedf4-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="cedf4-103">数値、`Boolean`、または日付/時刻の値を `String`に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="cedf4-104">文字列の内容が変換先のデータ型の有効な値として解釈される場合は、逆方向 (文字列値から数値、`Boolean`、または `Date`) に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="cedf4-105">失敗した場合は、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cedf4-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="cedf4-106">これらのすべての代入の変換は、どちらの方向でも縮小変換です。</span><span class="sxs-lookup"><span data-stu-id="cedf4-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="cedf4-107">型変換のキーワード (`CBool`、`CByte`、`CDate`、`CDbl`、`CDec`、`CInt`、`CLng`、`CSByte`、`CShort`、`CSng`、`CStr`) を使用する必要があります。`CUInt``CULng``CUShort``CType`</span><span class="sxs-lookup"><span data-stu-id="cedf4-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="cedf4-108"><xref:Microsoft.VisualBasic.Strings.Format%2A> 関数と <xref:Microsoft.VisualBasic.Conversion.Val%2A> 関数を使用すると、文字列と数値の間の変換をさらに制御できます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="cedf4-109">クラスまたは構造体を定義している場合は、`String` とクラスまたは構造体の型との間で型変換演算子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="cedf4-110">詳細については、「[方法: 変換演算子を定義する](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cedf4-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="cedf4-111">数値から文字列への変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="cedf4-112">`Format` 関数を使用すると、数値を書式設定された文字列に変換できます。これには、適切な数字だけでなく、通貨記号 (`$`など)、桁区切り記号、*桁*区切り記号 (`,`など)、小数点区切り記号 (`.`など) も含まれます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="cedf4-113">`Format` は、Windows の**コントロールパネル**で指定されている**地域のオプション**の設定に従って、適切なシンボルを自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="cedf4-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="cedf4-114">連結 (`&`) 演算子は、次の例に示すように、数値を文字列に暗黙的に変換できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cedf4-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="cedf4-115">文字列から数値への変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="cedf4-116">`Val` 関数を使用すると、文字列の数字を数値に明示的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="cedf4-117">`Val` は、数字、スペース、タブ、ラインフィード、またはピリオド以外の文字が見つかるまで文字列を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="cedf4-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="cedf4-118">シーケンス "& O" と "& H" は、数値システムのベースを変更し、スキャンを終了します。</span><span class="sxs-lookup"><span data-stu-id="cedf4-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="cedf4-119">`Val` の読み取りを停止するまで、適切なすべての文字が数値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="cedf4-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="cedf4-120">たとえば、次のステートメントは `141.825`値を返します。</span><span class="sxs-lookup"><span data-stu-id="cedf4-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="cedf4-121">Visual Basic が文字列を数値に変換する場合、Windows の**コントロールパネル**で指定されている**地域のオプション**の設定を使用して、桁区切り記号、小数点の区切り記号、および通貨記号を解釈します。</span><span class="sxs-lookup"><span data-stu-id="cedf4-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="cedf4-122">つまり、変換は1つの設定では成功しますが、別の設定では成功しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cedf4-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="cedf4-123">たとえば、`"$14.20"` は英語 (米国) のロケールでは許容されますが、フランス語のロケールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cedf4-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cedf4-124">参照</span><span class="sxs-lookup"><span data-stu-id="cedf4-124">See also</span></span>

- [<span data-ttu-id="cedf4-125">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="cedf4-126">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="cedf4-127">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="cedf4-128">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="cedf4-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="cedf4-129">配列変換</span><span class="sxs-lookup"><span data-stu-id="cedf4-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="cedf4-130">データの種類</span><span class="sxs-lookup"><span data-stu-id="cedf4-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cedf4-131">CString</span><span class="sxs-lookup"><span data-stu-id="cedf4-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cedf4-132">グローバル化およびローカライズされたアプリの開発</span><span class="sxs-lookup"><span data-stu-id="cedf4-132">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)

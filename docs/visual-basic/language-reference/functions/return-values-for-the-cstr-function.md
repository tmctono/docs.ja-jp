---
title: CStr 関数の戻り値
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349995"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="48794-102">CStr 関数の戻り値 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48794-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="48794-103">次の表では、`expression`のさまざまなデータ型に対する `CStr` の戻り値について説明します。</span><span class="sxs-lookup"><span data-stu-id="48794-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="48794-104">`expression` 型がの場合</span><span class="sxs-lookup"><span data-stu-id="48794-104">If `expression` type is</span></span>|<span data-ttu-id="48794-105">`CStr` 戻り値</span><span class="sxs-lookup"><span data-stu-id="48794-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="48794-106">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="48794-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="48794-107">"True" または "False" を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="48794-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="48794-108">Date データ型</span><span class="sxs-lookup"><span data-stu-id="48794-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="48794-109">システムの短い日付形式の `Date` 値 (日付と時刻) を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="48794-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="48794-110">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="48794-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="48794-111">数値を表す文字列。</span><span class="sxs-lookup"><span data-stu-id="48794-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="48794-112">CStr と日付</span><span class="sxs-lookup"><span data-stu-id="48794-112">CStr and Date</span></span>  
 <span data-ttu-id="48794-113">`Date` 型には、常に日付と時刻の両方の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48794-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="48794-114">型変換の場合、Visual Basic は 1/1/0001 (1 年1月1日) を日付の*ニュートラル値*と見なし、00:00:00 (午前0時) はその時刻のニュートラル値と見なされます。</span><span class="sxs-lookup"><span data-stu-id="48794-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="48794-115">`CStr` には、結果の文字列にニュートラル値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="48794-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="48794-116">たとえば、`#January 1, 0001 9:30:00#` を文字列に変換した場合、結果は "9:30:00 AM" になります。日付情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="48794-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="48794-117">ただし、日付情報は依然として元の `Date` 値に存在し、<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>などの関数を使用して回復できます。</span><span class="sxs-lookup"><span data-stu-id="48794-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48794-118">`CStr` 関数は、アプリケーションの現在のカルチャ設定に基づいて変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="48794-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="48794-119">特定のカルチャの数値の文字列形式を取得するには、数値の `ToString(IFormatProvider)` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="48794-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="48794-120">たとえば、型 `Double` の値を `String`に変換する場合は、<xref:System.Double.ToString%2A?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="48794-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48794-121">参照</span><span class="sxs-lookup"><span data-stu-id="48794-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="48794-122">CString</span><span class="sxs-lookup"><span data-stu-id="48794-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="48794-123">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="48794-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="48794-124">Date データ型</span><span class="sxs-lookup"><span data-stu-id="48794-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)

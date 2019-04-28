---
title: CStr 関数の戻り値 (Visual Basic)
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
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801531"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="c9035-102">CStr 関数の戻り値 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9035-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="c9035-103">次の表は、戻り値の`CStr`のさまざまなデータ型の`expression`します。</span><span class="sxs-lookup"><span data-stu-id="c9035-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="c9035-104">場合`expression`型</span><span class="sxs-lookup"><span data-stu-id="c9035-104">If `expression` type is</span></span>|<span data-ttu-id="c9035-105">`CStr` 戻り値</span><span class="sxs-lookup"><span data-stu-id="c9035-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="c9035-106">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="c9035-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="c9035-107">"True"を含む文字列または"False"。</span><span class="sxs-lookup"><span data-stu-id="c9035-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="c9035-108">Date データ型</span><span class="sxs-lookup"><span data-stu-id="c9035-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="c9035-109">含んでいる文字列を`Date`システムの短い日付形式で値 (日付と時刻)。</span><span class="sxs-lookup"><span data-stu-id="c9035-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="c9035-110">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="c9035-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="c9035-111">数値を表す文字列。</span><span class="sxs-lookup"><span data-stu-id="c9035-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="c9035-112">CStr と日付</span><span class="sxs-lookup"><span data-stu-id="c9035-112">CStr and Date</span></span>  
 <span data-ttu-id="c9035-113">`Date`型には常に日付と時刻の両方の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9035-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="c9035-114">型変換のために、Visual Basic であると見なす 1/1/0001 (年 1 月 1日年 1 月)、*ニュートラル値*を時間のニュートラル値の日付、および 00時 00分: 00 (午前 0 時)。</span><span class="sxs-lookup"><span data-stu-id="c9035-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="c9035-115">`CStr` 結果の文字列には基準値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c9035-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="c9035-116">たとえば、変換する`#January 1, 0001 9:30:00#`結果は"9時 30分: 00 AM"を文字列には、日付情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c9035-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="c9035-117">ただし、日付情報は、元に引き続き存在`Date`値し、などの関数で回復できる<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>します。</span><span class="sxs-lookup"><span data-stu-id="c9035-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9035-118">`CStr`関数は、アプリケーションの現在のカルチャ設定に基づいて変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9035-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="c9035-119">特定のカルチャの数値の文字列形式を取得するには、数値を使用`ToString(IFormatProvider)`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c9035-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="c9035-120">たとえば、使用して<xref:System.Double.ToString%2A?displayProperty=nameWithType>型の値を変換するときに`Double`を`String`します。</span><span class="sxs-lookup"><span data-stu-id="c9035-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9035-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9035-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="c9035-122">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="c9035-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c9035-123">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="c9035-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="c9035-124">Date データ型</span><span class="sxs-lookup"><span data-stu-id="c9035-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)

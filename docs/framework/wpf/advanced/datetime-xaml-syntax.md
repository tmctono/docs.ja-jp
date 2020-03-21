---
title: DateTime XAML 構文
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186327"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="5c5f0-102">DateTime XAML 構文</span><span class="sxs-lookup"><span data-stu-id="5c5f0-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="5c5f0-103">および などの<xref:System.Windows.Controls.Calendar><xref:System.Windows.Controls.DatePicker>一部のコントロールには、この型を<xref:System.DateTime>使用するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="5c5f0-104">これらのコントロールに対する日付または時刻の初期値は、分離コードで実行時に指定するのが一般的です。ただし、日付または時刻の初期値を XAML で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="5c5f0-105">WPF XAML パーサーは、<xref:System.DateTime>組み込みの XAML テキスト構文を使用して値の解析を処理します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="5c5f0-106">このトピックでは、XAML テキスト構文の<xref:System.DateTime>詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="5c5f0-107">DateTime XAML 構文が使用される状況</span><span class="sxs-lookup"><span data-stu-id="5c5f0-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="5c5f0-108">日付は必ずしも XAML で設定する必要はありません。また、XAML で設定することが適切とは言えない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="5c5f0-109">たとえば、このプロパティを<xref:System.DateTime.Now%2A?displayProperty=nameWithType>使用して実行時に日付を初期化したり、ユーザー入力に基づいて分離コード内の予定表の日付調整をすべて行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="5c5f0-110">ただし、日付<xref:System.Windows.Controls.Calendar><xref:System.Windows.Controls.DatePicker>をコントロール テンプレートにハードコーディングする場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="5c5f0-111">これらの<xref:System.DateTime>シナリオでは、XAML 構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="5c5f0-112">DateTime XAML 構文はネイティブの動作</span><span class="sxs-lookup"><span data-stu-id="5c5f0-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="5c5f0-113"><xref:System.DateTime>は、CLR の基本クラス ライブラリで定義されているクラスです。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="5c5f0-114">基本クラス ライブラリが CLR の他の部分とどのように関連するかにより、クラスに適用<xref:System.ComponentModel.TypeConverterAttribute>し、型コンバーターを使用して XAML からの文字列を処理し、ランタイム<xref:System.DateTime>オブジェクト モデルで文字列に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="5c5f0-115">変換動作を提供する `DateTimeConverter` クラスは存在しません。このトピックで説明する変換動作は、WPF XAML パーサーのネイティブな動作です。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="5c5f0-116">DateTime XAML 構文の書式指定文字列</span><span class="sxs-lookup"><span data-stu-id="5c5f0-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="5c5f0-117">フォーマット文字列を使用して、フォーマット<xref:System.DateTime>を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="5c5f0-118">書式指定文字列は、値を作成するときに使用できるテキスト構文を形式化します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="5c5f0-119"><xref:System.DateTime>既存の WPF コントロールの値は、通常は時間<xref:System.DateTime>コンポーネントではなく、日付コンポーネントのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="5c5f0-120">XAML で<xref:System.DateTime>を指定する場合は、任意の書式指定文字列を同じ意味で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="5c5f0-121">また、このトピックで特に示されていない形式および書式指定文字列も使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="5c5f0-122">技術的には、WPF XAML<xref:System.DateTime>パーサーによって指定され解析される任意の値の XAML は、 への<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>内部呼び出しを使用するため、XAML 入力に受<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>け入れられる任意の文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="5c5f0-123">詳細については、<xref:System.DateTime.Parse%2A?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5c5f0-124">DateTime XAML 構文では`en-us`、常<xref:System.Globalization.CultureInfo>にそのネイティブ変換の として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="5c5f0-125">XAML の属性レベル<xref:System.Windows.FrameworkElement.Language%2A>の型`xml:lang`変換は、そのコンテキストなしで動作するため、XAML の値または値の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="5c5f0-126">日や月を表示する順序などにはカルチャによる違いがあるため、ここで示した書式指定文字列は補完しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="5c5f0-127">ここで示した書式指定文字列は、その他のカルチャ設定に関係なく、XAML を解析する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="5c5f0-128">以下のセクションでは、一般的な<xref:System.DateTime>書式指定文字列について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="5c5f0-129">短い形式の日付パターン ("d")</span><span class="sxs-lookup"><span data-stu-id="5c5f0-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="5c5f0-130">次に、XAML の短い日付<xref:System.DateTime>形式を示します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="5c5f0-131">これは、WPF コントロールでの一般的な使用法で、必要なすべての情報を指定するための最も簡単な形式です。タイム ゾーン オフセットと時刻要素を誤って指定した場合でも影響を受けないため、他の形式ではなく、この形式の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="5c5f0-132">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="5c5f0-133">詳細については、<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="5c5f0-134">並べ替えできる DateTime のパターン ("s")</span><span class="sxs-lookup"><span data-stu-id="5c5f0-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="5c5f0-135">XAML での並べ<xref:System.DateTime>替え可能なパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="5c5f0-136">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します (時刻要素はすべて 0 として入力されます)。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="5c5f0-137">RFC1123 パターン ("r")</span><span class="sxs-lookup"><span data-stu-id="5c5f0-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="5c5f0-138">RFC1123 パターンの利点は、カルチャに依存しないために、RFC1123 パターンが使用されている他の日付ジェネレーターから入力された文字列を使用できることです。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="5c5f0-139">次に、XAML の RFC1123<xref:System.DateTime>パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="5c5f0-140">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します (時刻要素はすべて 0 として入力されます)。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="5c5f0-141">その他の形式とパターン</span><span class="sxs-lookup"><span data-stu-id="5c5f0-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="5c5f0-142">前述のように、 in <xref:System.DateTime> XAML は、 の入力として受け入れられる任意<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>の文字列として指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c5f0-143">これには、他の形式形式 (たとえば<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) や、特定<xref:System.Globalization.DateTimeFormatInfo>の形式として形式化されていない形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="5c5f0-144">たとえば、フォーム`YYYY/mm/dd`は の入力として受け<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>入れられます。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c5f0-145">このトピックでは、使用可能な形式の一部を説明します。標準的な使用手順としては、短い形式の日付パターンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c5f0-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5f0-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c5f0-146">See also</span></span>

- [<span data-ttu-id="5c5f0-147">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="5c5f0-147">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)

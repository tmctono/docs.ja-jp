---
title: その他のデータ型
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346342"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="2b95f-102">その他のデータ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b95f-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="2b95f-103">Visual Basic には、数値や文字を対象としていない複数のデータ型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2b95f-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="2b95f-104">これらは、yes/no の値、日付/時刻の値、オブジェクト アドレスなど、特殊なデータを扱います。</span><span class="sxs-lookup"><span data-stu-id="2b95f-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="2b95f-105">Visual Basic データ型を並べて比較している表を、[データ型](../../../../visual-basic/language-reference/data-types/index.md)に関するページで参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b95f-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="2b95f-106">ブール型</span><span class="sxs-lookup"><span data-stu-id="2b95f-106">Boolean Type</span></span>  
 <span data-ttu-id="2b95f-107">[Boolean データ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)は、`True` または `False` と解釈される符号なしの値です。</span><span class="sxs-lookup"><span data-stu-id="2b95f-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="2b95f-108">データ幅は、実装するプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2b95f-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="2b95f-109">変数が 2 つの状態 (true/false、yes/no、on/off など) の値のみを含む可能性がある場合は、`Boolean` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="2b95f-110">日付型</span><span class="sxs-lookup"><span data-stu-id="2b95f-110">Date Type</span></span>  
 <span data-ttu-id="2b95f-111">[Date データ型](../../../../visual-basic/language-reference/data-types/date-data-type.md)は、日付と時刻の両方の情報を保持する 64 ビット値です。</span><span class="sxs-lookup"><span data-stu-id="2b95f-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="2b95f-112">各インクリメントはグレゴリオ暦の西暦 1 年 1 月 1 日 (午前 12:00) からの経過時間を 100 ナノ秒単位で表します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="2b95f-113">変数が日付値、時刻値、またはその両方を含む可能性がある場合は、`Date` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="2b95f-114">オブジェクトの型</span><span class="sxs-lookup"><span data-stu-id="2b95f-114">Object Type</span></span>  
 <span data-ttu-id="2b95f-115">[Object データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)は、自らのアプリケーションまたはその他のアプリケーション内のオブジェクト インスタンスを指す 32 ビットのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="2b95f-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="2b95f-116">`Object` 変数は、アプリケーションによって認識される任意のオブジェクト、または任意のデータ型のデータを参照できます。</span><span class="sxs-lookup"><span data-stu-id="2b95f-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="2b95f-117">これには、"*値型*" (`Integer`、`Boolean`、構造体インスタンスなど) と "*参照型*" (`String` や <xref:System.Windows.Forms.Form>などのクラスから作成されるオブジェクトのインスタンスおよび配列インスタンス) の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b95f-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="2b95f-118">変数に含まれるポインターが、コンパイル時にはわからないクラスのインスタンスを指している場合、またはさまざまなデータ型の値を指す可能性がある場合は、`Object` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="2b95f-119">`Object` データ型の利点は、任意のデータ型のデータを格納するために使用できることです。</span><span class="sxs-lookup"><span data-stu-id="2b95f-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="2b95f-120">欠点は、実行時間が長くなる追加処理が発生し、アプリケーションのパフォーマンスが低下することです。</span><span class="sxs-lookup"><span data-stu-id="2b95f-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="2b95f-121">値型の `Object` 変数を使用すると、"*ボックス化*" と "*ボックス化解除*" が発生します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="2b95f-122">参照型に対して使用すると、"*遅延バインディング*" が発生します。</span><span class="sxs-lookup"><span data-stu-id="2b95f-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b95f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b95f-123">See also</span></span>

- [<span data-ttu-id="2b95f-124">型文字</span><span class="sxs-lookup"><span data-stu-id="2b95f-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="2b95f-125">基本データ型</span><span class="sxs-lookup"><span data-stu-id="2b95f-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="2b95f-126">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="2b95f-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="2b95f-127">文字データ型</span><span class="sxs-lookup"><span data-stu-id="2b95f-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [<span data-ttu-id="2b95f-128">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="2b95f-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="2b95f-129">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="2b95f-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)

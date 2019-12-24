---
title: その他のデータ型
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346342"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="4e793-102">その他のデータ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e793-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="4e793-103">Visual Basic には、数値や文字に向いていない複数のデータ型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e793-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="4e793-104">代わりに、yes/no 値、日付/時刻値、オブジェクトアドレスなどの特殊なデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="4e793-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="4e793-105">Visual Basic のデータ型の並列比較を示す表については、「[データ型の概要](../../../../visual-basic/language-reference/data-types/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e793-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="4e793-106">ブール型</span><span class="sxs-lookup"><span data-stu-id="4e793-106">Boolean Type</span></span>  
 <span data-ttu-id="4e793-107">[ブールデータ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)は、`True` または `False`として解釈される符号なしの値です。</span><span class="sxs-lookup"><span data-stu-id="4e793-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="4e793-108">データ幅は、実装するプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4e793-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="4e793-109">変数に、true/false、yes/no、on/off などの2つの状態の値のみを含めることができる場合は、それを `Boolean`として宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e793-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="4e793-110">日付型</span><span class="sxs-lookup"><span data-stu-id="4e793-110">Date Type</span></span>  
 <span data-ttu-id="4e793-111">[日付データ型](../../../../visual-basic/language-reference/data-types/date-data-type.md)は、日付と時刻の両方の情報を保持する64ビット値です。</span><span class="sxs-lookup"><span data-stu-id="4e793-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="4e793-112">各インクリメントは、グレゴリオ暦の1年1月1日の開始 (12:00 AM) からの経過時間の100ナノ秒を表します。</span><span class="sxs-lookup"><span data-stu-id="4e793-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="4e793-113">変数に日付値、時刻値、またはその両方を含めることができる場合は、`Date`として宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e793-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="4e793-114">オブジェクトの型</span><span class="sxs-lookup"><span data-stu-id="4e793-114">Object Type</span></span>  
 <span data-ttu-id="4e793-115">[Object データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)は、アプリケーション内または他のアプリケーション内のオブジェクトインスタンスを指す32ビットアドレスです。</span><span class="sxs-lookup"><span data-stu-id="4e793-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="4e793-116">`Object` 変数は、アプリケーションが認識する任意のオブジェクト、または任意のデータ型のデータを参照できます。</span><span class="sxs-lookup"><span data-stu-id="4e793-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="4e793-117">これには、`Integer`、`Boolean`、構造体のインスタンスなどの*値型*と、`String` や <xref:System.Windows.Forms.Form>、配列インスタンスなどのクラスから作成されたオブジェクトのインスタンスである*参照型*の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e793-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="4e793-118">コンパイル時にわからないクラスのインスタンスへのポインターが変数に格納されている場合、または、さまざまなデータ型のデータを参照できる場合は、それを `Object`として宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e793-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="4e793-119">`Object` データ型の利点は、任意のデータ型のデータを格納するために使用できることです。</span><span class="sxs-lookup"><span data-stu-id="4e793-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="4e793-120">欠点は、実行時間のかかる追加操作が発生し、アプリケーションの実行速度が低下することです。</span><span class="sxs-lookup"><span data-stu-id="4e793-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="4e793-121">値型に `Object` 変数を使用すると、*ボックス*化と*ボックス化解除*が発生します。</span><span class="sxs-lookup"><span data-stu-id="4e793-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="4e793-122">参照型に使用すると、*遅延バインディング*が発生します。</span><span class="sxs-lookup"><span data-stu-id="4e793-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e793-123">参照</span><span class="sxs-lookup"><span data-stu-id="4e793-123">See also</span></span>

- [<span data-ttu-id="4e793-124">型文字</span><span class="sxs-lookup"><span data-stu-id="4e793-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="4e793-125">基本データ型</span><span class="sxs-lookup"><span data-stu-id="4e793-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="4e793-126">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="4e793-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="4e793-127">文字データ型</span><span class="sxs-lookup"><span data-stu-id="4e793-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [<span data-ttu-id="4e793-128">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="4e793-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="4e793-129">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="4e793-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)

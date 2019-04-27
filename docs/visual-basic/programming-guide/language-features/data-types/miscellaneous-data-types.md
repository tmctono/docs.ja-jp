---
title: その他のデータ型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 4808d87322d5b21b70ec38e2eb31b2b204938745
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008242"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="15831-102">その他のデータ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15831-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="15831-103">Visual Basic ではない数字や文字を対象とするいくつかのデータ型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="15831-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="15831-104">代わりに、それらを扱う特化されたデータなど、はい/いいえ値、日付/時刻値、およびオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="15831-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="15831-105">Visual Basic のデータ型のサイド バイ サイドで比較を示す表を参照してください[データ型](../../../../visual-basic/language-reference/data-types/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="15831-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="15831-106">ブール型</span><span class="sxs-lookup"><span data-stu-id="15831-106">Boolean Type</span></span>  
 <span data-ttu-id="15831-107">[ブール データ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)符号なしの値として解釈されるは`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="15831-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="15831-108">データのサイズは実装されているプラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="15831-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="15831-109">場合は、変数は、はい/いいえ、またはオン/オフ、true または false などの 2 つの状態値のみを含めることができます、宣言として`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="15831-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="15831-110">日付型</span><span class="sxs-lookup"><span data-stu-id="15831-110">Date Type</span></span>  
 <span data-ttu-id="15831-111">[Date データ型](../../../../visual-basic/language-reference/data-types/date-data-type.md)は日付と時刻の両方の情報を保持する 64 ビット値です。</span><span class="sxs-lookup"><span data-stu-id="15831-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="15831-112">各インクリメントは、(12時 00分 AM) を開始してから、グレゴリオ暦での 1 年 1 月 1 日の経過時間の 100 ナノ秒を表します。</span><span class="sxs-lookup"><span data-stu-id="15831-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="15831-113">場合は、変数には、日付の値を時間の値、またはその両方を含めることができます、宣言として`Date`します。</span><span class="sxs-lookup"><span data-stu-id="15831-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="15831-114">オブジェクトの型</span><span class="sxs-lookup"><span data-stu-id="15831-114">Object Type</span></span>  
 <span data-ttu-id="15831-115">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)は、アプリケーション内、またはその他のアプリケーションでオブジェクトのインスタンスを指す 32 ビット アドレスです。</span><span class="sxs-lookup"><span data-stu-id="15831-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="15831-116">`Object`変数は、アプリケーションが認識されると、任意のオブジェクトや任意のデータ型のデータに参照できます。</span><span class="sxs-lookup"><span data-stu-id="15831-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="15831-117">両方が含まれます*値の型*など`Integer`、 `Boolean`、および構造体のインスタンスと*参照型*、オブジェクトなどのクラスから作成されたのインスタンスである`String`と<xref:System.Windows.Forms.Form>のインスタンスの配列。</span><span class="sxs-lookup"><span data-stu-id="15831-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="15831-118">変数は、コンパイル時に不明なクラスのインスタンスへのポインターを格納する場合、またはさまざまなデータ型のデータを指すことができる場合は、宣言として`Object`します。</span><span class="sxs-lookup"><span data-stu-id="15831-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="15831-119">利点、`Object`データ型は、任意のデータ型のデータの格納に使用できます。</span><span class="sxs-lookup"><span data-stu-id="15831-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="15831-120">デメリットは、実行時間がかかると、アプリケーションの実行速度が遅く、余分な処理が発生することです。</span><span class="sxs-lookup"><span data-stu-id="15831-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="15831-121">使用する場合、`Object`発生する値の型の変数、*ボックス化*と*ボックス化解除*します。</span><span class="sxs-lookup"><span data-stu-id="15831-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="15831-122">に参照型を使用する場合に発生する*遅延バインディング*します。</span><span class="sxs-lookup"><span data-stu-id="15831-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15831-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="15831-123">See also</span></span>

- [<span data-ttu-id="15831-124">型文字</span><span class="sxs-lookup"><span data-stu-id="15831-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="15831-125">基本データ型</span><span class="sxs-lookup"><span data-stu-id="15831-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="15831-126">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="15831-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="15831-127">文字データ型</span><span class="sxs-lookup"><span data-stu-id="15831-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [<span data-ttu-id="15831-128">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="15831-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="15831-129">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="15831-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)

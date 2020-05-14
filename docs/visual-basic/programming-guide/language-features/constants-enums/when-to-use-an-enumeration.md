---
title: 列挙型を使用する状況
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353955"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="71764-102">列挙型を使用する状況 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71764-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="71764-103">列挙型を使用すると、一連の関連する定数を簡単に操作できます。</span><span class="sxs-lookup"><span data-stu-id="71764-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="71764-104">列挙型 (`Enum`) は、一連の値のシンボリック名です。</span><span class="sxs-lookup"><span data-stu-id="71764-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="71764-105">列挙型はデータ型扱いであり、これを使用することで、変数やプロパティと共に使用する一連の定数を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="71764-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="71764-106">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="71764-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="71764-107">プロシージャで受け取れる変数の個数が限られている場合には、必ず列挙型の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="71764-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="71764-108">列挙型を使用すると、コードの明瞭さと読みやすさが増します。わかりやすい名前を使用すると特に効果的です。</span><span class="sxs-lookup"><span data-stu-id="71764-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="71764-109">列挙型を使用する利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71764-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="71764-110">数の入れ替えや入力間違いによるエラーを減らせます。</span><span class="sxs-lookup"><span data-stu-id="71764-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="71764-111">値を後で変更しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="71764-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="71764-112">コードが読みやすくなり、コードにエラーが紛れ込む可能性を抑えられます。</span><span class="sxs-lookup"><span data-stu-id="71764-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="71764-113">上位互換性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="71764-113">Ensures forward compatibility.</span></span> <span data-ttu-id="71764-114">列挙型を使用すると、今後メンバー名に対応する値が変更された場合に、コードでエラーが発生する確率が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="71764-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="71764-115">列挙型に名前を付ける</span><span class="sxs-lookup"><span data-stu-id="71764-115">Naming Enumerations</span></span>  
 <span data-ttu-id="71764-116">列挙型メンバーにはなんらかの名前付け規則を適用してください。</span><span class="sxs-lookup"><span data-stu-id="71764-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="71764-117">Visual Basic で列挙型メンバーを検出した場合、参照対象の別の型ライブラリに同じ名前が含まれていると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="71764-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="71764-118">アプリケーションまたはコンポーネントの値を特定できる、一意の接頭辞を使用してください。</span><span class="sxs-lookup"><span data-stu-id="71764-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="71764-119">列挙型のメンバーを参照する場合は、列挙型名でメンバー名を修飾するか、`Imports` ステートメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71764-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="71764-120">詳細については、[列挙型と名前の修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71764-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="71764-121">定義済みの列挙型</span><span class="sxs-lookup"><span data-stu-id="71764-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="71764-122">Visual Basic には、コードを作成しやすいように定義済みの列挙型が多数用意されています (`FirstDayOfWeek` や `MsgBoxResult` など)。</span><span class="sxs-lookup"><span data-stu-id="71764-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="71764-123">これらの一覧については、[定数と列挙型](../../../../visual-basic/language-reference/constants-and-enumerations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71764-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71764-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="71764-124">See also</span></span>

- [<span data-ttu-id="71764-125">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="71764-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="71764-126">方法: 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="71764-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="71764-127">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="71764-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="71764-128">方法: Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="71764-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="71764-129">方法: 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="71764-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="71764-130">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="71764-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="71764-131">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="71764-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)

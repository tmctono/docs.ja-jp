---
title: 列挙型を使用する状況
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353955"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="ace9c-102">列挙型を使用する状況 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ace9c-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="ace9c-103">列挙体を使用すると、関連する定数のセットを簡単に操作できます。</span><span class="sxs-lookup"><span data-stu-id="ace9c-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="ace9c-104">列挙型 (`Enum`) は、値のセットのシンボル名です。</span><span class="sxs-lookup"><span data-stu-id="ace9c-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="ace9c-105">列挙型はデータ型として扱われ、変数およびプロパティで使用する定数のセットを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ace9c-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="ace9c-106">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="ace9c-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="ace9c-107">プロシージャが限定された一連の変数を受け入れる場合は、列挙型の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ace9c-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="ace9c-108">列挙型により、特に意味のある名前が使用される場合に、明確で読みやすいコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ace9c-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="ace9c-109">列挙を使用する利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ace9c-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="ace9c-110">数値の転置またはミスによって発生するエラーを減らします。</span><span class="sxs-lookup"><span data-stu-id="ace9c-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="ace9c-111">では、将来の値の変更が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ace9c-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="ace9c-112">コードを読みやすくします。つまり、エラーが発生する可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="ace9c-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="ace9c-113">上位互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="ace9c-113">Ensures forward compatibility.</span></span> <span data-ttu-id="ace9c-114">列挙体を使用すると、後でメンバー名に対応する値を変更すると、コードが失敗する可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="ace9c-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="ace9c-115">列挙型の名前付け</span><span class="sxs-lookup"><span data-stu-id="ace9c-115">Naming Enumerations</span></span>  
 <span data-ttu-id="ace9c-116">列挙メンバーには名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="ace9c-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="ace9c-117">Visual Basic が列挙メンバー名を検出した場合、他の参照されるタイプライブラリに同じ名前が含まれていると、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ace9c-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="ace9c-118">アプリケーションまたはコンポーネントの値を識別する一意のプレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ace9c-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="ace9c-119">列挙体のメンバーを参照する場合は、メンバー名を列挙名で修飾するか、または `Imports` ステートメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace9c-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="ace9c-120">詳細については、「[列挙型と名前の修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace9c-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="ace9c-121">定義済みの列挙型</span><span class="sxs-lookup"><span data-stu-id="ace9c-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="ace9c-122">Visual Basic には、コードを容易にするために、`FirstDayOfWeek` や `MsgBoxResult`など、いくつかの定義済みの列挙型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ace9c-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="ace9c-123">これらの一覧については、「[定数と列挙型](../../../../visual-basic/language-reference/constants-and-enumerations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace9c-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace9c-124">参照</span><span class="sxs-lookup"><span data-stu-id="ace9c-124">See also</span></span>

- [<span data-ttu-id="ace9c-125">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="ace9c-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="ace9c-126">方法 : 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="ace9c-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ace9c-127">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="ace9c-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ace9c-128">方法: Visual Basic 内の列挙体を反復処理する</span><span class="sxs-lookup"><span data-stu-id="ace9c-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ace9c-129">方法 : 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="ace9c-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="ace9c-130">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="ace9c-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="ace9c-131">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="ace9c-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)

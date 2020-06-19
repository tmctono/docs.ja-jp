---
title: 表記規則とコード規則
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 0e36d9d61b0dd2701210ce614d15fd38f08f5401
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401356"
---
# <a name="typographic-and-code-conventions-visual-basic"></a><span data-ttu-id="552ed-102">表記規則とコード規則 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="552ed-102">Typographic and Code Conventions (Visual Basic)</span></span>

<span data-ttu-id="552ed-103">Visual Basic のドキュメントでは、次の表記規則とコード規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="552ed-103">Visual Basic documentation uses the following typographic and code conventions.</span></span>  
  
## <a name="typographic-conventions"></a><span data-ttu-id="552ed-104">表記規則</span><span class="sxs-lookup"><span data-stu-id="552ed-104">Typographic Conventions</span></span>  
  
|<span data-ttu-id="552ed-105">例</span><span class="sxs-lookup"><span data-stu-id="552ed-105">Example</span></span>|<span data-ttu-id="552ed-106">説明</span><span class="sxs-lookup"><span data-stu-id="552ed-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="552ed-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span><span class="sxs-lookup"><span data-stu-id="552ed-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span></span>|<span data-ttu-id="552ed-108">言語固有のキーワードとランタイム メンバーは、先頭文字が大文字であり、この例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-108">Language-specific keywords and runtime members have initial uppercase letters and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="552ed-109">**SmallProject**、**ButtonCollection**</span><span class="sxs-lookup"><span data-stu-id="552ed-109">**SmallProject**, **ButtonCollection**</span></span>|<span data-ttu-id="552ed-110">入力を求められる語句は、この例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-110">Words and phrases you are instructed to type are formatted as shown in this example.</span></span>|  
|[<span data-ttu-id="552ed-111">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="552ed-111">Module Statement</span></span>](statements/module-statement.md)|<span data-ttu-id="552ed-112">別のヘルプ ページにアクセスするためにクリックするリンクは、この例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-112">Links you can click to go to another Help page are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="552ed-113">*object*、*variableName*、`argumentList`</span><span class="sxs-lookup"><span data-stu-id="552ed-113">*object*, *variableName*, `argumentList`</span></span>|<span data-ttu-id="552ed-114">指定する情報のプレースホルダーは、この例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-114">Placeholders for information that you supply are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="552ed-115">[ Shadows ]、[ *expressionList* ]</span><span class="sxs-lookup"><span data-stu-id="552ed-115">[ Shadows ], [ *expressionList* ]</span></span>|<span data-ttu-id="552ed-116">構文では、省略可能な項目は角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="552ed-116">In syntax, optional items are enclosed in brackets.</span></span>|  
|<span data-ttu-id="552ed-117">{ `Public` &#124; `Friend` &#124; `Private` }</span><span class="sxs-lookup"><span data-stu-id="552ed-117">{ `Public` &#124; `Friend` &#124; `Private` }</span></span>|<span data-ttu-id="552ed-118">構文で、2 つ以上の項目のいずれかを選択する必要がある場合、項目は中かっこで囲まれ、縦棒で区切られます。</span><span class="sxs-lookup"><span data-stu-id="552ed-118">In syntax, when you must make a choice between two or more items, the items are enclosed in braces and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="552ed-119">項目を 1 つだけ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="552ed-119">You must select one, and only one, of the items.</span></span>|  
|<span data-ttu-id="552ed-120">[ `Protected` &#124; `Friend` ]</span><span class="sxs-lookup"><span data-stu-id="552ed-120">[ `Protected` &#124; `Friend` ]</span></span>|<span data-ttu-id="552ed-121">構文で、2 つ以上の項目から任意で選択できる場合、項目は角かっこで囲まれ、縦棒で区切られます。</span><span class="sxs-lookup"><span data-stu-id="552ed-121">In syntax, when you have the option of selecting between two or more items, the items are enclosed in square brackets and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="552ed-122">項目は自由に組み合わせて選択でき、項目をまったく選択しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="552ed-122">You can select any combination of the items, or no item.</span></span>|  
|<span data-ttu-id="552ed-123">[{ `ByVal` &#124; `ByRef` }]</span><span class="sxs-lookup"><span data-stu-id="552ed-123">[{ `ByVal` &#124; `ByRef` }]</span></span>|<span data-ttu-id="552ed-124">構文で、項目を 1 つのみ選択できるが、項目を完全に省略することもできる場合、これらの項目は、中かっこで囲まれて角かっこで囲まれ、縦棒で区切られます。</span><span class="sxs-lookup"><span data-stu-id="552ed-124">In syntax, when you can select no more than one item, but you can also omit the items completely, the items are enclosed in square brackets surrounded by braces and separated by vertical bars.</span></span>|  
|<span data-ttu-id="552ed-125">*memberName*1、*memberName*2、*memberName*3</span><span class="sxs-lookup"><span data-stu-id="552ed-125">*memberName*1, *memberName*2, *memberName*3</span></span>|<span data-ttu-id="552ed-126">同じプレースホルダーの複数のインスタンスは、例に示すように、添字により区別されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-126">Multiple instances of the same placeholder are differentiated by subscripts, as shown in the example.</span></span>|  
|<span data-ttu-id="552ed-127">*memberName1*</span><span class="sxs-lookup"><span data-stu-id="552ed-127">*memberName1*</span></span><br /><br /> <span data-ttu-id="552ed-128">...</span><span class="sxs-lookup"><span data-stu-id="552ed-128">...</span></span><br /><br /> <span data-ttu-id="552ed-129">*memberNameN*</span><span class="sxs-lookup"><span data-stu-id="552ed-129">*memberNameN*</span></span>|<span data-ttu-id="552ed-130">構文では、省略記号 (...) を使用して、省略記号の直前にある種類の項目の数が不定であることを示します。</span><span class="sxs-lookup"><span data-stu-id="552ed-130">In syntax, an ellipsis (...) is used to indicate an indefinite number of items of the kind immediately in front of the ellipsis.</span></span><br /><br /> <span data-ttu-id="552ed-131">コード内の省略記号は、わかりやすくするために省略されたコードを示します。</span><span class="sxs-lookup"><span data-stu-id="552ed-131">In code, ellipses signify code omitted for the sake of clarity.</span></span>|  
|<span data-ttu-id="552ed-132">ESC、ENTER</span><span class="sxs-lookup"><span data-stu-id="552ed-132">ESC, ENTER</span></span>|<span data-ttu-id="552ed-133">キーボードのキー名とキー シーケンスは、すべて大文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-133">Key names and key sequences on the keyboard appear in all uppercase letters.</span></span>|  
|<span data-ttu-id="552ed-134">Alt + F1</span><span class="sxs-lookup"><span data-stu-id="552ed-134">ALT+F1</span></span>|<span data-ttu-id="552ed-135">各キー名の間にプラス記号 (+) が表示されている場合は、一方のキーを押しながらもう一方のキーを押す必要があります。</span><span class="sxs-lookup"><span data-stu-id="552ed-135">When plus signs (+) appear between key names, you must hold down one key while pressing the other.</span></span> <span data-ttu-id="552ed-136">たとえば、ALT + F1 は、ALT キーを押しながら F1 キーを押すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="552ed-136">For example, ALT+F1 means hold down the ALT key while pressing the F1 key.</span></span>|  
  
## <a name="code-conventions"></a><span data-ttu-id="552ed-137">コード規則</span><span class="sxs-lookup"><span data-stu-id="552ed-137">Code Conventions</span></span>  
  
|<span data-ttu-id="552ed-138">例</span><span class="sxs-lookup"><span data-stu-id="552ed-138">Example</span></span>|<span data-ttu-id="552ed-139">説明</span><span class="sxs-lookup"><span data-stu-id="552ed-139">Description</span></span>|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|<span data-ttu-id="552ed-140">コード サンプルは固定ピッチ フォントで表示され、次の例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-140">Code samples appear in a fixed-pitch font and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="552ed-141">上記のステートメントは、`sampleString` の値を "Hello, world!" に設定します</span><span class="sxs-lookup"><span data-stu-id="552ed-141">The previous statement sets the value of `sampleString` to "Hello, world!"</span></span>|<span data-ttu-id="552ed-142">次の例に示すように、説明文のコード要素は固定ピッチ フォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="552ed-142">Code elements in explanatory text appear in a fixed-pitch font, as shown in this example.</span></span>|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|<span data-ttu-id="552ed-143">コードのコメントは、アポストロフィ (') または REM キーワードで始まります。</span><span class="sxs-lookup"><span data-stu-id="552ed-143">Code comments are introduced by an apostrophe (') or the REM keyword.</span></span>|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|<span data-ttu-id="552ed-144">行の末尾にスペースに続いてアンダースコア (_) があるは、ステートメントが次の行に続くことを示します。</span><span class="sxs-lookup"><span data-stu-id="552ed-144">A space followed by an underscore ( _) at the end of a line indicates that the statement continues on the following line.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="552ed-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="552ed-145">See also</span></span>

- [<span data-ttu-id="552ed-146">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="552ed-146">Visual Basic Language Reference</span></span>](index.md)
- [<span data-ttu-id="552ed-147">キーワード</span><span class="sxs-lookup"><span data-stu-id="552ed-147">Keywords</span></span>](keywords/index.md)
- [<span data-ttu-id="552ed-148">Visual Basic ランタイム ライブラリのメンバー</span><span class="sxs-lookup"><span data-stu-id="552ed-148">Visual Basic Runtime Library Members</span></span>](runtime-library-members.md)
- [<span data-ttu-id="552ed-149">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="552ed-149">Visual Basic Naming Conventions</span></span>](../programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="552ed-150">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="552ed-150">How to: Break and Combine Statements in Code</span></span>](../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="552ed-151">コード内のコメント</span><span class="sxs-lookup"><span data-stu-id="552ed-151">Comments in Code</span></span>](../programming-guide/program-structure/comments-in-code.md)

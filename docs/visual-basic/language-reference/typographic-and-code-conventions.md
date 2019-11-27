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
ms.openlocfilehash: 4906c5ebadb7ce77f2d0e53b2fc5dbab69c5b41f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352711"
---
# <a name="typographic-and-code-conventions-visual-basic"></a><span data-ttu-id="14ed0-102">表記規則とコード規則 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14ed0-102">Typographic and Code Conventions (Visual Basic)</span></span>

<span data-ttu-id="14ed0-103">Visual Basic のドキュメントでは、次の表記規則とコード規則に従って記述されています。</span><span class="sxs-lookup"><span data-stu-id="14ed0-103">Visual Basic documentation uses the following typographic and code conventions.</span></span>  
  
## <a name="typographic-conventions"></a><span data-ttu-id="14ed0-104">表記規則</span><span class="sxs-lookup"><span data-stu-id="14ed0-104">Typographic Conventions</span></span>  
  
|<span data-ttu-id="14ed0-105">例</span><span class="sxs-lookup"><span data-stu-id="14ed0-105">Example</span></span>|<span data-ttu-id="14ed0-106">説明</span><span class="sxs-lookup"><span data-stu-id="14ed0-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14ed0-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span><span class="sxs-lookup"><span data-stu-id="14ed0-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span></span>|<span data-ttu-id="14ed0-108">Visual Basic 特有のキーワードやランタイム メンバは、太字で先頭を大文字にして表記します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-108">Language-specific keywords and runtime members have initial uppercase letters and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="14ed0-109">**SmallProject**、 **buttoncollection**</span><span class="sxs-lookup"><span data-stu-id="14ed0-109">**SmallProject**, **ButtonCollection**</span></span>|<span data-ttu-id="14ed0-110">入力する語句は、次の例に示すように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-110">Words and phrases you are instructed to type are formatted as shown in this example.</span></span>|  
|[<span data-ttu-id="14ed0-111">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="14ed0-111">Module Statement</span></span>](../../visual-basic/language-reference/statements/module-statement.md)|<span data-ttu-id="14ed0-112">別のヘルプページにアクセスするためにクリックできるリンクは、この例に示すように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="14ed0-112">Links you can click to go to another Help page are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="14ed0-113">*object*、 *variableName*、`argumentList`</span><span class="sxs-lookup"><span data-stu-id="14ed0-113">*object*, *variableName*, `argumentList`</span></span>|<span data-ttu-id="14ed0-114">指定する情報のプレースホルダーは、次の例に示すように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-114">Placeholders for information that you supply are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="14ed0-115">[影]、[*式の一覧*]</span><span class="sxs-lookup"><span data-stu-id="14ed0-115">[ Shadows ], [ *expressionList* ]</span></span>|<span data-ttu-id="14ed0-116">構文では、省略可能な項目が角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="14ed0-116">In syntax, optional items are enclosed in brackets.</span></span>|  
|<span data-ttu-id="14ed0-117">{`Public` &#124; `Friend` &#124; `Private`}</span><span class="sxs-lookup"><span data-stu-id="14ed0-117">{ `Public` &#124; `Friend` &#124; `Private` }</span></span>|<span data-ttu-id="14ed0-118">構文では、2つ以上の項目のいずれかを選択する必要がある場合、項目は中かっこで囲まれ、縦棒で区切られます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-118">In syntax, when you must make a choice between two or more items, the items are enclosed in braces and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="14ed0-119">項目を1つだけ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14ed0-119">You must select one, and only one, of the items.</span></span>|  
|<span data-ttu-id="14ed0-120">[`Protected` &#124; `Friend`]</span><span class="sxs-lookup"><span data-stu-id="14ed0-120">[ `Protected` &#124; `Friend` ]</span></span>|<span data-ttu-id="14ed0-121">構文では、2つ以上の項目を選択するオプションがある場合、項目は角かっこで囲まれ、縦棒で区切られます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-121">In syntax, when you have the option of selecting between two or more items, the items are enclosed in square brackets and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="14ed0-122">項目の任意の組み合わせを選択することも、項目を使用しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-122">You can select any combination of the items, or no item.</span></span>|  
|<span data-ttu-id="14ed0-123">[{`ByVal` &#124; `ByRef`}]</span><span class="sxs-lookup"><span data-stu-id="14ed0-123">[{ `ByVal` &#124; `ByRef` }]</span></span>|<span data-ttu-id="14ed0-124">構文では、複数の項目を選択できますが、項目を完全に省略することもできます。これらの項目は、中かっこで囲まれ、縦棒で区切られて角かっこで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-124">In syntax, when you can select no more than one item, but you can also omit the items completely, the items are enclosed in square brackets surrounded by braces and separated by vertical bars.</span></span>|  
|<span data-ttu-id="14ed0-125">*membername*1、 *Membername*2、 *membername*3</span><span class="sxs-lookup"><span data-stu-id="14ed0-125">*memberName*1, *memberName*2, *memberName*3</span></span>|<span data-ttu-id="14ed0-126">同じプレースホルダーの複数のインスタンスは、例に示すように、添字によって区別されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-126">Multiple instances of the same placeholder are differentiated by subscripts, as shown in the example.</span></span>|  
|<span data-ttu-id="14ed0-127">*memberName1*</span><span class="sxs-lookup"><span data-stu-id="14ed0-127">*memberName1*</span></span><br /><br /> <span data-ttu-id="14ed0-128">...</span><span class="sxs-lookup"><span data-stu-id="14ed0-128">...</span></span><br /><br /> <span data-ttu-id="14ed0-129">*memberNameN*</span><span class="sxs-lookup"><span data-stu-id="14ed0-129">*memberNameN*</span></span>|<span data-ttu-id="14ed0-130">構文では、省略記号 (...) を使用して、省略記号の直前にある種類の項目の不定数を示します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-130">In syntax, an ellipsis (...) is used to indicate an indefinite number of items of the kind immediately in front of the ellipsis.</span></span><br /><br /> <span data-ttu-id="14ed0-131">コードでは、省略記号はわかりやすくするために省略されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-131">In code, ellipses signify code omitted for the sake of clarity.</span></span>|  
|<span data-ttu-id="14ed0-132">ESC, ENTER</span><span class="sxs-lookup"><span data-stu-id="14ed0-132">ESC, ENTER</span></span>|<span data-ttu-id="14ed0-133">キーボードのキー名とキーシーケンスは、すべて大文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-133">Key names and key sequences on the keyboard appear in all uppercase letters.</span></span>|  
|<span data-ttu-id="14ed0-134">ALT + F1</span><span class="sxs-lookup"><span data-stu-id="14ed0-134">ALT+F1</span></span>|<span data-ttu-id="14ed0-135">プラス記号 (+) は、キーの組み合わせを表します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-135">When plus signs (+) appear between key names, you must hold down one key while pressing the other.</span></span> <span data-ttu-id="14ed0-136">たとえば、Alt + F1 は Alt キーを押しながら、F1 キーを押すことを表します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-136">For example, ALT+F1 means hold down the ALT key while pressing the F1 key.</span></span>|  
  
## <a name="code-conventions"></a><span data-ttu-id="14ed0-137">コード規則</span><span class="sxs-lookup"><span data-stu-id="14ed0-137">Code Conventions</span></span>  
  
|<span data-ttu-id="14ed0-138">例</span><span class="sxs-lookup"><span data-stu-id="14ed0-138">Example</span></span>|<span data-ttu-id="14ed0-139">説明</span><span class="sxs-lookup"><span data-stu-id="14ed0-139">Description</span></span>|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|<span data-ttu-id="14ed0-140">コードサンプルは固定ピッチフォントで表示され、次の例に示すように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-140">Code samples appear in a fixed-pitch font and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="14ed0-141">前のステートメントにより、`sampleString` の値が "Hello, world!" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-141">The previous statement sets the value of `sampleString` to "Hello, world!"</span></span>|<span data-ttu-id="14ed0-142">説明のテキスト内のコード要素は、この例で示すように固定ピッチ フォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-142">Code elements in explanatory text appear in a fixed-pitch font, as shown in this example.</span></span>|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|<span data-ttu-id="14ed0-143">コードコメントは、アポストロフィ (') または REM キーワードによって導入されます。</span><span class="sxs-lookup"><span data-stu-id="14ed0-143">Code comments are introduced by an apostrophe (') or the REM keyword.</span></span>|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|<span data-ttu-id="14ed0-144">行の末尾にスペースとアンダースコア (_) が続く場合は、ステートメントが次の行で続行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="14ed0-144">A space followed by an underscore ( _) at the end of a line indicates that the statement continues on the following line.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14ed0-145">参照</span><span class="sxs-lookup"><span data-stu-id="14ed0-145">See also</span></span>

- [<span data-ttu-id="14ed0-146">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="14ed0-146">Visual Basic Language Reference</span></span>](../../visual-basic/language-reference/index.md)
- [<span data-ttu-id="14ed0-147">キーワード</span><span class="sxs-lookup"><span data-stu-id="14ed0-147">Keywords</span></span>](../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="14ed0-148">Visual Basic ランタイム ライブラリのメンバー</span><span class="sxs-lookup"><span data-stu-id="14ed0-148">Visual Basic Runtime Library Members</span></span>](../../visual-basic/language-reference/runtime-library-members.md)
- [<span data-ttu-id="14ed0-149">Visual Basic 名前付け規則</span><span class="sxs-lookup"><span data-stu-id="14ed0-149">Visual Basic Naming Conventions</span></span>](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="14ed0-150">方法 : コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="14ed0-150">How to: Break and Combine Statements in Code</span></span>](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="14ed0-151">コード内のコメント</span><span class="sxs-lookup"><span data-stu-id="14ed0-151">Comments in Code</span></span>](../../visual-basic/programming-guide/program-structure/comments-in-code.md)

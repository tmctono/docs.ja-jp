---
title: '方法: コード内でのステートメントの分割と結合 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: a0a77b161d81271a4cb7eecf2982a287debee6a5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991725"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="94303-102">方法: コード内でのステートメントの分割と結合 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94303-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>

<span data-ttu-id="94303-103">コードを記述するときに、コードエディターで水平スクロールを必要とする長いステートメントを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="94303-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="94303-104">これはコードの実行方法には影響しませんが、モニターに表示されるコードをユーザーまたは他のユーザーが読み取ることが困難になります。</span><span class="sxs-lookup"><span data-stu-id="94303-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="94303-105">このような場合は、1つの long ステートメントを複数の行に分割することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="94303-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>

## <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="94303-106">1つのステートメントを複数の行に分割するには</span><span class="sxs-lookup"><span data-stu-id="94303-106">To break a single statement into multiple lines</span></span>

<span data-ttu-id="94303-107">行連結文字を使用します。これは、改行`_`する位置で、アンダースコア () です。</span><span class="sxs-lookup"><span data-stu-id="94303-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="94303-108">アンダースコアは、直後にスペースを付け、その直後に行終端記号 (キャリッジリターン) を付けるか、または (バージョン16.0 以降) コメントの後に復帰を続けます。</span><span class="sxs-lookup"><span data-stu-id="94303-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span>

  > [!NOTE]
  > <span data-ttu-id="94303-109">場合によっては、行連結文字を省略すると、Visual Basic コンパイラは、次のコード行でステートメントを暗黙的に続行します。</span><span class="sxs-lookup"><span data-stu-id="94303-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="94303-110">行連結文字を省略できる構文要素の一覧については、「[ステートメント](../../../visual-basic/programming-guide/language-features/statements.md)」の「暗黙的な行の連結」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94303-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>

  <span data-ttu-id="94303-111">次の例では、ステートメントは、行連結文字が最後の行以外のすべてを終了する4行に分割されます。</span><span class="sxs-lookup"><span data-stu-id="94303-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  <span data-ttu-id="94303-112">このシーケンスを使用すると、コードがオンラインでも印刷時でも読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="94303-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>

  <span data-ttu-id="94303-113">行連結文字は、行の最後の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="94303-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="94303-114">同じ行の他の何にも従うことはできません。</span><span class="sxs-lookup"><span data-stu-id="94303-114">You can't follow it with anything else on the same line.</span></span>

  <span data-ttu-id="94303-115">行連結文字を使用できる場所については、いくつかの制限があります。たとえば、引数名の途中で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="94303-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="94303-116">行連結文字を使用して引数リストを分割することはできますが、引数の個々の名前はそのままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="94303-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>

  <span data-ttu-id="94303-117">行連結文字を使用してコメントを続行することはできません。</span><span class="sxs-lookup"><span data-stu-id="94303-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="94303-118">コンパイラは、コメント内の文字が特別な意味を持つかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="94303-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="94303-119">複数行のコメントの場合は、各行でコメント記号`'`() を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94303-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>

 <span data-ttu-id="94303-120">各ステートメントを別々の行に配置することをお勧めしますが、Visual Basic 複数のステートメントを同じ行に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="94303-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>

## <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="94303-121">複数のステートメントを同じ行に配置するには</span><span class="sxs-lookup"><span data-stu-id="94303-121">To place multiple statements on the same line</span></span>

<span data-ttu-id="94303-122">次の例のように、`:`ステートメントをコロン () で区切ります。</span><span class="sxs-lookup"><span data-stu-id="94303-122">Separate the statements with a colon (`:`), as in the following example:</span></span>

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a><span data-ttu-id="94303-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="94303-123">See also</span></span>

- [<span data-ttu-id="94303-124">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="94303-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="94303-125">ステートメント</span><span class="sxs-lookup"><span data-stu-id="94303-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

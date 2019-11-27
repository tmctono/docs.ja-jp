---
title: 名前付け規則
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347320"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="2ea2d-102">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="2ea2d-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="2ea2d-103">Visual Basic アプリケーションの要素に名前を付けるときは、その名前の最初の文字は、英字またはアンダー スコアにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="2ea2d-104">ただし、アンダースコアで始まる名前は、[言語に依存しないコンポーネント](../../../standard/language-independence-and-language-independent-components.md)(CLS) に準拠していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="2ea2d-105">次の提案が、名前付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="2ea2d-106">`FindLastRecord` と `RedrawMyForm`のように、名前に含まれる各単語の大文字を大文字にして開始します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="2ea2d-107">`InitNameArray` または `CloseDialog`のように、動詞を使用して関数名とメソッド名を開始します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="2ea2d-108">`EmployeeName` または `CarAccessory`のように、クラス、構造体、モジュール、およびプロパティの名前を名詞で開始します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="2ea2d-109">"I" というプレフィックスを使用してインターフェイス名を開始し、`IComponent`のように名詞または名詞句を続けます。または、`IPersistable`のように、インターフェイスの動作を記述する形容詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="2ea2d-110">アンダー スコアは使用しないで、略語の使用も控えてください。 なぜなら略語は混乱を招くからです。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="2ea2d-111">"`MouseEventHandler`" のように、イベントの種類と "`EventHandler`" サフィックスが記述されている名詞を使用して、イベントハンドラー名を開始します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="2ea2d-112">イベント引数クラスの名前には、"`EventArgs`" サフィックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="2ea2d-113">イベントの概念が "before" または "after" の場合は、"`ControlAdd`" または "`ControlAdded`" のように、現在または過去の形でサフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="2ea2d-114">長い、または頻繁に使用される用語では、名前の長さを適切に維持するために略語を使用します。 たとえば、"Hypertext Markup Language"の代わりに"HTML"を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="2ea2d-115">一般的に、32 文字を超える変数の名前は低解像度のモニターでは読むことが困難です。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="2ea2d-116">また、略語はアプリケーション全体を通して一貫性のあるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="2ea2d-117">プロジェクトの中で"HTML"と"Hypertext Markup Language"をランダムに切り替えることは混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="2ea2d-118">外部スコープで使われている名前と同じものを、内部スコープの中で使用することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="2ea2d-119">誤った変数がアクセスされた場合エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="2ea2d-120">同名のキーワードと変数の間でコンフリクトが起きる場合、適切な種類のライブラリを使って先立ってキーワードを識別しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="2ea2d-121">たとえば、`Date`という変数がある場合は、<xref:System.DateTime.Date%2A?displayProperty=nameWithType>を呼び出すことによってのみ、組み込みの `Date` 関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea2d-122">参照</span><span class="sxs-lookup"><span data-stu-id="2ea2d-122">See also</span></span>

- [<span data-ttu-id="2ea2d-123">コード内の要素名としてのキーワード</span><span class="sxs-lookup"><span data-stu-id="2ea2d-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="2ea2d-124">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="2ea2d-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="2ea2d-125">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="2ea2d-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="2ea2d-126">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="2ea2d-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="2ea2d-127">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ea2d-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)

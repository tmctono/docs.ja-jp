---
title: Declared Element Names
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: e8620517b934a5f1a97ea25c5a94c8b932bb47b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345427"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="924dc-102">宣言された要素の名前 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="924dc-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="924dc-103">宣言されたすべての要素には、*識別子*とも呼ばれる名前が付いています。これは、コードがそれを参照するために使用します。</span><span class="sxs-lookup"><span data-stu-id="924dc-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="924dc-104">ルール</span><span class="sxs-lookup"><span data-stu-id="924dc-104">Rules</span></span>  
 <span data-ttu-id="924dc-105">Visual Basic 内の要素名は、次の規則を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="924dc-106">先頭には、アルファベット文字またはアンダースコア (`_`) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="924dc-107">アルファベット、数字、およびアンダースコアのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="924dc-108">アンダースコアで始まる場合は、少なくとも1つのアルファベット文字または10進数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="924dc-109">長さは1023文字以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="924dc-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="924dc-110">1023文字の長さの制限は、`outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`など、完全修飾名の文字列全体にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="924dc-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="924dc-111">次の例は、有効な要素名を示しています。</span><span class="sxs-lookup"><span data-stu-id="924dc-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="924dc-112">次の例は、無効な要素名を示しています。</span><span class="sxs-lookup"><span data-stu-id="924dc-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="924dc-113">最初のはアンダースコアのみを含み、2番目のは10進数の数字で始まり、3番目の文字には無効な文字 ($) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="924dc-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="924dc-114">アンダースコア (`_`) で始まる要素名は、[言語に依存しないコンポーネント](../../../../standard/language-independence-and-language-independent-components.md)(cls) の一部ではないため、このような名前を定義するコンポーネントを cls 準拠のコードで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="924dc-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="924dc-115">ただし、要素名の他の位置にあるアンダースコアは CLS に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="924dc-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="924dc-116">名前の長さのガイドライン</span><span class="sxs-lookup"><span data-stu-id="924dc-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="924dc-117">実際には、要素の性質を明確に識別しながら、可能な限り短い名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="924dc-118">これにより、コードの読みやすさが向上し、行の長さとソースファイルのサイズが減少します。</span><span class="sxs-lookup"><span data-stu-id="924dc-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="924dc-119">一方、要素が表す内容と、コードでその要素がどのように使用されているかを正確に記述していない場合は、名前を短くするべきではありません。</span><span class="sxs-lookup"><span data-stu-id="924dc-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="924dc-120">これは、コードを読みやすくするために重要です。</span><span class="sxs-lookup"><span data-stu-id="924dc-120">This is important for the readability of your code.</span></span> <span data-ttu-id="924dc-121">他のユーザーがそれを理解しようとしている場合、または記述した後に長い時間を見ている場合は、適切な要素名を使用するとかなりの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="924dc-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="924dc-122">エスケープされた名前</span><span class="sxs-lookup"><span data-stu-id="924dc-122">Escaped Names</span></span>  
 <span data-ttu-id="924dc-123">一般に、要素名は、Visual Basic によって予約されているキーワード (`Case` や `Friend`など) と一致しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="924dc-124">ただし、エスケープされた*名前*を定義することもできます。これは、角かっこ (`[ ]`) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="924dc-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="924dc-125">エスケープされた名前は、角かっこによってあいまいさが解消されるため、任意の Visual Basic キーワードと一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="924dc-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="924dc-126">また、コード内で後で名前を参照するときにも、角かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="924dc-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="924dc-127">一般に、次の場合にのみ、エスケープされた名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-127">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="924dc-128">コードは、名前として使用されているキーワードを予約していない以前のバージョンの Visual Basic から移行されました。もしくは</span><span class="sxs-lookup"><span data-stu-id="924dc-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="924dc-129">指定されたキーワードが予約されていない別の言語で記述されたコードを操作しています。</span><span class="sxs-lookup"><span data-stu-id="924dc-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="924dc-130">それ以外の場合は、名前がキーワードと競合する場合は、要素の名前を変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="924dc-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="924dc-131">統合開発環境 (IDE: integrated development environment) を使用すると、簡単にこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="924dc-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="924dc-132">詳細については、「[リファクタリング](/visualstudio/ide/refactoring-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="924dc-132">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="924dc-133">名前の大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="924dc-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="924dc-134">Visual Basic の要素名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="924dc-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="924dc-135">つまり、コンパイラは、アルファベットの大文字と小文字が異なる2つの名前を比較するときに、同じ名前として解釈します。</span><span class="sxs-lookup"><span data-stu-id="924dc-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="924dc-136">たとえば、 `ABC` と `abc` は、宣言された同じ要素を参照していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="924dc-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="924dc-137">しかし、共通言語ランタイム (CLR) のバインディングでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="924dc-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="924dc-138">このため、アセンブリまたは DLL を作成し、他のアセンブリで使用できるようにすると、名前の大文字と小文字が区別されるようになります。</span><span class="sxs-lookup"><span data-stu-id="924dc-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="924dc-139">たとえば、 `ABC`という名前の要素を持つクラスを定義し、他のアセンブリから共通言語ランタイムを通じてこのクラスを使用する場合は、この要素を `ABC`として参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924dc-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="924dc-140">後でクラスを再コンパイルし、要素の名前を `abc`に変更した場合、クラスを使用している他のアセンブリは、その要素にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="924dc-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="924dc-141">したがって、アセンブリを更新してリリースするときは、パブリックな要素の名前の大文字と小文字を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="924dc-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="924dc-142">名前とロケール</span><span class="sxs-lookup"><span data-stu-id="924dc-142">Names and Locales</span></span>  
 <span data-ttu-id="924dc-143">名前の比較は、ロケールに依存しません。</span><span class="sxs-lookup"><span data-stu-id="924dc-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="924dc-144">2つの名前が1つのロケールで一致する場合は、すべてのロケールで一致することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="924dc-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924dc-145">参照</span><span class="sxs-lookup"><span data-stu-id="924dc-145">See also</span></span>

- [<span data-ttu-id="924dc-146">宣言された要素</span><span class="sxs-lookup"><span data-stu-id="924dc-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="924dc-147">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="924dc-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="924dc-148">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="924dc-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="924dc-149">ステートメント</span><span class="sxs-lookup"><span data-stu-id="924dc-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

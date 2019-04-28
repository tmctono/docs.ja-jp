---
title: 宣言された要素の名前 (Visual Basic)
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
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61828621"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="c4ec8-102">宣言された要素の名前 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4ec8-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="c4ec8-103">宣言された各要素とも呼ばれる、名前を持つ、*識別子*、これは、コードを使用して、それを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c4ec8-104">ルール</span><span class="sxs-lookup"><span data-stu-id="c4ec8-104">Rules</span></span>  
 <span data-ttu-id="c4ec8-105">Visual Basic では、要素名は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="c4ec8-106">文字は英字またはアンダー スコアで始まる必要がありますが (`_`)。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="c4ec8-107">アルファベット文字、10 進数字およびアンダー スコアのみでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="c4ec8-108">アンダー スコアで始まる場合、少なくとも 1 つのアルファベット文字または 10 進数字でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="c4ec8-109">長さが 1023 文字はできません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="c4ec8-110">1023 文字の長さの制限にも適用されます、完全修飾名では、文字列全体など`outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="c4ec8-111">次の例では、有効な要素名を示します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="c4ec8-112">次の例では、無効な要素名を示します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="c4ec8-113">最初にアンダー スコアのみが含まれています、10 進数字の場合は、始まり、2 つ目および 3 番目に無効な文字 ($) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="c4ec8-114">アンダー スコアで始まる要素名 (`_`) は含まれません、 [Language Independence and Language-independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS) にため、CLS 準拠コードのような名前を定義するコンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="c4ec8-115">ただし、要素名の他の任意の位置でアンダー スコアは CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="c4ec8-116">名前の長さのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c4ec8-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="c4ec8-117">実際には、名前はできるだけ短く中の要素の特性を明確にします。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="c4ec8-118">これは、コードの読みやすさが向上し、行の長さとソース ファイルのサイズを縮小します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="c4ec8-119">その一方で、自分の名前は、いない適切に記述できる要素が表す内容と、コードがそれを使用する方法長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="c4ec8-120">これは、コードの読みやすさにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-120">This is important for the readability of your code.</span></span> <span data-ttu-id="c4ec8-121">それを理解しようとする他の人がいる場合、または自分で探している場合に作成した後、長い時間は、適切な要素名は、かなりの時間を保存できます。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="c4ec8-122">エスケープされた名前</span><span class="sxs-lookup"><span data-stu-id="c4ec8-122">Escaped Names</span></span>  
 <span data-ttu-id="c4ec8-123">一般に、要素名に一致しないなど、Visual Basic では、によって予約済みキーワードのいずれかの`Case`または`Friend`します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="c4ec8-124">ただし、定義することができます、*エスケープ名前*、角かっこで囲まれている (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="c4ec8-125">エスケープされた名前は、角かっこは、任意のあいまいさをなくすために、Visual Basic のキーワードを照合できます。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="c4ec8-126">後続のコードで名前を参照する場合は、角かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="c4ec8-127">一般に、エスケープされた名前を使用する必要がある場合にのみ。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-127">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="c4ec8-128">コードが名前として使用されているキーワードが確保されていない Visual Basic の以前のバージョンから移行します。または</span><span class="sxs-lookup"><span data-stu-id="c4ec8-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="c4ec8-129">指定されたキーワードが予約されていない別の言語で記述されたコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="c4ec8-130">それ以外の場合、キーワードを使用してその名前が競合する場合、要素名の変更を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="c4ec8-131">統合開発環境 (IDE) では、これを行う簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="c4ec8-132">詳細については、次を参照してください。[リファクタリング](/visualstudio/vb-ide/refactoring-vb)します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="c4ec8-133">名前に大文字小文字の区別</span><span class="sxs-lookup"><span data-stu-id="c4ec8-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="c4ec8-134">Visual Basic での要素名は大文字です。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="c4ec8-135">これは、コンパイラは、英字の大文字小文字のみが異なる 2 つの名前を比較をする際を解釈するには同じ名前としてことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="c4ec8-136">たとえば、 `ABC` と `abc` は、宣言された同じ要素を参照していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="c4ec8-137">ただし、共通言語ランタイム (CLR) は、大文字のバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="c4ec8-138">このため、アセンブリまたは DLL を作成し、他のアセンブリで使用できるようにすると、名前の大文字と小文字が区別されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="c4ec8-139">たとえば、 `ABC`という名前の要素を持つクラスを定義し、他のアセンブリから共通言語ランタイムを通じてこのクラスを使用する場合は、この要素を `ABC`として参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="c4ec8-140">かどうか、その後、クラスを再コンパイルして要素の名前を変更`abc`クラスを使用して、他のアセンブリがその要素にアクセスできなくします。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="c4ec8-141">したがって、アセンブリを更新してリリースするときは、パブリックな要素の名前の大文字と小文字を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="c4ec8-142">名前とロケール</span><span class="sxs-lookup"><span data-stu-id="c4ec8-142">Names and Locales</span></span>  
 <span data-ttu-id="c4ec8-143">名前の比較ではロケールに依存しません。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="c4ec8-144">1 つのロケールで 2 つの名前が同じ場合は、すべてのロケールに一致するように保証されます。</span><span class="sxs-lookup"><span data-stu-id="c4ec8-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ec8-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4ec8-145">See also</span></span>

- [<span data-ttu-id="c4ec8-146">宣言された要素</span><span class="sxs-lookup"><span data-stu-id="c4ec8-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="c4ec8-147">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="c4ec8-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="c4ec8-148">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="c4ec8-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c4ec8-149">ステートメント</span><span class="sxs-lookup"><span data-stu-id="c4ec8-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

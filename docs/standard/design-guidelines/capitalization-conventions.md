---
title: 大文字の使用規則
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: fee7f5b7749c97a87e37581f67cbe1b49250b9ce
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709531"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="347b0-102">大文字の使用規則</span><span class="sxs-lookup"><span data-stu-id="347b0-102">Capitalization Conventions</span></span>
<span data-ttu-id="347b0-103">この章のガイドラインでは、一貫して適用されている場合に、型、メンバー、およびパラメーターの識別子を読みやすくするための簡単な方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="347b0-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="347b0-104">識別子の大文字小文字の規則</span><span class="sxs-lookup"><span data-stu-id="347b0-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="347b0-105">識別子内の単語を区別するには、識別子内の各単語の最初の文字を大文字にします。</span><span class="sxs-lookup"><span data-stu-id="347b0-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="347b0-106">語句を区別するためにアンダースコアを使用したり、識別子内の任意の場所で単語を区別したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="347b0-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="347b0-107">識別子の使用方法によっては、次の2つの適切な方法で識別子を大文字にすることができます。</span><span class="sxs-lookup"><span data-stu-id="347b0-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
- <span data-ttu-id="347b0-108">パスワードの大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="347b0-108">PascalCasing</span></span>  
  
- <span data-ttu-id="347b0-109">キャメル</span><span class="sxs-lookup"><span data-stu-id="347b0-109">camelCasing</span></span>  
  
 <span data-ttu-id="347b0-110">次の例に示すように、パラメーター名を除くすべての識別子に使用される、文字表記規則は、各単語の最初の文字 (長さが2文字を超える頭字語を含む) を大文字にします。</span><span class="sxs-lookup"><span data-stu-id="347b0-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="347b0-111">次の識別子に示されているように、2文字の頭字語では、両方の文字が大文字になります。</span><span class="sxs-lookup"><span data-stu-id="347b0-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="347b0-112">次の例に示すように、キャメル規則は、パラメーター名に対してのみ使用され、最初の単語を除く各単語の最初の文字を大文字にします。</span><span class="sxs-lookup"><span data-stu-id="347b0-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="347b0-113">この例に示すように、camel 形式の識別子を開始する2文字の頭字語は両方とも小文字です。</span><span class="sxs-lookup"><span data-stu-id="347b0-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="347b0-114">**✓ DO** すべてパブリック メンバー、種類、および名前空間の名前を複数の単語で構成される pascal 表記を使用を使用します。</span><span class="sxs-lookup"><span data-stu-id="347b0-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="347b0-115">**✓ DO** パラメーター名の camel 表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="347b0-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="347b0-116">次の表では、さまざまな種類の識別子の大文字と小文字の規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="347b0-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="347b0-117">識別子</span><span class="sxs-lookup"><span data-stu-id="347b0-117">Identifier</span></span>|<span data-ttu-id="347b0-118">大文字小文字の区別</span><span class="sxs-lookup"><span data-stu-id="347b0-118">Casing</span></span>|<span data-ttu-id="347b0-119">使用例</span><span class="sxs-lookup"><span data-stu-id="347b0-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="347b0-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="347b0-120">Namespace</span></span>|<span data-ttu-id="347b0-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="347b0-122">の型</span><span class="sxs-lookup"><span data-stu-id="347b0-122">Type</span></span>|<span data-ttu-id="347b0-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="347b0-124">Interface</span><span class="sxs-lookup"><span data-stu-id="347b0-124">Interface</span></span>|<span data-ttu-id="347b0-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="347b0-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="347b0-126">Method</span></span>|<span data-ttu-id="347b0-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="347b0-128">property</span><span class="sxs-lookup"><span data-stu-id="347b0-128">Property</span></span>|<span data-ttu-id="347b0-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="347b0-130">Event</span><span class="sxs-lookup"><span data-stu-id="347b0-130">Event</span></span>|<span data-ttu-id="347b0-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="347b0-132">フィールド</span><span class="sxs-lookup"><span data-stu-id="347b0-132">Field</span></span>|<span data-ttu-id="347b0-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="347b0-134">列挙値</span><span class="sxs-lookup"><span data-stu-id="347b0-134">Enum value</span></span>|<span data-ttu-id="347b0-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="347b0-136">パラメータ</span><span class="sxs-lookup"><span data-stu-id="347b0-136">Parameter</span></span>|<span data-ttu-id="347b0-137">Camel</span><span class="sxs-lookup"><span data-stu-id="347b0-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="347b0-138">複合語と一般的な用語を大文字にする</span><span class="sxs-lookup"><span data-stu-id="347b0-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="347b0-139">ほとんどの複合用語は、大文字と小文字を区別するために1つの単語として扱われます。</span><span class="sxs-lookup"><span data-stu-id="347b0-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="347b0-140">**X DO NOT** いわゆる閉じたフォームの複合語内の各単語を大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="347b0-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="347b0-141">これらは、エンドポイントなどの1つの単語として記述された複合ワードです。</span><span class="sxs-lookup"><span data-stu-id="347b0-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="347b0-142">大文字と小文字のガイドラインのために、閉じた複合ワードを1つの単語として扱います。</span><span class="sxs-lookup"><span data-stu-id="347b0-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="347b0-143">現在のディクショナリを使用して、複合単語が閉じた形式で記述されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="347b0-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="347b0-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="347b0-144">Pascal</span></span>|<span data-ttu-id="347b0-145">Camel</span><span class="sxs-lookup"><span data-stu-id="347b0-145">Camel</span></span>|<span data-ttu-id="347b0-146">not</span><span class="sxs-lookup"><span data-stu-id="347b0-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="347b0-147">大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="347b0-147">Case Sensitivity</span></span>  
 <span data-ttu-id="347b0-148">CLR で実行できる言語は、大文字と小文字の区別をサポートするためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="347b0-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="347b0-149">お使いの言語でサポートされている場合でも、フレームワークにアクセスする可能性のある他の言語はありません。</span><span class="sxs-lookup"><span data-stu-id="347b0-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="347b0-150">したがって、外部からアクセスできるすべての Api では、同じコンテキスト内の2つの名前を区別するために大文字と小文字だけを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="347b0-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="347b0-151">**X DO NOT** すべてのプログラミング言語が大文字小文字を区別があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="347b0-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="347b0-152">しかし、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="347b0-152">They are not.</span></span> <span data-ttu-id="347b0-153">名前は大文字と小文字のみで異なることはできません。</span><span class="sxs-lookup"><span data-stu-id="347b0-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="347b0-154">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="347b0-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="347b0-155">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="347b0-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347b0-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="347b0-156">See also</span></span>

- [<span data-ttu-id="347b0-157">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="347b0-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="347b0-158">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="347b0-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

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
author: KrzysztofCwalina
ms.openlocfilehash: e0da4cd747846921d170d9c07d6f1fb91dbd4ed7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615248"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="47f15-102">大文字の使用規則</span><span class="sxs-lookup"><span data-stu-id="47f15-102">Capitalization Conventions</span></span>
<span data-ttu-id="47f15-103">この章のレイアウトを使用するための単純なメソッドのガイドラインは、型、メンバー、およびパラメーターを読みやすくする識別子を一貫した適用されるときに場合です。</span><span class="sxs-lookup"><span data-stu-id="47f15-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="47f15-104">識別子の大文字と小文字の規則</span><span class="sxs-lookup"><span data-stu-id="47f15-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="47f15-105">識別子内の単語を区別するためには、識別子内の各単語の最初の文字を大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="47f15-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="47f15-106">アンダー スコアは、単語を区別するために使用しないでくださいまたはさらに言えば、識別子で任意の場所。</span><span class="sxs-lookup"><span data-stu-id="47f15-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="47f15-107">識別子の使用によって、識別子を大文字に変換する 2 つの適切な方法はあります。</span><span class="sxs-lookup"><span data-stu-id="47f15-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
- <span data-ttu-id="47f15-108">Pascal 表記を使用</span><span class="sxs-lookup"><span data-stu-id="47f15-108">PascalCasing</span></span>  
  
- <span data-ttu-id="47f15-109">キャメル ケース</span><span class="sxs-lookup"><span data-stu-id="47f15-109">camelCasing</span></span>  
  
 <span data-ttu-id="47f15-110">Pascal 表記を使用規則は、パラメーター名を除くすべての識別子には、次の例に示すように、(2 文字の長さを頭字語を含む) の各単語の最初の文字を大文字になります。</span><span class="sxs-lookup"><span data-stu-id="47f15-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="47f15-111">特殊なケースは、次の識別子で示すように 2 文字の頭字語が両方の文字が大文字で入力に行われます。</span><span class="sxs-lookup"><span data-stu-id="47f15-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="47f15-112">キャメル ケース規約、パラメーター名では、専用に使用では、次の例に示すように、最初の単語以外の各単語の最初の文字が大文字にします。</span><span class="sxs-lookup"><span data-stu-id="47f15-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="47f15-113">例に示すも camel 形式の識別子を開始 2 文字の頭字語は小文字の両方です。</span><span class="sxs-lookup"><span data-stu-id="47f15-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="47f15-114">**✓ DO** すべてパブリック メンバー、種類、および名前空間の名前を複数の単語で構成される pascal 表記を使用を使用します。</span><span class="sxs-lookup"><span data-stu-id="47f15-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="47f15-115">**✓ DO** パラメーター名の camel 表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="47f15-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="47f15-116">次の表では、さまざまな種類の識別子の大文字と小文字の規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="47f15-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="47f15-117">識別子</span><span class="sxs-lookup"><span data-stu-id="47f15-117">Identifier</span></span>|<span data-ttu-id="47f15-118">大文字小文字の区別</span><span class="sxs-lookup"><span data-stu-id="47f15-118">Casing</span></span>|<span data-ttu-id="47f15-119">例</span><span class="sxs-lookup"><span data-stu-id="47f15-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="47f15-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="47f15-120">Namespace</span></span>|<span data-ttu-id="47f15-121">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="47f15-122">型</span><span class="sxs-lookup"><span data-stu-id="47f15-122">Type</span></span>|<span data-ttu-id="47f15-123">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="47f15-124">Interface</span><span class="sxs-lookup"><span data-stu-id="47f15-124">Interface</span></span>|<span data-ttu-id="47f15-125">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="47f15-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="47f15-126">Method</span></span>|<span data-ttu-id="47f15-127">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="47f15-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="47f15-128">Property</span></span>|<span data-ttu-id="47f15-129">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="47f15-130">イベント</span><span class="sxs-lookup"><span data-stu-id="47f15-130">Event</span></span>|<span data-ttu-id="47f15-131">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="47f15-132">フィールド</span><span class="sxs-lookup"><span data-stu-id="47f15-132">Field</span></span>|<span data-ttu-id="47f15-133">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="47f15-134">列挙値</span><span class="sxs-lookup"><span data-stu-id="47f15-134">Enum value</span></span>|<span data-ttu-id="47f15-135">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="47f15-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47f15-136">Parameter</span></span>|<span data-ttu-id="47f15-137">Camel 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="47f15-138">複合語の大文字と一般的な用語</span><span class="sxs-lookup"><span data-stu-id="47f15-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="47f15-139">ほとんどの複合語は、大文字と小文字の目的で 1 つの単語として扱われます。</span><span class="sxs-lookup"><span data-stu-id="47f15-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="47f15-140">**X DO NOT** いわゆる閉じたフォームの複合語内の各単語を大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="47f15-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="47f15-141">これらは、複合語のエンドポイントなど、1 つの単語として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="47f15-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="47f15-142">大文字と小文字のガイドラインについては、目的には、1 つの単語として閉じられたフォームの複合語を処理します。</span><span class="sxs-lookup"><span data-stu-id="47f15-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="47f15-143">現在のディクショナリを使用すると、複合語が閉じたフォームで記述されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="47f15-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="47f15-144">Pascal 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-144">Pascal</span></span>|<span data-ttu-id="47f15-145">Camel 形式</span><span class="sxs-lookup"><span data-stu-id="47f15-145">Camel</span></span>|<span data-ttu-id="47f15-146">Not</span><span class="sxs-lookup"><span data-stu-id="47f15-146">Not</span></span>|  
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
  
## <a name="case-sensitivity"></a><span data-ttu-id="47f15-147">大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="47f15-147">Case Sensitivity</span></span>  
 <span data-ttu-id="47f15-148">CLR で実行できる言語は、いくつかの操作を行いますが、大文字小文字の区別をサポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="47f15-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="47f15-149">お使いの言語をサポートしている場合でも、フレームワークにアクセスする他の言語は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="47f15-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="47f15-150">したがって、外部からアクセス可能であるすべての Api は、場合、同じコンテキストで 2 つの名前を区別するために単独で使用できません。</span><span class="sxs-lookup"><span data-stu-id="47f15-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="47f15-151">**X DO NOT** すべてのプログラミング言語が大文字小文字を区別があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="47f15-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="47f15-152">しかし、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="47f15-152">They are not.</span></span> <span data-ttu-id="47f15-153">大文字と小文字だけ名前が異なることはできません。</span><span class="sxs-lookup"><span data-stu-id="47f15-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="47f15-154">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="47f15-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="47f15-155">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="47f15-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f15-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="47f15-156">See also</span></span>

- [<span data-ttu-id="47f15-157">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="47f15-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="47f15-158">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="47f15-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

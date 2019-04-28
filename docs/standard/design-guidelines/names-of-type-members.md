---
title: 型のメンバーの名前
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
author: KrzysztofCwalina
ms.openlocfilehash: 7cf98b8ed1957352f357c7a9d580b4fd567a1634
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757496"
---
# <a name="names-of-type-members"></a><span data-ttu-id="e2ee7-102">型のメンバーの名前</span><span class="sxs-lookup"><span data-stu-id="e2ee7-102">Names of Type Members</span></span>
<span data-ttu-id="e2ee7-103">型は次のメンバーで構成されています: メソッド、プロパティ、イベント、コンストラクター、フィールド。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="e2ee7-104">次のセクションは、型のメンバーに名前を付けるためのガイドラインを示しています。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="e2ee7-105">メソッドの名前</span><span class="sxs-lookup"><span data-stu-id="e2ee7-105">Names of Methods</span></span>  
 <span data-ttu-id="e2ee7-106">メソッドはアクションを実行する手段であるため、デザインのガイドラインでは、メソッド名を動詞または動詞句にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="e2ee7-107">また、このガイドラインに従うと、名詞句または形容詞句であるプロパティ名および型名と、メソッド名を区別するためにも機能します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="e2ee7-108">**✓ DO** 動詞または動詞句は、メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="e2ee7-109">プロパティの名前</span><span class="sxs-lookup"><span data-stu-id="e2ee7-109">Names of Properties</span></span>  
 <span data-ttu-id="e2ee7-110">他のメンバーとは異なり、プロパティには名詞句または形容詞の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="e2ee7-111">つまり、プロパティはデータを参照するため、プロパティの名前にはデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="e2ee7-112">プロパティ名には、常に Pascal 形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="e2ee7-113">**✓ DO** 名詞、名詞句、または形容詞を使用してプロパティの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="e2ee7-114">**X DO NOT** 次の例のように、"Get"メソッドの名前に一致するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="e2ee7-115">通常、このパターンは、プロパティが実際にメソッドであることを示します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="e2ee7-116">**✓ DO** 後に"List"または"Collection"単数形の語句を使用する代わりに、コレクション内の項目を記述する複数形の語句でコレクションのプロパティの名前を付けます</span><span class="sxs-lookup"><span data-stu-id="e2ee7-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="e2ee7-117">**✓ DO** 肯定の語句でブール型プロパティの名前 (`CanSeek`の代わりに`CantSeek`)。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="e2ee7-118">必要に応じて、ブールプロパティの先頭に "Is"、 "Can"、または "Has"を追加することもできますが、値を追加する場合に限定します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="e2ee7-119">**✓ CONSIDER** プロパティの型と同じ名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="e2ee7-120">たとえば、次のプロパティは、`Color` という名前の列挙値を適切に取得および設定するため、プロパティは `Color` という名前になります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="e2ee7-121">イベントの名前</span><span class="sxs-lookup"><span data-stu-id="e2ee7-121">Names of Events</span></span>  
 <span data-ttu-id="e2ee7-122">イベントは常に、発生中のアクションまたは発生したアクションのいずれかのアクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="e2ee7-123">そのため、メソッドと同様、イベントには動詞の名前が付けられ、イベントが発生した時刻を示すために動詞の時制が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="e2ee7-124">**✓ DO** 動詞または動詞句を持つイベントの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="e2ee7-125">例として、`Clicked`、`Painting`、`DroppedDown` などがあります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="e2ee7-126">**✓ DO** 現在および過去時制を使用して、前後の概念でイベント名を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="e2ee7-127">たとえば、ウィンドウを閉じる前に発生するクローズ イベントは `Closing` と呼ばれ、ウィンドウを閉じた後に発生するクローズ イベントは `Closed` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="e2ee7-128">**X DO NOT** プレイベントとポストイベントを示す "Before" または "After"を接頭や接尾に使用しないでください。 前述の通り、現在と過去の時制を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="e2ee7-129">前述のように、現在形と過去形を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="e2ee7-130">**✓ DO** 次の例に示すように"EventHandler"サフィックスを持つイベント ハンドラー (デリゲートがイベントの種類として使用) の名前をつけます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="e2ee7-131">**✓ DO** イベント ハンドラーにおいては`sender`と`e`という 2 つのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="e2ee7-132">sender パラメーターは、イベントを発生させたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="e2ee7-133">より具体的な型を使用できる場合も、通常、sender パラメーターの型は `object` になります。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="e2ee7-134">**✓ DO** イベント引数クラス"EventArgs"サフィックスを持つ名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="e2ee7-135">フィールドの名前</span><span class="sxs-lookup"><span data-stu-id="e2ee7-135">Names of Fields</span></span>  
 <span data-ttu-id="e2ee7-136">フィールドの名前付けのガイドラインは、静的パブリック フィールドと保護されたフィールドを対象とします。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="e2ee7-137">内部フィールドとプライベート フィールドは、ガイドラインの対象ではありません。また、パブリック インスタンス フィールドや保護されたインスタンス フィールドは、「[メンバーのデザインのガイドライン](../../../docs/standard/design-guidelines/member.md)」で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="e2ee7-138">**✓ DO** フィールドの名前に PascalCasing を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="e2ee7-139">**✓ DO** 名詞、名詞句、または形容詞を使用してフィールドの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="e2ee7-140">**X DO NOT** フィールド名に接頭語を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="e2ee7-141">たとえば、静的フィールドを示すために、"g_" や "s_" を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e2ee7-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="e2ee7-142">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="e2ee7-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e2ee7-143">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="e2ee7-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ee7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2ee7-144">See also</span></span>

- [<span data-ttu-id="e2ee7-145">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e2ee7-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e2ee7-146">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e2ee7-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

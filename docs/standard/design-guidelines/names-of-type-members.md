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
ms.openlocfilehash: a9cd531100057fbad4884a20e6e7db6ef94e7956
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709219"
---
# <a name="names-of-type-members"></a><span data-ttu-id="cc8db-102">型のメンバーの名前</span><span class="sxs-lookup"><span data-stu-id="cc8db-102">Names of Type Members</span></span>
<span data-ttu-id="cc8db-103">型は次のメンバーで構成されています: メソッド、プロパティ、イベント、コンストラクター、フィールド。</span><span class="sxs-lookup"><span data-stu-id="cc8db-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="cc8db-104">次のセクションは、型のメンバーに名前を付けるためのガイドラインを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc8db-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="cc8db-105">メソッドの名前</span><span class="sxs-lookup"><span data-stu-id="cc8db-105">Names of Methods</span></span>  
 <span data-ttu-id="cc8db-106">メソッドはアクションを実行する手段であるため、デザインのガイドラインでは、メソッド名を動詞または動詞句にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc8db-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="cc8db-107">また、このガイドラインに従うと、名詞句または形容詞句であるプロパティ名および型名と、メソッド名を区別するためにも機能します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="cc8db-108">**✓ DO**: 動詞または動詞句のメソッド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```csharp  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="cc8db-109">プロパティの名前</span><span class="sxs-lookup"><span data-stu-id="cc8db-109">Names of Properties</span></span>  
 <span data-ttu-id="cc8db-110">他のメンバーとは異なり、プロパティには名詞句または形容詞の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc8db-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="cc8db-111">つまり、プロパティはデータを参照するため、プロパティの名前にはデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="cc8db-112">プロパティ名には、常に Pascal 形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="cc8db-113">**✓ DO**: 名詞、名詞句、または形容詞を使用してプロパティに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="cc8db-114">**X DO NOT**: 次の例のように、"Get" メソッドの名前と一致するプロパティを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cc8db-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="cc8db-115">通常、このパターンは、プロパティが実際にメソッドであることを示します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="cc8db-116">**✓ DO** name コレクションのプロパティには、単数形の語句と "List" または "collection" を使用する代わりに、コレクション内の項目を記述する複数形の語句を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>  
  
 <span data-ttu-id="cc8db-117">**✓ DO**: 肯定の語句 (`CantSeek` ではなく `CanSeek`) を使用して、ブール値のプロパティに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="cc8db-118">必要に応じて、ブール型プロパティの前に "Is"、"has"、または "has" を付けることもできますが、値を追加する場所のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-118">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>  
  
 <span data-ttu-id="cc8db-119">**✓ CONSIDER**: プロパティの型と同じ名前をプロパティに指定します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="cc8db-120">たとえば、次のプロパティは、`Color` という名前の列挙値を適切に取得および設定するため、プロパティは `Color` という名前になります。</span><span class="sxs-lookup"><span data-stu-id="cc8db-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```csharp  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="cc8db-121">イベントの名前</span><span class="sxs-lookup"><span data-stu-id="cc8db-121">Names of Events</span></span>  
 <span data-ttu-id="cc8db-122">イベントは常に、発生中のアクションまたは発生したアクションのいずれかのアクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="cc8db-123">そのため、メソッドと同様、イベントには動詞の名前が付けられ、イベントが発生した時刻を示すために動詞の時制が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="cc8db-124">**✓ DO**: 動詞または動詞句を使ってイベントに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="cc8db-125">例として、`Clicked`、`Painting`、`DroppedDown` などがあります。</span><span class="sxs-lookup"><span data-stu-id="cc8db-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="cc8db-126">**✓ DO**: 現在形や過去形を使って、イベント名に前と後の概念を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="cc8db-127">たとえば、ウィンドウを閉じる前に発生するクローズ イベントは `Closing` と呼ばれ、ウィンドウを閉じた後に発生するクローズ イベントは `Closed` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="cc8db-128">**X DO NOT**: プリイベントとポストイベントを示すために、"Before" や "After" の接頭辞または接尾辞を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cc8db-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="cc8db-129">前述のように、現在形と過去形を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="cc8db-130">**✓ DO**: 次の例に示すように、イベント ハンドラー (イベントの型として使用されるデリゲート) に "EventHandler" サフィックスを使って名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="cc8db-131">**✓ DO**: イベント ハンドラーに `sender` と `e` という名前の 2 つのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="cc8db-132">sender パラメーターは、イベントを発生させたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="cc8db-133">より具体的な型を使用できる場合も、通常、sender パラメーターの型は `object` になります。</span><span class="sxs-lookup"><span data-stu-id="cc8db-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="cc8db-134">**✓ DO**: "EventArgs" サフィックスを使ってイベントの引数クラスに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="cc8db-135">フィールドの名前</span><span class="sxs-lookup"><span data-stu-id="cc8db-135">Names of Fields</span></span>  
 <span data-ttu-id="cc8db-136">フィールドの名前付けのガイドラインは、静的パブリック フィールドと保護されたフィールドを対象とします。</span><span class="sxs-lookup"><span data-stu-id="cc8db-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="cc8db-137">内部フィールドとプライベート フィールドは、ガイドラインの対象ではありません。また、パブリック インスタンス フィールドや保護されたインスタンス フィールドは、「[メンバーのデザインのガイドライン](../../../docs/standard/design-guidelines/member.md)」で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="cc8db-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="cc8db-138">**✓ DO**: フィールド名に Pascal 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc8db-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="cc8db-139">**✓ DO**: 名詞、名詞句、または形容詞を使用してフィールドに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cc8db-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="cc8db-140">**X DO NOT**: フィールド名にプレフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cc8db-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="cc8db-141">たとえば、静的フィールドを示すために、"g_" や "s_" を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cc8db-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="cc8db-142">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="cc8db-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cc8db-143">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="cc8db-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8db-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc8db-144">See also</span></span>

- [<span data-ttu-id="cc8db-145">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cc8db-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="cc8db-146">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cc8db-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

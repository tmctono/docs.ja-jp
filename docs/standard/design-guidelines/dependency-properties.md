---
title: 依存関係プロパティ
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778769"
---
# <a name="dependency-properties"></a><span data-ttu-id="73c56-102">依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="73c56-102">Dependency Properties</span></span>
<span data-ttu-id="73c56-103">依存関係プロパティ (DP) は、たとえば (フィールド) の型の変数に格納することではなく、プロパティ ストアにその値を格納する標準プロパティです。</span><span class="sxs-lookup"><span data-stu-id="73c56-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="73c56-104">依存プロパティは、ある種のオブジェクトとそのコンテナーの間のリレーションシップを記述する「プロパティ」を表す、Get と Set の静的メソッドとしてモデル化された依存関係プロパティ (の位置など、`Button`上のオブジェクトを`Panel`コンテナーの場合)。</span><span class="sxs-lookup"><span data-stu-id="73c56-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="73c56-105">**✓ DO** プロパティ スタイル設定、トリガー、データ バインディング、アニメーション、動的なリソース、および継承などの WPF 機能をサポートする必要がある場合は、依存関係プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="73c56-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="73c56-106">依存関係プロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="73c56-106">Dependency Property Design</span></span>  
 <span data-ttu-id="73c56-107">**✓ DO** から継承<xref:System.Windows.DependencyObject>、または依存関係プロパティを実装する場合、そのサブタイプのいずれか。</span><span class="sxs-lookup"><span data-stu-id="73c56-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="73c56-108">型は、プロパティ ストアの非常に効率的な実装を提供し、自動的に WPF データ バインドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="73c56-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="73c56-109">**✓ DO** 正規の CLR プロパティとパブリックな静的読み取り専用フィールドのインスタンスを格納する提供<xref:System.Windows.DependencyProperty?displayProperty=nameWithType>各依存関係プロパティです。</span><span class="sxs-lookup"><span data-stu-id="73c56-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="73c56-110">**✓ DO** 依存関係プロパティを実装するインスタンス メソッドを呼び出すことによって<xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType>と<xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="73c56-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="73c56-111">**✓ DO** "Property"のプロパティの名前をアスタリスクの依存関係プロパティの静的フィールドの名前</span><span class="sxs-lookup"><span data-stu-id="73c56-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="73c56-112">**X DO NOT** コード内の依存関係プロパティの既定値を明示的に設定を代わりにメタデータの設定です。</span><span class="sxs-lookup"><span data-stu-id="73c56-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="73c56-113">プロパティの既定値を明示的に設定するをスタイル設定などのいくつかの暗黙的な方法で設定されているから、そのプロパティをできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="73c56-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="73c56-114">**X DO NOT** 静的フィールドにアクセスする標準コード以外のプロパティ アクセサーにコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="73c56-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="73c56-115">コードがしません実行をスタイル設定などの暗黙的な方法で、プロパティが設定されている場合のスタイルを設定するため、静的フィールドを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="73c56-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="73c56-116">**X DO NOT** 依存関係プロパティを使用してセキュリティで保護されたデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="73c56-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="73c56-117">プライベートでも依存関係プロパティは、パブリックにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73c56-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="73c56-118">接続されている依存関係プロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="73c56-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="73c56-119">依存関係プロパティが、前のセクションで説明されている宣言型の組み込みのプロパティを表しますたとえば、`Text`プロパティは、プロパティの`TextButton`、宣言します。</span><span class="sxs-lookup"><span data-stu-id="73c56-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="73c56-120">依存関係プロパティの特殊なは、接続されている依存関係プロパティです。</span><span class="sxs-lookup"><span data-stu-id="73c56-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="73c56-121">添付プロパティの典型的な例は、<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="73c56-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="73c56-122">プロパティ ボタン (いないグリッドの) 列の位置を表しますは"にアタッチされている"ボタンのグリッドで、グリッドで、ボタンが含まれている場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="73c56-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="73c56-123">添付プロパティの定義は、アクセサーが静的な Get と Set メソッドによって表されることを除いて、通常の依存関係プロパティのほとんどの場合ようになります。</span><span class="sxs-lookup"><span data-stu-id="73c56-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```csharp
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="73c56-124">依存関係プロパティの検証</span><span class="sxs-lookup"><span data-stu-id="73c56-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="73c56-125">プロパティは、多くの場合、検証と呼ばれるものを実装します。</span><span class="sxs-lookup"><span data-stu-id="73c56-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="73c56-126">プロパティの値を変更する試行したときに検証ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="73c56-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="73c56-127">残念なことに依存関係プロパティのアクセサーには、任意の検証コードを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="73c56-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="73c56-128">代わりに、依存関係プロパティの検証ロジックは、プロパティの登録時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c56-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="73c56-129">**X DO NOT** プロパティのアクセサーの依存関係プロパティの検証ロジックを配置します。</span><span class="sxs-lookup"><span data-stu-id="73c56-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="73c56-130">代わりに、検証コールバックを渡す`DependencyProperty.Register`メソッド。</span><span class="sxs-lookup"><span data-stu-id="73c56-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="73c56-131">依存関係プロパティの変更通知</span><span class="sxs-lookup"><span data-stu-id="73c56-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="73c56-132">**X DO NOT** 依存関係プロパティのアクセサーでの変更通知のロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="73c56-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="73c56-133">依存関係プロパティに変更通知のコールバックを指定して使用する必要があります組み込みの変更通知機能があり、<xref:System.Windows.PropertyMetadata>します。</span><span class="sxs-lookup"><span data-stu-id="73c56-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="73c56-134">依存関係プロパティの値の強制型変換</span><span class="sxs-lookup"><span data-stu-id="73c56-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="73c56-135">プロパティ ストアが実際に変更する前に、setter をプロパティ set アクセス操作子に渡された値が変更されたときにプロパティの強制型変換が行われます。</span><span class="sxs-lookup"><span data-stu-id="73c56-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="73c56-136">**X DO NOT** 依存関係プロパティのアクセサーに強制変換ロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="73c56-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="73c56-137">依存関係プロパティは、組み込みの強制型変換機能を持っているし、強制型変換のコールバックを指定することによって使用できます、`PropertyMetadata`します。</span><span class="sxs-lookup"><span data-stu-id="73c56-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="73c56-138">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="73c56-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="73c56-139">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="73c56-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c56-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="73c56-140">See also</span></span>

- [<span data-ttu-id="73c56-141">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="73c56-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="73c56-142">共通デザイン パターン</span><span class="sxs-lookup"><span data-stu-id="73c56-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)

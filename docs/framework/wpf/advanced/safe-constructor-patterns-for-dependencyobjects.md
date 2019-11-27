---
title: DependencyObject の安全なコンストラクター パターン
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 66e380a9428395c772d0dcfe45a995374774aec6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283825"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="a65e5-102">DependencyObject の安全なコンストラクター パターン</span><span class="sxs-lookup"><span data-stu-id="a65e5-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="a65e5-103">一般的に、コンストラクターは派生クラスのコンストラクターの基底の初期化として呼び出されることがあるため、クラスのコンストラクターでは、仮想メソッドやデリゲートなどのコールバックを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="a65e5-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="a65e5-104">対象オブジェクトの初期化が不完全な状態で、仮想メソッドに入ることがあります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="a65e5-105">ただし、プロパティ システム自体は、依存関係プロパティ システムの一部としてコールバックを呼び出し、内部的に公開します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="a65e5-106"><xref:System.Windows.DependencyObject.SetValue%2A> の呼び出しで依存関係プロパティの値を設定する操作と同様に、特定の場所にコールバックが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="a65e5-107">このため、使用する型が基底クラスとして使われる場合に、コンストラクター本体内に依存関係プロパティ値を設定すると問題が発生する可能性があり、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a65e5-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="a65e5-108">依存関係プロパティの状態と固有のコールバックに関する特定の問題を回避する <xref:System.Windows.DependencyObject> コンストラクターを実装するための特定のパターンがあります。これについては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a65e5-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a><span data-ttu-id="a65e5-109">プロパティ システムの仮想メソッド</span><span class="sxs-lookup"><span data-stu-id="a65e5-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="a65e5-110">依存関係プロパティ値 (<xref:System.Windows.ValidateValueCallback>、<xref:System.Windows.PropertyChangedCallback>、<xref:System.Windows.CoerceValueCallback>、<xref:System.Windows.DependencyObject.OnPropertyChanged%2A>) を設定する <xref:System.Windows.DependencyObject.SetValue%2A> 呼び出しの計算中に、次の仮想メソッドまたはコールバックが呼び出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="a65e5-111">これらの仮想メソッドまたはコールバックは、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のプロパティ システムと依存関係プロパティの汎用性を高めるうえで、それぞれ特定の目的を果たします。</span><span class="sxs-lookup"><span data-stu-id="a65e5-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="a65e5-112">これらの仮想メソッドを使用してプロパティ値の決定をカスタマイズする方法の詳細については、「[依存関係プロパティのコールバックと検証](dependency-property-callbacks-and-validation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a65e5-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="a65e5-113">FXCop ルールの強制とプロパティシステム純粋</span><span class="sxs-lookup"><span data-stu-id="a65e5-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="a65e5-114">ビルド プロセスの一部として Microsoft ツールの FXCop を使用している場合、基底コンストラクターを呼び出す特定の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] フレームワーク クラスを派生させるとき、派生クラスで独自の依存関係プロパティを実装するときに、FXCop の特定のルール違反が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="a65e5-115">ルール違反に該当する名前文字列は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a65e5-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="a65e5-116">このルールは、FXCop に設定されている既定のパブリック ルールの一部です。</span><span class="sxs-lookup"><span data-stu-id="a65e5-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="a65e5-117">このルールによって報告されるのは、依存関係プロパティ システムの仮想メソッドを最終的に呼び出す、依存関係プロパティ システム内のトレースです。</span><span class="sxs-lookup"><span data-stu-id="a65e5-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="a65e5-118">このルール違反は、このトピックで説明されている推奨コンストラクター パターンに従っている場合も発生し続ける可能性があるため、FXCop のルール セット構成でこのルールを無効にするか抑制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="a65e5-119">既存のクラスの使用ではなくクラスの派生が大半の原因</span><span class="sxs-lookup"><span data-stu-id="a65e5-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="a65e5-120">このルールによって報告される問題は、構築のシーケンスで仮想メソッドを呼び出すように実装したクラスが派生される場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="a65e5-121">クラスをシールする場合、クラスが派生されないとわかっている場合、クラスが派生されないように強制する場合は、ここで説明する内容や FXCop のルールによって起こる問題は該当しません。</span><span class="sxs-lookup"><span data-stu-id="a65e5-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="a65e5-122">ただし、テンプレートや拡張可能なコントロール ライブラリのセットを作成する場合などのように、基底クラスとしての使用を想定したクラスを作成する場合は、ここで説明されているコンストラクターの推奨パターンに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="a65e5-123">既定のコンストラクターにおいて、コールバックによって要求されるすべての値の初期化の必要性</span><span class="sxs-lookup"><span data-stu-id="a65e5-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="a65e5-124">クラスによって使用されるすべてのインスタンスメンバー (プロパティシステム純粋セクション内のリストからのコールバック) は、パラメーターなしのクラスコンストラクターで初期化する必要があります。これらの値の一部は、によって "real" 値によって入力されます。パラメーターなしのコンストラクターのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a65e5-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="a65e5-125">次のコード例 (および以降の例) は、この規則に違反する擬似 C# コードの例であり、問題を説明しています。</span><span class="sxs-lookup"><span data-stu-id="a65e5-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="a65e5-126">アプリケーションコードが `new MyClass(objectvalue)`を呼び出すと、パラメーターなしのコンストラクターと基底クラスのコンストラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a65e5-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="a65e5-127">次に `Property1 = object1`を設定します。これにより、所有している `MyClass` <xref:System.Windows.DependencyObject>の仮想メソッド `OnPropertyChanged` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a65e5-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="a65e5-128">オーバーライドでは、まだ初期化されていない `_myList` が参照されます。</span><span class="sxs-lookup"><span data-stu-id="a65e5-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="a65e5-129">これらの問題を回避する方法の 1 つは、コールバックが他の依存関係プロパティのみを使用し、それぞれの使用する依存関係プロパティが、登録済みのメタデータの一部として確立された既定値を持つようにすることです。</span><span class="sxs-lookup"><span data-stu-id="a65e5-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a><span data-ttu-id="a65e5-130">安全なコンストラクター パターン</span><span class="sxs-lookup"><span data-stu-id="a65e5-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="a65e5-131">クラスが基底クラスとして使用される場合に、不完全な初期化のリスクを回避するには、次のパターンに従ってください。</span><span class="sxs-lookup"><span data-stu-id="a65e5-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="a65e5-132">パラメーターなしのコンストラクターによる基本初期化の呼び出し</span><span class="sxs-lookup"><span data-stu-id="a65e5-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="a65e5-133">基底クラスの既定値を呼び出す次のコンストラクターを実装します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="a65e5-134">基底クラスのシグネチャと一致しない、既定以外の (簡易) コンストラクター</span><span class="sxs-lookup"><span data-stu-id="a65e5-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="a65e5-135">これらのコンストラクターがパラメーターを使用して初期化時に依存関係プロパティを設定する場合は、まず、初期化のために独自のクラスのパラメーターなしのコンストラクターを呼び出し、次にパラメーターを使用して依存関係プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="a65e5-136">これらは、クラスによって定義された依存関係プロパティか、基底クラスから継承された依存関係プロパティのいずれかですが、いずれの場合も次のパターンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a65e5-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="a65e5-137">基底クラスのシグネチャと一致する、既定以外の (簡易) コンストラクター</span><span class="sxs-lookup"><span data-stu-id="a65e5-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="a65e5-138">同じパラメーター化を使用して基底コンストラクターを呼び出す代わりに、独自のクラスのパラメーターなしのコンストラクターを再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="a65e5-139">基底初期化子を呼び出さないでください。代わりに `this()` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="a65e5-140">次に、渡されたパラメーターを関連プロパティを設定する値として使用し、元のコンストラクターの動作を複製します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="a65e5-141">特定のパラメーターを設定するプロパティを決定する場合は、参考として元の基底コンストラクターのドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a65e5-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="a65e5-142">すべてのシグネチャを一致させることが必要</span><span class="sxs-lookup"><span data-stu-id="a65e5-142">Must match all signatures</span></span>  
 <span data-ttu-id="a65e5-143">基本型に複数のシグネチャがある場合は、さらに設定する前に、使用可能なすべてのシグネチャを独自のコンストラクター実装と意図的に一致させる必要があります。属性.</span><span class="sxs-lookup"><span data-stu-id="a65e5-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="a65e5-144">SetValue による依存関係プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="a65e5-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="a65e5-145">プロパティ設定の便宜のためにラッパーを持たないプロパティを設定し、<xref:System.Windows.DependencyObject.SetValue%2A>で値を設定する場合にも、同じパターンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a65e5-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="a65e5-146">コンストラクターパラメーターをパススルーする <xref:System.Windows.DependencyObject.SetValue%2A> を呼び出すと、初期化のためにクラスのパラメーターなしのコンストラクターも呼び出される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a65e5-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65e5-147">参照</span><span class="sxs-lookup"><span data-stu-id="a65e5-147">See also</span></span>

- [<span data-ttu-id="a65e5-148">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="a65e5-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="a65e5-149">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="a65e5-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="a65e5-150">依存関係プロパティのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a65e5-150">Dependency Property Security</span></span>](dependency-property-security.md)

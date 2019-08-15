---
title: カスタム コントロールのアプリケーション設定
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040460"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="0ad95-102">カスタム コントロールのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="0ad95-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="0ad95-103">コントロールがサードパーティ製アプリケーションでホストされている場合は、カスタムコントロールにアプリケーション設定を保持する機能を提供するために、特定のタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>

 <span data-ttu-id="0ad95-104">アプリケーション設定機能に関するドキュメントのほとんどは、スタンドアロンアプリケーションを作成することを前提として記述されています。</span><span class="sxs-lookup"><span data-stu-id="0ad95-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="0ad95-105">ただし、他の開発者がアプリケーションでホストするコントロールを作成する場合は、コントロールが設定を適切に保持するために、追加の手順をいくつか実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>

## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="0ad95-106">アプリケーション設定とカスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="0ad95-106">Application Settings and Custom Controls</span></span>
 <span data-ttu-id="0ad95-107">コントロールで設定を適切に永続化するには、から<xref:System.Configuration.ApplicationSettingsBase>派生した独自の専用アプリケーション設定ラッパークラスを作成することによって、プロセスをカプセル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="0ad95-108">また、メインコントロールクラスはを実装<xref:System.Configuration.IPersistComponentSettings>する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="0ad95-109">インターフェイスには、と<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>という2つのメソッドと共に、いくつかのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ad95-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="0ad95-110">Visual Studio の**Windows フォームデザイナー**を使用してコントロールをフォームに追加すると、コントロールが<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>初期化されるときに Windows フォームが自動的に呼び出さ<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>れます。 `Dispose`コントロールのメソッドでを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>

 <span data-ttu-id="0ad95-111">さらに、カスタムコントロールのアプリケーション設定が Visual Studio などのデザイン時環境で適切に機能するためには、次のものを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>

1. <span data-ttu-id="0ad95-112">を1つのパラメーター <xref:System.ComponentModel.IComponent>として受け取るコンストラクターを持つカスタムアプリケーション設定クラス。</span><span class="sxs-lookup"><span data-stu-id="0ad95-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="0ad95-113">このクラスを使用すると、すべてのアプリケーション設定を保存して読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0ad95-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="0ad95-114">このクラスの新しいインスタンスを作成するときは、コンストラクターを使用してカスタムコントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>

2. <span data-ttu-id="0ad95-115">フォームの<xref:System.Windows.Forms.Form.Load>イベントハンドラーなど、コントロールを作成してフォームに配置した後に、このカスタム設定クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>

 <span data-ttu-id="0ad95-116">カスタム設定クラスを作成する方法について[は、「方法:アプリケーション設定](how-to-create-application-settings.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>

## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="0ad95-117">設定キーと共有設定</span><span class="sxs-lookup"><span data-stu-id="0ad95-117">Settings Keys and Shared Settings</span></span>
 <span data-ttu-id="0ad95-118">一部のコントロールは、同じフォーム内で複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ad95-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="0ad95-119">ほとんどの場合、これらのコントロールは個別の設定を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad95-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="0ad95-120"><xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> の<xref:System.Configuration.IPersistComponentSettings>プロパティを使用すると、フォーム上のコントロールの複数のバージョンを明確に区別するために機能する一意の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0ad95-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>

 <span data-ttu-id="0ad95-121">を実装<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>する最も簡単な方法は、 <xref:System.Windows.Forms.Control.Name%2A> <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>のコントロールのプロパティを使用することです。</span><span class="sxs-lookup"><span data-stu-id="0ad95-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="0ad95-122">コントロールの設定を読み込んだ場合、または保存した場合<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>は、の<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>値を<xref:System.Configuration.ApplicationSettingsBase>クラスのプロパティに渡します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="0ad95-123">アプリケーション設定は、ユーザーの設定を XML に永続化するときに、この一意のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="0ad95-124">次のコード例は、 `<userSettings>` `Text`プロパティの設定を保存するという名前`CustomControl1`のカスタムコントロールのインスタンスをセクションが検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ad95-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 <span data-ttu-id="0ad95-125">の<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>値が指定されていないコントロールのインスタンスは、同じ設定を共有します。</span><span class="sxs-lookup"><span data-stu-id="0ad95-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ad95-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ad95-126">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="0ad95-127">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0ad95-127">Application Settings Architecture</span></span>](application-settings-architecture.md)

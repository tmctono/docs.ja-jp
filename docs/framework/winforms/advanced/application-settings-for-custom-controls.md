---
title: カスタム コントロールのアプリケーション設定
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: 69a5caef8bab45503b9f34422de8c2ba2e7f01ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960902"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="91474-102">カスタム コントロールのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="91474-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="91474-103">コントロールがサード パーティ製のアプリケーションでホストされている場合は、アプリケーションの設定を保存する機能、カスタム コントロールを提供する特定のタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91474-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="91474-104">アプリケーション設定機能についてのドキュメントのほとんどは、スタンドアロン アプリケーションを作成することを前提として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="91474-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="91474-105">ただし場合は、アプリケーションで他の開発者をホストするコントロールを作成する必要がありますの設定を保持するコントロールのいくつかの追加手順を実行する適切です。</span><span class="sxs-lookup"><span data-stu-id="91474-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="91474-106">アプリケーションの設定とカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="91474-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="91474-107">その設定を正しく保持する、コントロールの設定ラッパー クラスから派生した独自の専用アプリケーションを作成して、プロセスをカプセルにする必要があります<xref:System.Configuration.ApplicationSettingsBase>します。</span><span class="sxs-lookup"><span data-stu-id="91474-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="91474-108">また、メインのコントロール クラスを実装する必要があります、<xref:System.Configuration.IPersistComponentSettings>します。</span><span class="sxs-lookup"><span data-stu-id="91474-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="91474-109">インターフェイスには、2 つのメソッドに加えていくつかのプロパティが含まれます。<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>と<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>します。</span><span class="sxs-lookup"><span data-stu-id="91474-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="91474-110">使用してフォームにコントロールを追加する場合、 **Windows フォーム デザイナー** Windows フォームを呼び出し、Visual Studio で<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>コントロールが初期化される場合に自動的に呼び出す必要があります<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>で自分で、 `Dispose`コントロールのメソッド。</span><span class="sxs-lookup"><span data-stu-id="91474-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="91474-111">さらに、Visual Studio などのデザイン時環境で適切に機能するカスタム コントロールのアプリケーション設定の順序で、次を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91474-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1. <span data-ttu-id="91474-112">受け取るコンス トラクターを持つカスタム アプリケーション設定クラスを<xref:System.ComponentModel.IComponent>パラメーターを 1 つ。</span><span class="sxs-lookup"><span data-stu-id="91474-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="91474-113">保存し、すべてのアプリケーションの設定を読み込むには、このクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="91474-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="91474-114">このクラスの新しいインスタンスを作成するときは、コンス トラクターを使用して、カスタム コントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="91474-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2. <span data-ttu-id="91474-115">コントロールを作成し、フォームのように、フォームに配置した後、このカスタム設定クラスを作成<xref:System.Windows.Forms.Form.Load>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="91474-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="91474-116">カスタム設定クラスを作成する方法の詳細については、次を参照してください。[方法。アプリケーション設定を作成する](how-to-create-application-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="91474-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="91474-117">設定キーと共有設定</span><span class="sxs-lookup"><span data-stu-id="91474-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="91474-118">一部のコントロールを同じフォーム内で複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="91474-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="91474-119">ほとんどの場合、これらのコントロールを各自の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="91474-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="91474-120"><xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>プロパティ<xref:System.Configuration.IPersistComponentSettings>フォーム上のコントロールの複数のバージョンを解消するために機能する一意の文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="91474-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="91474-121">実装する最も簡単な方法は、<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>を使用して、<xref:System.Windows.Forms.Control.Name%2A>のコントロールのプロパティ、<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>します。</span><span class="sxs-lookup"><span data-stu-id="91474-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="91474-122">値を渡すロードまたはコントロールの設定を保存するときに<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>に、<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>のプロパティ、<xref:System.Configuration.ApplicationSettingsBase>クラス。</span><span class="sxs-lookup"><span data-stu-id="91474-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="91474-123">アプリケーションの設定は、XML に、ユーザーの設定が引き続き発生するときに、この一意のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="91474-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="91474-124">次のコード例に示す方法、`<userSettings>`セクションという名前のカスタム コントロールのインスタンスを探すことがあります`CustomControl1`の設定を保存するその`Text`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="91474-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="91474-125">すべてのインスタンスの値を指定されていないコントロールの<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>同じ設定で共有されます。</span><span class="sxs-lookup"><span data-stu-id="91474-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91474-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="91474-126">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="91474-127">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="91474-127">Application Settings Architecture</span></span>](application-settings-architecture.md)

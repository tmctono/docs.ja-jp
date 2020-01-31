---
title: コントロールのアクセシビリティプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743421"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="244d9-102">ユーザ補助ガイドラインをサポートする Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="244d9-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="244d9-103">キーボードフォーカスの公開や画面要素の公開など、アクセシビリティに関する多くのガイドラインをサポートするために、Windows フォームの標準ツールボックスのコントロール。</span><span class="sxs-lookup"><span data-stu-id="244d9-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="244d9-104">ユーザー補助のための事前計画</span><span class="sxs-lookup"><span data-stu-id="244d9-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="244d9-105">コントロールのプロパティは、次の表に示すように、他のアクセシビリティガイドラインをサポートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="244d9-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="244d9-106">また、メニューを使用して、プログラムの機能へのアクセスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="244d9-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="244d9-107">Control プロパティ</span><span class="sxs-lookup"><span data-stu-id="244d9-107">Control Property</span></span>|<span data-ttu-id="244d9-108">アクセシビリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="244d9-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="244d9-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="244d9-109">AccessibleDescription</span></span>|<span data-ttu-id="244d9-110">説明は、スクリーンリーダーなどのユーザー補助機能に報告されます。</span><span class="sxs-lookup"><span data-stu-id="244d9-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="244d9-111">ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。</span><span class="sxs-lookup"><span data-stu-id="244d9-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="244d9-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="244d9-112">AccessibleName</span></span>|<span data-ttu-id="244d9-113">ユーザー補助機能に報告される名前。</span><span class="sxs-lookup"><span data-stu-id="244d9-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="244d9-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="244d9-114">AccessibleRole</span></span>|<span data-ttu-id="244d9-115">ユーザーインターフェイスでの要素の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="244d9-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="244d9-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="244d9-116">TabIndex</span></span>|<span data-ttu-id="244d9-117">フォームを使用して、実用的なナビゲーションパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="244d9-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="244d9-118">テキストボックスなどの固有のラベルを持たないコントロールは、関連付けられているラベルをタブオーダーの直前に配置することが重要です。</span><span class="sxs-lookup"><span data-stu-id="244d9-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="244d9-119">テキスト</span><span class="sxs-lookup"><span data-stu-id="244d9-119">Text</span></span>|<span data-ttu-id="244d9-120">アクセスキーを作成するには、"&" 文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="244d9-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="244d9-121">アクセスキーの使用は、ドキュメント化されたキーボードアクセスを機能に提供することの一部です。</span><span class="sxs-lookup"><span data-stu-id="244d9-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="244d9-122">フォント サイズ</span><span class="sxs-lookup"><span data-stu-id="244d9-122">Font Size</span></span>|<span data-ttu-id="244d9-123">フォントサイズを調整できない場合は、10ポイント以上に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="244d9-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="244d9-124">フォームのフォントサイズを設定すると、その後フォームに追加されたすべてのコントロールのサイズが同じになります。</span><span class="sxs-lookup"><span data-stu-id="244d9-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="244d9-125">前景色</span><span class="sxs-lookup"><span data-stu-id="244d9-125">Forecolor</span></span>|<span data-ttu-id="244d9-126">このプロパティが既定値に設定されている場合は、ユーザーの色の設定がフォームで使用されます。</span><span class="sxs-lookup"><span data-stu-id="244d9-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="244d9-127">背景色</span><span class="sxs-lookup"><span data-stu-id="244d9-127">Backcolor</span></span>|<span data-ttu-id="244d9-128">このプロパティが既定値に設定されている場合は、ユーザーの色の設定がフォームで使用されます。</span><span class="sxs-lookup"><span data-stu-id="244d9-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="244d9-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="244d9-129">BackgroundImage</span></span>|<span data-ttu-id="244d9-130">テキストを読みやすくするには、このプロパティを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="244d9-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="244d9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="244d9-131">See also</span></span>

- [<span data-ttu-id="244d9-132">チュートリアル: ユーザー補助対応の Windows ベースのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="244d9-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)

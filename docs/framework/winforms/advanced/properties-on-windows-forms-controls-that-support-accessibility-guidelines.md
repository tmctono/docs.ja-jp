---
title: ユーザ補助ガイドラインをサポートする Windows フォーム コントロールのプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b3f10fe472e449d39385facdbc716cba9b3f7382
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640496"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="4d327-102">ユーザ補助ガイドラインをサポートする Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="4d327-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="4d327-103">Windows フォームの標準的なツールボックス コントロールでは、キーボード フォーカスを公開することや、画面要素の公開など、アクセシビリティのガイドラインの多くをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4d327-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="4d327-104">アクセシビリティの計画を立てる</span><span class="sxs-lookup"><span data-stu-id="4d327-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="4d327-105">コントロールのプロパティは、次の表に示すように、その他のユーザー補助のガイドラインをサポートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d327-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="4d327-106">さらに、メニューを使用して、プログラムの機能にアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d327-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="4d327-107">コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="4d327-107">Control Property</span></span>|<span data-ttu-id="4d327-108">ユーザー補助機能に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4d327-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="4d327-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="4d327-109">AccessibleDescription</span></span>|<span data-ttu-id="4d327-110">説明は、スクリーン リーダーなどのユーザー補助機能に報告されます。</span><span class="sxs-lookup"><span data-stu-id="4d327-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="4d327-111">ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。</span><span class="sxs-lookup"><span data-stu-id="4d327-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="4d327-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="4d327-112">AccessibleName</span></span>|<span data-ttu-id="4d327-113">この名前は、ユーザー補助機能が報告されます。</span><span class="sxs-lookup"><span data-stu-id="4d327-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="4d327-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="4d327-114">AccessibleRole</span></span>|<span data-ttu-id="4d327-115">ユーザー インターフェイスの要素の使用方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4d327-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="4d327-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="4d327-116">TabIndex</span></span>|<span data-ttu-id="4d327-117">フォームで実用的な移動パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d327-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="4d327-118">コントロールがタブ オーダー内直後に、関連するラベルのテキスト ボックスなどの組み込みのラベルがない場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="4d327-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="4d327-119">テキスト</span><span class="sxs-lookup"><span data-stu-id="4d327-119">Text</span></span>|<span data-ttu-id="4d327-120">アクセス キーを作成するのにには、"&"の文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d327-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="4d327-121">アクセス キーの使用は、文書化されているキーボード アクセス機能を提供することの一部です。</span><span class="sxs-lookup"><span data-stu-id="4d327-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="4d327-122">フォント サイズ</span><span class="sxs-lookup"><span data-stu-id="4d327-122">Font Size</span></span>|<span data-ttu-id="4d327-123">フォント サイズが調整可能でない場合は、10 ポイント以上に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d327-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="4d327-124">フォームのフォント サイズを設定すると、後からフォームに追加されるすべてのコントロールが同じサイズになります。</span><span class="sxs-lookup"><span data-stu-id="4d327-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="4d327-125">前景色</span><span class="sxs-lookup"><span data-stu-id="4d327-125">Forecolor</span></span>|<span data-ttu-id="4d327-126">このプロパティが、既定値に設定されている場合、ユーザーの色の設定は、フォームで使用します。</span><span class="sxs-lookup"><span data-stu-id="4d327-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="4d327-127">背景色</span><span class="sxs-lookup"><span data-stu-id="4d327-127">Backcolor</span></span>|<span data-ttu-id="4d327-128">このプロパティが、既定値に設定されている場合、ユーザーの色の設定は、フォームで使用します。</span><span class="sxs-lookup"><span data-stu-id="4d327-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="4d327-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="4d327-129">BackgroundImage</span></span>|<span data-ttu-id="4d327-130">このプロパティは、テキストを読みやすくする場合は空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4d327-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d327-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d327-131">See also</span></span>

- [<span data-ttu-id="4d327-132">チュートリアル: ユーザー補助対応の Windows ベースのアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d327-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)

---
title: ワークフロー デザイン操作のカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715136"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="87229-102">ワークフロー デザイン操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="87229-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="87229-103">カスタムアクティビティを設計し、Windows ワークフローデザイナーを再ホストするシナリオは、.NET Framework 4 で大幅に簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="87229-103">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="87229-104">開発も配置も簡単になり、柔軟性も向上しました。</span><span class="sxs-lookup"><span data-stu-id="87229-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="87229-105">主要なインフラストラクチャの変更は、新しいアクティビティデザイナーのプログラミングモデルが Windows Presentation Foundation (WPF) に基づいて構築されることです。</span><span class="sxs-lookup"><span data-stu-id="87229-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="87229-106">これにより、アクティビティデザイナーを宣言によって定義し、他のアプリケーションのワークフローデザイナーを比較しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="87229-106">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="87229-107">再ホストするときに、カスタム式エディターを開発して、IntelliSense や簡略化された式ドメインをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="87229-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="87229-108">ワークフローサービスを使用すると、Windows Communication Foundation (WCF) との統合がシームレスになりました。</span><span class="sxs-lookup"><span data-stu-id="87229-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="87229-109">カスタム アクティビティ デザイナーおよびモデル アイテム ツリーを使用して、再ホストされたワークフロー デザイナーのデザイン時の操作を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="87229-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="87229-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="87229-110">In This Section</span></span>

 [<span data-ttu-id="87229-111">カスタム アクティビティ デザイナーおよびテンプレートの使用</span><span class="sxs-lookup"><span data-stu-id="87229-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="87229-112">新しいカスタム アクティビティ デザイナーおよびテンプレートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="87229-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="87229-113">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="87229-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="87229-114">Visual Studio の外部で Windows ワークフローデザイナーを再ホストする方法と、検証エラーを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="87229-114">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="87229-115">カスタム式エディターの使用</span><span class="sxs-lookup"><span data-stu-id="87229-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="87229-116">Visual Studio 2010 の外部で再ホストされたワークフローデザイナーで使用するカスタム式エディターを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="87229-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="87229-117">辞書／辞典／その他</span><span class="sxs-lookup"><span data-stu-id="87229-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="87229-118">参照</span><span class="sxs-lookup"><span data-stu-id="87229-118">See also</span></span>

- [<span data-ttu-id="87229-119">Windows Workflow Foundation の拡張</span><span class="sxs-lookup"><span data-stu-id="87229-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="87229-120">デザイナー</span><span class="sxs-lookup"><span data-stu-id="87229-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="87229-121">カスタム アクティビティ デザイナー</span><span class="sxs-lookup"><span data-stu-id="87229-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="87229-122">デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="87229-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)

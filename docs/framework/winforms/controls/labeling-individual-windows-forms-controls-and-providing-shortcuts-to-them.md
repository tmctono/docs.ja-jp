---
title: 各 Windows フォーム コントロールのラベル設定とショートカットの作成
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- shortcuts [Windows Forms], controls
- keyboard shortcuts [Windows Forms], controls
- Windows Forms controls, labels
ms.assetid: 6eaf868c-819f-4131-8f59-048e20c286f7
ms.openlocfilehash: 8d7ae8c807b8c5347a455b81c2c1a1b0897430c2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710603"
---
# <a name="labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them"></a><span data-ttu-id="19d43-102">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="19d43-102">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>
<span data-ttu-id="19d43-103">Windows フォームに追加されたコントロールには、ユーザー操作をさらに特殊化するために使用されるプロパティとメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="19d43-103">Controls added to Windows Forms have properties and methods that are used to further specialize the user experience.</span></span> <span data-ttu-id="19d43-104">ユーザーのニーズに合わせてユーザー インターフェイスをカスタマイズすることは、適切に設計された Windows アプリケーションにおいて非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="19d43-104">Customizing your user interface to suit the needs of the user is extremely important for well-designed Windows applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19d43-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="19d43-105">In This Section</span></span>  
 [<span data-ttu-id="19d43-106">方法: によって表示されるテキストを設定、Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="19d43-106">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 <span data-ttu-id="19d43-107">コントロールにテキスト ラベルを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19d43-107">Describes how to assign a text label to a control.</span></span>  
  
 [<span data-ttu-id="19d43-108">方法: によって表示されるイメージの設定を Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="19d43-108">How to: Set the Image Displayed by a Windows Forms Control</span></span>](how-to-set-the-image-displayed-by-a-windows-forms-control.md)  
 <span data-ttu-id="19d43-109">イメージを表示するためのコントロールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19d43-109">Explains how to configure a control to display images.</span></span>  
  
 [<span data-ttu-id="19d43-110">方法: Windows フォーム コントロールのアクセス キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="19d43-110">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)  
 <span data-ttu-id="19d43-111">定義済みのキーボード ショートカットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19d43-111">Gives information about creating predefined keyboard shortcuts.</span></span>  
  
 [<span data-ttu-id="19d43-112">Windows フォーム上のコントロールのユーザー補助情報の提供</span><span class="sxs-lookup"><span data-stu-id="19d43-112">Providing Accessibility Information for Controls on a Windows Form</span></span>](providing-accessibility-information-for-controls-on-a-windows-form.md)  
 <span data-ttu-id="19d43-113">コントロールでユーザー補助機能を使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19d43-113">Gives information about enabling your controls to work with accessibility aids.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="19d43-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="19d43-114">Related Sections</span></span>  
 [<span data-ttu-id="19d43-115">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="19d43-115">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="19d43-116">コントロールを使用して実行できる、その他の基本的な項目へのリンク。</span><span class="sxs-lookup"><span data-stu-id="19d43-116">Links to other basic things you can do with controls.</span></span>  
  
 <span data-ttu-id="19d43-117">参照してください[方法。Windows フォーム デザイナーを使用してコントロールのアクセス キーを作成](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md)、[方法。によって表示されるテキストを設定、Windows フォーム デザイナーを使用してコントロール](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md)、[方法。によって表示されるイメージの設定を Windows フォーム デザイナーを使用してコントロール](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="19d43-117">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>

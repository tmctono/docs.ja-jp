---
title: マルチ ドキュメント インターフェイス (MDI) アプリケーション
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956558"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="33bbb-102">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="33bbb-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="33bbb-103">マルチドキュメントインターフェイス (MDI) アプリケーションを使用すると、複数のドキュメントを同時に表示することができ、各ドキュメントは独自のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33bbb-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="33bbb-104">MDI アプリケーションには、多くの場合、ウィンドウまたはドキュメントを切り替えるためのサブメニューを含む [ウィンドウ] メニュー項目があります。</span><span class="sxs-lookup"><span data-stu-id="33bbb-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33bbb-105">Windows フォームの MDI フォームとシングルドキュメントインターフェイス (SDI) ウィンドウには、いくつかの動作の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="33bbb-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="33bbb-106">プロパティ`Opacity`は、MDI 子フォームの外観には影響しません。</span><span class="sxs-lookup"><span data-stu-id="33bbb-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="33bbb-107">また、メソッドは、MDI 子フォームの動作には影響しません。 <xref:System.Windows.Forms.Form.CenterToParent%2A></span><span class="sxs-lookup"><span data-stu-id="33bbb-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33bbb-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="33bbb-108">In This Section</span></span>  
 [<span data-ttu-id="33bbb-109">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="33bbb-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="33bbb-110">MDI アプリケーション内の複数のドキュメントのコンテナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33bbb-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="33bbb-111">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="33bbb-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="33bbb-112">MDI 親フォーム内で動作する1つまたは複数のウィンドウを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="33bbb-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="33bbb-113">方法: アクティブな MDI 子フォームを特定する</span><span class="sxs-lookup"><span data-stu-id="33bbb-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="33bbb-114">フォーカスのある子ウィンドウを確認し、その内容をクリップボードに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="33bbb-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="33bbb-115">方法: アクティブな MDI 子フォームにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="33bbb-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="33bbb-116">アクティブな子ウィンドウに情報を転送する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="33bbb-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="33bbb-117">方法: MDI 子フォームを配置する</span><span class="sxs-lookup"><span data-stu-id="33bbb-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="33bbb-118">MDI アプリケーションの子ウィンドウを並べて配置したり、整列したりするための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="33bbb-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>

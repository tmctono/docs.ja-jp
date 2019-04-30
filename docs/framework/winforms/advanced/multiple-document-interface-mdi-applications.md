---
title: マルチ ドキュメント インターフェイス (MDI) アプリケーション
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61952049"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="976cc-102">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="976cc-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="976cc-103">マルチ ドキュメント インターフェイス (MDI) アプリケーションでは、独自のウィンドウに表示される各ドキュメントに、同時に複数のドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="976cc-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="976cc-104">MDI アプリケーションには、多くの場合、ウィンドウやドキュメント間の切り替えのサブメニューのあるウィンドウのメニュー項目があります。</span><span class="sxs-lookup"><span data-stu-id="976cc-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="976cc-105">Windows フォームの MDI フォームと、シングル ドキュメント インターフェイス (SDI) ウィンドウをいくつかの動作違いがあります。</span><span class="sxs-lookup"><span data-stu-id="976cc-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="976cc-106">`Opacity`プロパティが MDI 子フォームの外観に影響しません。</span><span class="sxs-lookup"><span data-stu-id="976cc-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="976cc-107">さらに、<xref:System.Windows.Forms.Form.CenterToParent%2A>メソッドでは MDI 子フォームの動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="976cc-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="976cc-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="976cc-108">In This Section</span></span>  
 [<span data-ttu-id="976cc-109">方法: MDI 親フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="976cc-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="976cc-110">MDI アプリケーション内で複数のドキュメントのコンテナーを作成するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="976cc-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="976cc-111">方法: MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="976cc-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="976cc-112">MDI 親フォーム内で動作する 1 つまたは複数の windows を作成するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="976cc-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="976cc-113">方法: アクティブな MDI 子を決定します。</span><span class="sxs-lookup"><span data-stu-id="976cc-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="976cc-114">フォーカスを持つ子ウィンドウを確認するための手順を示します (とその内容をクリップボードに送信) します。</span><span class="sxs-lookup"><span data-stu-id="976cc-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="976cc-115">方法: アクティブな MDI 子ウィンドウにデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="976cc-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="976cc-116">アクティブな子ウィンドウに情報を転送するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="976cc-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="976cc-117">方法: MDI 子フォームを配置します。</span><span class="sxs-lookup"><span data-stu-id="976cc-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="976cc-118">並べて表示、重ねて表示したり、または MDI アプリケーションの子ウィンドウの配置の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="976cc-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>

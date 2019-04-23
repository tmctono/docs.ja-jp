---
title: メッセージ キュー (MSMQ) のインストール
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 64736f8f0a34a53658dd2838738a3d36b3891d2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305092"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="921ee-102">メッセージ キュー (MSMQ) のインストール</span><span class="sxs-lookup"><span data-stu-id="921ee-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="921ee-103">メッセージ キュー 4.0 およびメッセージ キュー 3.0 をインストールする方法を次の手順に示します。</span><span class="sxs-lookup"><span data-stu-id="921ee-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="921ee-104">メッセージ キュー 4.0 は、[!INCLUDE[wxp](../../../../includes/wxp-md.md)] および [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] では使用できません。</span><span class="sxs-lookup"><span data-stu-id="921ee-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="921ee-105">Windows Server 2008 または Windows Server 2008 R2 にメッセージ キュー 4.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="921ee-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="921ee-106">サーバー マネージャーで、**機能**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="921ee-107">右側のペインで**機能の概要**、 をクリックして**機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="921ee-108">結果ウィンドウで、展開**メッセージ キュー**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="921ee-109">展開**メッセージ キュー サービス**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="921ee-110">をクリックして**ディレクトリ サービス統合**(コンピューターの場合、ドメインに参加している)、そのクリックして**HTTP サポート**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="921ee-111">クリックして**次**、順にクリックします**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="921ee-112">Windows 7 または Windows Vista にメッセージ キュー 4.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="921ee-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="921ee-113">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="921ee-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="921ee-114">クリックして**プログラム**し、**プログラムと機能**、 をクリックして**Windows 機能の有効化オンとオフを**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="921ee-115">[Microsoft Message Queue (MSMQ) Server]、[Microsoft Message Queue (MSMQ) Server Core] の順に展開して、インストールする次のメッセージ キュー機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="921ee-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="921ee-116">[MSMQ Active Directory Domain Services Integration] (ドメインに参加するコンピューターの場合)</span><span class="sxs-lookup"><span data-stu-id="921ee-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="921ee-117">[MSMQ HTTP サポート]</span><span class="sxs-lookup"><span data-stu-id="921ee-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="921ee-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="921ee-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="921ee-119">コンピューターを再起動するメッセージが表示されたら、クリックして**OK**インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="921ee-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="921ee-120">Windows XP および Windows Server 2003 にメッセージ キュー 3.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="921ee-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="921ee-121">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="921ee-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="921ee-122">クリックして**プログラムの追加と削除** をクリックし、 **Windows コンポーネントの追加**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="921ee-123">メッセージ キューを選択し、クリックして**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="921ee-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="921ee-124">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] を実行している場合は、メッセージ キューにアクセスするアプリケーション サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="921ee-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="921ee-125">詳細ページで、[MSMQ HTTP サポート] オプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="921ee-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="921ee-126">をクリックして**OK**を詳細ページを終了し、をクリックし、 **[次へ]**。</span><span class="sxs-lookup"><span data-stu-id="921ee-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="921ee-127">インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="921ee-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="921ee-128">コンピューターを再起動するメッセージが表示されたら、クリックして**OK**インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="921ee-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921ee-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="921ee-129">See also</span></span>

- [<span data-ttu-id="921ee-130">セットアップ手順</span><span class="sxs-lookup"><span data-stu-id="921ee-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)

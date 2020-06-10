---
title: メッセージ キュー (MSMQ) のインストール
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 1bf79ed5dbcb9f2ace903260cc440e77df3aef09
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592295"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="fe7e5-102">メッセージ キュー (MSMQ) のインストール</span><span class="sxs-lookup"><span data-stu-id="fe7e5-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="fe7e5-103">メッセージ キュー 4.0 およびメッセージ キュー 3.0 をインストールする方法を次の手順に示します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe7e5-104">Windows XP および Windows Server 2003 では、メッセージキュー4.0 は使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-104">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="fe7e5-105">Windows Server 2008 または Windows Server 2008 R2 にメッセージ キュー 4.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="fe7e5-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="fe7e5-106">サーバーマネージャーで、[**機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="fe7e5-107">右側のウィンドウの [機能の**概要**] で、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="fe7e5-108">結果のウィンドウで、[**メッセージキュー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="fe7e5-109">[**メッセージキューサービス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="fe7e5-110">[**ディレクトリサービスの統合**] (ドメインに参加しているコンピューターの場合) をクリックし、[ **HTTP サポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="fe7e5-111">[**次へ**] をクリックし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="fe7e5-112">Windows 7 または Windows Vista にメッセージ キュー 4.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="fe7e5-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="fe7e5-113">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="fe7e5-114">[**プログラム**] をクリックし、[**プログラムと機能**] で [ **Windows の機能の有効化または無効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="fe7e5-115">[Microsoft Message Queue (MSMQ) Server]、[Microsoft Message Queue (MSMQ) Server Core] の順に展開して、インストールする次のメッセージ キュー機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="fe7e5-116">[MSMQ Active Directory Domain Services Integration] (ドメインに参加するコンピューターの場合)</span><span class="sxs-lookup"><span data-stu-id="fe7e5-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="fe7e5-117">[MSMQ HTTP サポート]</span><span class="sxs-lookup"><span data-stu-id="fe7e5-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="fe7e5-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="fe7e5-119">コンピューターの再起動を求めるメッセージが表示されたら、[ **OK** ] をクリックしてインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="fe7e5-120">Windows XP および Windows Server 2003 にメッセージ キュー 3.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="fe7e5-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="fe7e5-121">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="fe7e5-122">[**プログラムの追加と削除**] をクリックし、[ **Windows コンポーネントの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="fe7e5-123">[メッセージキュー] を選択し、[**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fe7e5-124">Windows Server 2003 を実行している場合は、[アプリケーションサーバー] を選択してメッセージキューにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-124">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="fe7e5-125">詳細ページで、[MSMQ HTTP サポート] オプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="fe7e5-126">[ **OK** ] をクリックして詳細ページを終了し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="fe7e5-127">インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="fe7e5-128">コンピューターの再起動を求めるメッセージが表示されたら、[ **OK** ] をクリックしてインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="fe7e5-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7e5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe7e5-129">See also</span></span>

- [<span data-ttu-id="fe7e5-130">セットアップ手順</span><span class="sxs-lookup"><span data-stu-id="fe7e5-130">Set-Up Instructions</span></span>](set-up-instructions.md)

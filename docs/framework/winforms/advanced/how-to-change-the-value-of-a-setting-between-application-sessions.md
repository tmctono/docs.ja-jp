---
title: '方法: アプリケーション セッション間での設定の値を変更します。'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714360"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="eb6e7-102">方法: アプリケーション セッション間での設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="eb6e7-103">アプリケーションをコンパイルおよび展開後に、アプリケーション セッション間での設定の値を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="eb6e7-104">たとえば、適切なデータベースの場所を指す接続文字列を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="eb6e7-105">アプリケーションをコンパイルおよび展開した後は、デザイン時ツールを使用できない、ために、ファイルに手動で設定値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="eb6e7-106">アプリケーション セッション間での設定の値を変更するには</span><span class="sxs-lookup"><span data-stu-id="eb6e7-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="eb6e7-107">Microsoft メモ帳またはいくつかその他のテキスト エディターまたは XML エディターを使用して、アプリケーションに関連する .config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="eb6e7-108">変更する設定のエントリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="eb6e7-109">次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="eb6e7-110">設定の新しい値を入力し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="eb6e7-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6e7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb6e7-111">See also</span></span>
- [<span data-ttu-id="eb6e7-112">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="eb6e7-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="eb6e7-113">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="eb6e7-113">Application Settings Overview</span></span>](application-settings-overview.md)

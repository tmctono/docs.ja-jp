---
title: システム情報
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732580"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="0c68c-102">システム情報と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="0c68c-102">System Information and Windows Forms</span></span>
<span data-ttu-id="0c68c-103">場合によっては、コードを決定するために、アプリケーションが実行されているコンピューターに関する情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c68c-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="0c68c-104">たとえば、特定のネットワークドメインに接続されている場合にのみ適用される関数があるとします。この場合、ドメインを特定し、ドメインが存在しない場合は関数を無効にする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="0c68c-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="0c68c-105">Windows フォームアプリケーションは、<xref:System.Windows.Forms.SystemInformation> クラスを使用して、実行時にコンピューターに関するさまざまなことを判断できます。</span><span class="sxs-lookup"><span data-stu-id="0c68c-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="0c68c-106">次の例は、<xref:System.Windows.Forms.SystemInformation> クラスを使用して <xref:System.Windows.Forms.SystemInformation.UserName%2A> と <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c68c-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 <span data-ttu-id="0c68c-107"><xref:System.Windows.Forms.SystemInformation> クラスのすべてのメンバーは読み取り専用です。ユーザーの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c68c-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="0c68c-108">クラスには100を超えるメンバーがあり、コンピューターに接続されているモニターの数 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) から Windows エクスプローラーのアイコンの間隔 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> と <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>) までのすべての情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="0c68c-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="0c68c-109"><xref:System.Windows.Forms.SystemInformation> クラスの便利なメンバーの中には、<xref:System.Windows.Forms.SystemInformation.ComputerName%2A>、<xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>、<xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>、<xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>などがあります。</span><span class="sxs-lookup"><span data-stu-id="0c68c-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c68c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c68c-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="0c68c-111">Windows フォームでの電源管理</span><span class="sxs-lookup"><span data-stu-id="0c68c-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)

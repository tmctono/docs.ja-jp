---
title: システム情報と Windows フォーム
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
ms.openlocfilehash: eeb469dbf4553634aa50d0a9ea17e9b2464defb4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934694"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="7ea22-102">システム情報と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="7ea22-102">System Information and Windows Forms</span></span>
<span data-ttu-id="7ea22-103">コードで決定するために、アプリケーションが実行されているコンピューターに関する情報を収集するために必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ea22-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="7ea22-104">たとえば、のみ、特定のネットワークのドメインに接続しているときに適用される関数がある可能性があります。ここでドメインを確認して、ドメインが存在しない場合、関数を無効にする方法する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ea22-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="7ea22-105">Windows フォーム アプリケーションを使用できる、<xref:System.Windows.Forms.SystemInformation>クラスを実行時にさまざまなコンピューターに関する考慮事項を確認します。</span><span class="sxs-lookup"><span data-stu-id="7ea22-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="7ea22-106">次の例を使用して、<xref:System.Windows.Forms.SystemInformation>を取得するクラス、<xref:System.Windows.Forms.SystemInformation.UserName%2A>と<xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="7ea22-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <span data-ttu-id="7ea22-107">すべてのメンバー、<xref:System.Windows.Forms.SystemInformation>クラスは読み取り専用はユーザーの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ea22-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="7ea22-108">コンピューターに接続されているモニターの数からすべての情報を返すクラスの 100 を超えるメンバーが (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) に Windows エクスプ ローラーのアイコンの間隔 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A>と<xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>)。</span><span class="sxs-lookup"><span data-stu-id="7ea22-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="7ea22-109">いくつかの便利なメンバーの<xref:System.Windows.Forms.SystemInformation>クラスが含まれて<xref:System.Windows.Forms.SystemInformation.ComputerName%2A>、 <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>、 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>、および<xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>します。</span><span class="sxs-lookup"><span data-stu-id="7ea22-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea22-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ea22-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="7ea22-111">Windows フォームでの電源管理</span><span class="sxs-lookup"><span data-stu-id="7ea22-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)

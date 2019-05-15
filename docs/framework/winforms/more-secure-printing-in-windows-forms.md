---
title: Windows フォームでのより安全な印刷
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: b0387a82f142fb32912dad1370d6ac0c784e8894
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592640"
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="6aca0-102">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="6aca0-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="6aca0-103">頻繁に、Windows フォーム アプリケーションには、印刷機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6aca0-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="6aca0-104">.NET Framework を使用して、<xref:System.Drawing.Printing.PrintingPermission>クラスからの印刷機能へのアクセス制御および関連付けられている<xref:System.Drawing.Printing.PrintingPermissionLevel>アクセスのレベルを示す列挙値。</span><span class="sxs-lookup"><span data-stu-id="6aca0-104">The .NET Framework uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="6aca0-105">既定では、ローカルのイントラネットとインターネット ゾーンに既定では、印刷が有効になりますただし、どちらのゾーン レベルのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="6aca0-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="6aca0-106">アプリケーションが印刷できるかどうか、ユーザーの介入が必要ですか、印刷は、アプリケーションに付与されるアクセス許可の値に依存できません。</span><span class="sxs-lookup"><span data-stu-id="6aca0-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="6aca0-107">ローカル イントラネット ゾーンでは既定では、<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>とイントラネット ゾーンのアクセスを受け取る<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>アクセスします。</span><span class="sxs-lookup"><span data-stu-id="6aca0-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="6aca0-108">次の表では、各印刷アクセス許可レベルで使用可能な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6aca0-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="6aca0-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="6aca0-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="6aca0-110">説明</span><span class="sxs-lookup"><span data-stu-id="6aca0-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="6aca0-111">インストールされているすべてのプリンターへのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6aca0-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="6aca0-112">既定のプリンターにプログラムによる印刷と制限の厳しい印刷ダイアログ ボックスを使用した安全な印刷できます。</span><span class="sxs-lookup"><span data-stu-id="6aca0-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="6aca0-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6aca0-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="6aca0-114">制限されたダイアログ ボックスからのみ印刷機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6aca0-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="6aca0-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6aca0-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="6aca0-116">プリンターにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6aca0-116">Prevents access to printers.</span></span> <span data-ttu-id="6aca0-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6aca0-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6aca0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aca0-118">See also</span></span>

- [<span data-ttu-id="6aca0-119">Windows フォームにおけるファイルおよびデータへのより安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="6aca0-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="6aca0-120">Windows フォームのセキュリティに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6aca0-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="6aca0-121">Windows フォームのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="6aca0-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="6aca0-122">Windows フォームのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6aca0-122">Windows Forms Security</span></span>](windows-forms-security.md)

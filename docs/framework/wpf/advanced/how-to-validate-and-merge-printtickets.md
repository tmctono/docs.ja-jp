---
title: '方法: PrintTickets を検証およびマージする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 9e5242c07179501e6b39840a36f8dd6364d65b84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918344"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="76422-102">方法: PrintTickets を検証およびマージする</span><span class="sxs-lookup"><span data-stu-id="76422-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="76422-103">[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [印刷スキーマ](https://go.microsoft.com/fwlink/?LinkId=186397)には、柔軟で拡張<xref:System.Printing.PrintCapabilities>可能<xref:System.Printing.PrintTicket>な要素と要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76422-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="76422-104">前者は印刷デバイスの機能を示しています。後者では、デバイスが特定の順序のドキュメント、個々のドキュメント、または個々のページに対してこれらの機能をどのように使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="76422-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="76422-105">印刷をサポートするアプリケーションの一般的なタスクシーケンスは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76422-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="76422-106">プリンターの機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="76422-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="76422-107">これらの<xref:System.Printing.PrintTicket>機能を使用するようにを構成します。</span><span class="sxs-lookup"><span data-stu-id="76422-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="76422-108">を<xref:System.Printing.PrintTicket>検証します。</span><span class="sxs-lookup"><span data-stu-id="76422-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="76422-109">この記事では、これを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="76422-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76422-110">例</span><span class="sxs-lookup"><span data-stu-id="76422-110">Example</span></span>  
 <span data-ttu-id="76422-111">次の簡単な例では、プリンターが両面印刷をサポートしているかどうかのみを知りたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="76422-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="76422-112">主な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76422-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="76422-113">メソッド<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>を<xref:System.Printing.PrintCapabilities>使用してオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="76422-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="76422-114">必要な機能があるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="76422-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="76422-115">次の例では、 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> <xref:System.Printing.PrintCapabilities>オブジェクトのプロパティをテストして、用紙の両面に印刷機能があり、シートの横に "ページめくり" が付いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76422-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="76422-116">は<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>コレクションであるため、の`Contains` <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="76422-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="76422-117">この手順は、厳密には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="76422-117">This step is not strictly necessary.</span></span> <span data-ttu-id="76422-118">以下で使用する<xref:System.Printing.PrintTicket> メソッドは、内の各要求をプリンターの機能と照合してチェックします。<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A></span><span class="sxs-lookup"><span data-stu-id="76422-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="76422-119">要求された機能がプリンターでサポートされていない場合、プリンタードライバーは、 <xref:System.Printing.PrintTicket>メソッドによって返されたの代替要求を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="76422-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="76422-120">プリンターが両面印刷をサポートしている場合は<xref:System.Printing.PrintTicket> 、このサンプルコードによって、二重化を求めるが作成されます。</span><span class="sxs-lookup"><span data-stu-id="76422-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="76422-121">ただし、アプリケーションでは、 <xref:System.Printing.PrintTicket>要素で使用可能なすべてのプリンター設定が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="76422-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="76422-122">これは、プログラマとプログラム時間の両方で無駄になります。</span><span class="sxs-lookup"><span data-stu-id="76422-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="76422-123">代わりに、この<xref:System.Printing.PrintTicket>コードでは二重の要求のみを設定し、これを既存の、完全に構成<xref:System.Printing.PrintTicket>および検証された (この場合は<xref:System.Printing.PrintTicket>ユーザーの既定値) とマージします。</span><span class="sxs-lookup"><span data-stu-id="76422-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="76422-124">したがって、このサンプルで<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>は、メソッドを呼び出して、ユーザー <xref:System.Printing.PrintTicket>の既定値<xref:System.Printing.PrintTicket>を使用して、新しいを最小限にします。</span><span class="sxs-lookup"><span data-stu-id="76422-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="76422-125">これにより<xref:System.Printing.ValidationResult> 、新しい<xref:System.Printing.PrintTicket>をプロパティの1つとして含むが返されます。</span><span class="sxs-lookup"><span data-stu-id="76422-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="76422-126">このサンプルでは、新しい<xref:System.Printing.PrintTicket>要求が二重になっていることをテストします。</span><span class="sxs-lookup"><span data-stu-id="76422-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="76422-127">存在する場合は、サンプルによってユーザーの既定の印刷チケットが新しく作成されます。</span><span class="sxs-lookup"><span data-stu-id="76422-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="76422-128">上記の手順 2 `false`. を省略した場合、プリンターでは、長辺に沿った両面印刷がサポートされていないと、テストの結果としてが発生します。</span><span class="sxs-lookup"><span data-stu-id="76422-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="76422-129">(上記のメモを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="76422-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="76422-130">最後の重要な手順は、 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue.Commit%2A>メソッドを使用して、 <xref:System.Printing.PrintQueue>のプロパティに対する変更をコミットすることです。</span><span class="sxs-lookup"><span data-stu-id="76422-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="76422-131">この例を簡単にテストできるように、この例の残りの部分を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="76422-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="76422-132">プロジェクトと名前空間を作成し、この記事の両方のコードスニペットを名前空間ブロックに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="76422-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="76422-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="76422-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="76422-134">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="76422-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="76422-135">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="76422-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="76422-136">スキーマの印刷</span><span class="sxs-lookup"><span data-stu-id="76422-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)

---
title: '方法: クリップボードからデータを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: e8f77a4fd1047598d51c2e0932d9c1309a305a86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295511"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="c1aa2-102">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="c1aa2-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="c1aa2-103"><xref:System.Windows.Forms.Clipboard>クラスは、Windows オペレーティング システムのクリップボード機能との対話に使用できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="c1aa2-104">多くのアプリケーションは、クリップボードをデータの一時的なリポジトリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="c1aa2-105">たとえば、ワード プロセッサでは、切り取りと貼り付けの操作中に、クリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="c1aa2-106">クリップボードも別に 1 つのアプリケーションから情報を転送するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="c1aa2-107">一部のアプリケーションでは、データを使用できる可能性のあるその他のアプリケーションの数を増やすには、複数の形式でのクリップボードにデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="c1aa2-108">クリップボードの形式は、形式を識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="c1aa2-109">特定の形式を使用するアプリケーションでは、クリップボードに関連付けられているデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="c1aa2-110"><xref:System.Windows.Forms.DataFormats>クラスは、使用する定義済みの形式名を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="c1aa2-111">独自の形式名を使用してもまたはその形式として、オブジェクトの型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="c1aa2-112">クリップボードにデータを追加する方法の詳細については、次を参照してください。[方法。クリップボードにデータを追加](how-to-add-data-to-the-clipboard.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="c1aa2-113">特定の形式でデータがクリップボードに含まれるかどうかを判断するのいずれかの操作を使用して、 `Contains`*形式*メソッドまたは<xref:System.Windows.Forms.Clipboard.GetData%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="c1aa2-114">クリップボードからデータを取得するには、いずれかを使用、 `Get`*形式*メソッドまたは<xref:System.Windows.Forms.Clipboard.GetData%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="c1aa2-115">これらのメソッドは、の新しい[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-115">These methods are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
 <span data-ttu-id="c1aa2-116">バージョンを使用して、クリップボードからデータにアクセスするよりも前[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]を使用して、<xref:System.Windows.Forms.Clipboard.GetDataObject%2A>メソッドの返されたメソッドを呼び出すと<xref:System.Windows.Forms.IDataObject>します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-116">To access data from the Clipboard by using versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="c1aa2-117">たとえば、呼び出す特定の形式が返されるオブジェクトで使用できるかどうかを確認するのには<xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1aa2-118">すべての Windows ベースのアプリケーションでは、システムのクリップボードを共有します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="c1aa2-119">そのため、別のアプリケーションに切り替えた場合に、内容は変更される可能性が。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="c1aa2-120"><xref:System.Windows.Forms.Clipboard>クラスは、シングル スレッド アパートメント (STA) モードに設定するスレッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="c1aa2-121">このクラスを使用することを確認、`Main`メソッドが設定されて、<xref:System.STAThreadAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="c1aa2-122">1 つの一般的な形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="c1aa2-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="c1aa2-123">使用して、 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>、 <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>、 <xref:System.Windows.Forms.Clipboard.GetImage%2A>、または<xref:System.Windows.Forms.Clipboard.GetText%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="c1aa2-124">必要に応じて、使用、対応する`Contains`*形式*データが特定の形式で使用できるかどうかを判断するには、最初のメソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="c1aa2-125">これらのメソッドはでのみ使用可能な[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-125">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="c1aa2-126">カスタム形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="c1aa2-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="c1aa2-127">使用して、<xref:System.Windows.Forms.Clipboard.GetData%2A>メソッドをカスタム形式名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="c1aa2-128">このメソッドでのみ使用[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-128">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="c1aa2-129">定義済みの形式名を使用することも、<xref:System.Windows.Forms.Clipboard.SetData%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="c1aa2-130">詳細については、「 <xref:System.Windows.Forms.DataFormats> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="c1aa2-131">複数の形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="c1aa2-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="c1aa2-132"><xref:System.Windows.Forms.Clipboard.GetDataObject%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="c1aa2-133">このメソッドを使用して、バージョンでクリップボードからデータを取得する必要がありますよりも前[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-133">You must use this method to retrieve data from the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="c1aa2-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1aa2-134">See also</span></span>

- [<span data-ttu-id="c1aa2-135">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="c1aa2-135">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="c1aa2-136">方法: データをクリップボードに追加します。</span><span class="sxs-lookup"><span data-stu-id="c1aa2-136">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)

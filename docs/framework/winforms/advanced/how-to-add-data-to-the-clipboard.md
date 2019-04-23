---
title: '方法: クリップボードにデータを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 03d3a0c6026761fcdbc45472f2bbb7ac593f4394
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325684"
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="885c7-102">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="885c7-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="885c7-103"><xref:System.Windows.Forms.Clipboard>クラスは、Windows オペレーティング システムのクリップボード機能との対話に使用できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="885c7-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="885c7-104">多くのアプリケーションは、クリップボードをデータの一時的なリポジトリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="885c7-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="885c7-105">たとえば、ワード プロセッサでは、切り取りと貼り付けの操作中に、クリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="885c7-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="885c7-106">クリップボードも別に 1 つのアプリケーションからデータを転送するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="885c7-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="885c7-107">クリップボードにデータを追加すると、その形式を使用する場合、その他のアプリケーションは、データを認識できるように、データ形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="885c7-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="885c7-108">データを使用できる可能性のあるその他のアプリケーションの数を増やすに複数の異なる形式でクリップボードにデータを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="885c7-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="885c7-109">クリップボードの形式は、その形式を使用するアプリケーションに関連付けられているデータを取得できるようにする形式を識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="885c7-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="885c7-110"><xref:System.Windows.Forms.DataFormats>クラスは、使用する定義済みの形式名を提供します。</span><span class="sxs-lookup"><span data-stu-id="885c7-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="885c7-111">独自の形式名を使用してもまたはその形式として、オブジェクトの型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="885c7-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="885c7-112">1 つまたは複数の形式でクリップボードにデータを追加するには、使用、<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="885c7-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="885c7-113">この方法では、任意のオブジェクトを渡すことができますが、複数の形式でデータを追加する必要があります最初に、データを追加する別のオブジェクトが複数の形式を扱うために設計されています。</span><span class="sxs-lookup"><span data-stu-id="885c7-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="885c7-114">データを追加する、通常、<xref:System.Windows.Forms.DataObject>を実装する任意の型を使用することができますが、<xref:System.Windows.Forms.IDataObject>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="885c7-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="885c7-115">[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]クリップボードの基本的な作業を容易に設計された新しいメソッドを使用して、クリップボードに直接データを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="885c7-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="885c7-116">テキストなどの 1 つの一般的な形式でデータを操作する場合は、これらのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="885c7-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="885c7-117">すべての Windows ベースのアプリケーションでは、クリップボードを共有します。</span><span class="sxs-lookup"><span data-stu-id="885c7-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="885c7-118">そのため、別のアプリケーションに切り替えた場合に、内容は変更される可能性が。</span><span class="sxs-lookup"><span data-stu-id="885c7-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="885c7-119"><xref:System.Windows.Forms.Clipboard>クラスは、シングル スレッド アパートメント (STA) モードに設定するスレッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="885c7-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="885c7-120">このクラスを使用することを確認、`Main`メソッドが設定されて、<xref:System.STAThreadAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="885c7-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="885c7-121">オブジェクトはクリップボードに配置するためにシリアル化可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="885c7-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="885c7-122">型をシリアル化可能にするには、マークで、<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="885c7-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="885c7-123">クリップボードのメソッドにシリアル化できないオブジェクトを渡すと、例外をスローせず、メソッドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="885c7-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="885c7-124">シリアル化の詳細については、「<xref:System.Runtime.Serialization>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="885c7-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="885c7-125">1 つの一般的な形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="885c7-125">To add data to the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="885c7-126">使用して、 <xref:System.Windows.Forms.Clipboard.SetAudio%2A>、 <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>、 <xref:System.Windows.Forms.Clipboard.SetImage%2A>、または<xref:System.Windows.Forms.Clipboard.SetText%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="885c7-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="885c7-127">これらのメソッドはでのみ使用可能な[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="885c7-127">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="885c7-128">カスタム形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="885c7-128">To add data to the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="885c7-129">使用して、<xref:System.Windows.Forms.Clipboard.SetData%2A>メソッドをカスタム形式名を使用します。</span><span class="sxs-lookup"><span data-stu-id="885c7-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="885c7-130">このメソッドでのみ使用[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="885c7-130">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="885c7-131">定義済みの形式名を使用することも、<xref:System.Windows.Forms.Clipboard.SetData%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="885c7-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="885c7-132">詳細については、「 <xref:System.Windows.Forms.DataFormats> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="885c7-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="885c7-133">複数の形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="885c7-133">To add data to the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="885c7-134">使用して、<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>メソッドを渡します、<xref:System.Windows.Forms.DataObject>データを格納しています。</span><span class="sxs-lookup"><span data-stu-id="885c7-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="885c7-135">このメソッドを使用してデータのバージョンでクリップボードを追加する必要がありますよりも前[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="885c7-135">You must use this method to add data to the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="885c7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="885c7-136">See also</span></span>

- [<span data-ttu-id="885c7-137">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="885c7-137">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="885c7-138">方法: クリップボードからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="885c7-138">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)

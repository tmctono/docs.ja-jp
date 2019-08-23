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
ms.openlocfilehash: 88c2f2d872ae32b2cb3f0df13ce4816400695385
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963782"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="52fe9-102">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="52fe9-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="52fe9-103">クラス<xref:System.Windows.Forms.Clipboard>には、Windows オペレーティングシステムのクリップボード機能との対話に使用できるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="52fe9-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="52fe9-104">多くのアプリケーションでは、データの一時リポジトリとしてクリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="52fe9-105">たとえば、ワードプロセッサは、切り取りと貼り付けの操作中にクリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="52fe9-106">クリップボードは、アプリケーション間で情報を転送する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="52fe9-107">アプリケーションによっては、データを複数の形式でクリップボードに格納することで、データを使用する可能性のある他のアプリケーションの数を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="52fe9-108">クリップボード形式は、形式を識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="52fe9-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="52fe9-109">識別された形式を使用するアプリケーションは、クリップボードにある関連データを取得できます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="52fe9-110">クラス<xref:System.Windows.Forms.DataFormats>には、使用するための定義済みの形式名が用意されています。</span><span class="sxs-lookup"><span data-stu-id="52fe9-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="52fe9-111">独自の形式名を使用することも、形式としてオブジェクトの型を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="52fe9-112">クリップボードにデータを追加する方法につい[ては、「」を参照してください。クリップボード](how-to-add-data-to-the-clipboard.md)にデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="52fe9-113">クリップボードに特定の形式のデータが含まれているかどうか`Contains`を確認するに<xref:System.Windows.Forms.Clipboard.GetData%2A>は、いずれかの*書式*メソッドまたはメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="52fe9-114">クリップボードからデータを取得するには、いずれ`Get`かの*書式*メソッド<xref:System.Windows.Forms.Clipboard.GetData%2A>またはメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="52fe9-115">これらのメソッドは .NET Framework 2.0 で新しく追加されたものです。</span><span class="sxs-lookup"><span data-stu-id="52fe9-115">These methods are new in .NET Framework 2.0.</span></span>  
  
 <span data-ttu-id="52fe9-116">.NET Framework 2.0 より前のバージョンを使用してクリップボードのデータにアクセス<xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType>するには、メソッドを使用し<xref:System.Windows.Forms.IDataObject>て、返されるのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-116">To access data from the Clipboard by using versions earlier than .NET Framework 2.0, use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="52fe9-117">たとえば、返されたオブジェクトで特定の形式が使用可能かどうかを判断<xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>するには、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52fe9-118">すべての Windows ベースのアプリケーションは、システムクリップボードを共有します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="52fe9-119">そのため、別のアプリケーションに切り替えると、コンテンツが変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52fe9-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="52fe9-120">クラス<xref:System.Windows.Forms.Clipboard>は、シングルスレッドアパートメント (STA) モードに設定されているスレッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="52fe9-121">このクラスを使用するには、 `Main`メソッドが<xref:System.STAThreadAttribute>属性でマークされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="52fe9-122">1つの共通形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="52fe9-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="52fe9-123">、、、または<xref:System.Windows.Forms.Clipboard.GetText%2A>メソッドを使用します。 <xref:System.Windows.Forms.Clipboard.GetImage%2A> <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A> <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A></span><span class="sxs-lookup"><span data-stu-id="52fe9-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="52fe9-124">必要に応じて、 `Contains`対応する*書式*メソッドを使用して、データを特定の形式で使用できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="52fe9-125">これらのメソッドは、.NET Framework 2.0 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-125">These methods are available only in .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="52fe9-126">カスタム形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="52fe9-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="52fe9-127">カスタム書式<xref:System.Windows.Forms.Clipboard.GetData%2A>名を使用して、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="52fe9-128">このメソッドは、.NET Framework 2.0 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-128">This method is available only in .NET Framework 2.0.</span></span>  
  
     <span data-ttu-id="52fe9-129">メソッドでは、 <xref:System.Windows.Forms.Clipboard.SetData%2A>定義済みの書式名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52fe9-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="52fe9-130">詳細については、「 <xref:System.Windows.Forms.DataFormats> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52fe9-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="52fe9-131">複数の形式でクリップボードからデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="52fe9-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="52fe9-132"><xref:System.Windows.Forms.Clipboard.GetDataObject%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="52fe9-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="52fe9-133">.NET Framework 2.0 より前のバージョンのクリップボードからデータを取得するには、このメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52fe9-133">You must use this method to retrieve data from the Clipboard on versions earlier than .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="52fe9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="52fe9-134">See also</span></span>

- [<span data-ttu-id="52fe9-135">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="52fe9-135">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="52fe9-136">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="52fe9-136">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)

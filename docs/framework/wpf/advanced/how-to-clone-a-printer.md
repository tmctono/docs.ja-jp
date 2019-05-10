---
title: '方法: プリンターを複製する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: e6af8d6410c4e383990bdaa27f97cc698be71719
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649199"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="e1966-102">方法: プリンターを複製する</span><span class="sxs-lookup"><span data-stu-id="e1966-102">How to: Clone a Printer</span></span>
<span data-ttu-id="e1966-103">ほとんどの企業が、ある時点で、購入、同じモデルの複数のプリンターです。</span><span class="sxs-lookup"><span data-stu-id="e1966-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="e1966-104">通常、これらがすべてインストールと実質的に同じ構成設定。</span><span class="sxs-lookup"><span data-stu-id="e1966-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="e1966-105">かかることがあります各プリンターをインストールしてエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e1966-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="e1966-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType>名前空間と<xref:System.Printing.PrintServer.InstallPrintQueue%2A>Microsoft .NET Framework で公開されているクラスでは、すぐに既存の印刷キューから任意の数の複製がその他の印刷キューをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="e1966-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1966-107">例</span><span class="sxs-lookup"><span data-stu-id="e1966-107">Example</span></span>  
 <span data-ttu-id="e1966-108">次の例では、2 番目の印刷キューは既存の印刷キューから複製されました。</span><span class="sxs-lookup"><span data-stu-id="e1966-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="e1966-109">最初の 2 つ目とは異なる、名前、場所、ポート、および共有状態でのみです。</span><span class="sxs-lookup"><span data-stu-id="e1966-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="e1966-110">これを行うための主要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1966-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="e1966-111">作成、<xref:System.Printing.PrintQueue>クローンを作成することは、既存のプリンターのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e1966-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="e1966-112">作成、<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>から、<xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>の<xref:System.Printing.PrintQueue>します。</span><span class="sxs-lookup"><span data-stu-id="e1966-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="e1966-113"><xref:System.Collections.DictionaryEntry.Value%2A>このディクショナリ内の各エントリのプロパティから派生した型の 1 つのオブジェクトである<xref:System.Printing.IndexedProperties.PrintProperty>します。</span><span class="sxs-lookup"><span data-stu-id="e1966-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="e1966-114">このディクショナリ内のエントリの値を設定する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="e1966-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="e1966-115">使用して、辞書の**削除**と<xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A>エントリを削除し、目的の値に再び追加する方法。</span><span class="sxs-lookup"><span data-stu-id="e1966-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="e1966-116">使用して、辞書の<xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="e1966-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="e1966-117">次の例では、両方の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1966-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="e1966-118">作成、<xref:System.Printing.IndexedProperties.PrintBooleanProperty>オブジェクトし、設定、 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 「とき」にし、その<xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A>に`true`。</span><span class="sxs-lookup"><span data-stu-id="e1966-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="e1966-119">使用して、<xref:System.Printing.IndexedProperties.PrintBooleanProperty>オブジェクトの値を<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>の「とき」のエントリ。</span><span class="sxs-lookup"><span data-stu-id="e1966-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="e1966-120">作成、<xref:System.Printing.IndexedProperties.PrintStringProperty>オブジェクトし、設定、 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "ShareName"にし、その<xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>に適切な<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="e1966-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="e1966-121">使用して、<xref:System.Printing.IndexedProperties.PrintStringProperty>オブジェクトの値を<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>の"ShareName"エントリ。</span><span class="sxs-lookup"><span data-stu-id="e1966-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="e1966-122">別の作成<xref:System.Printing.IndexedProperties.PrintStringProperty>オブジェクトし、設定、 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 「場所」にし、その<xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>に適切な<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="e1966-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="e1966-123">もう 1 つを使用して、<xref:System.Printing.IndexedProperties.PrintStringProperty>オブジェクトの値を<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>の「場所」のエントリ。</span><span class="sxs-lookup"><span data-stu-id="e1966-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="e1966-124">配列を作成する<xref:System.String>秒。</span><span class="sxs-lookup"><span data-stu-id="e1966-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="e1966-125">各項目は、サーバー上のポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="e1966-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="e1966-126">使用<xref:System.Printing.PrintServer.InstallPrintQueue%2A>を新しい値で、新しいプリンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e1966-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="e1966-127">例を次にします。</span><span class="sxs-lookup"><span data-stu-id="e1966-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="e1966-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1966-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="e1966-129">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="e1966-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="e1966-130">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="e1966-130">Printing Overview</span></span>](printing-overview.md)

---
title: '方法: インク データにカスタム データを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640867"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="62fba-102">方法: インク データにカスタム データを追加する</span><span class="sxs-lookup"><span data-stu-id="62fba-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="62fba-103">インクが Ink Serialized Format (ISF) として保存されるときに、保存されるインクにカスタム データを追加できます。</span><span class="sxs-lookup"><span data-stu-id="62fba-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="62fba-104">カスタム データは、<xref:System.Windows.Ink.DrawingAttributes>、<xref:System.Windows.Ink.StrokeCollection>、または <xref:System.Windows.Ink.Stroke> に保存できます。</span><span class="sxs-lookup"><span data-stu-id="62fba-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="62fba-105">カスタム データは 3 つのオブジェクトに保存できるため、データを保存する最適な場所を決めることができます。</span><span class="sxs-lookup"><span data-stu-id="62fba-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="62fba-106">これら 3 つのクラスすべてで同様のメソッドを使用し、カスタム データの格納とアクセスが行われます。</span><span class="sxs-lookup"><span data-stu-id="62fba-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="62fba-107">カスタム データとして保存できるのは、次の種類のみとなります。</span><span class="sxs-lookup"><span data-stu-id="62fba-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="62fba-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="62fba-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="62fba-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="62fba-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="62fba-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="62fba-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="62fba-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="62fba-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="62fba-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="62fba-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="62fba-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="62fba-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="62fba-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="62fba-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="62fba-121">例</span><span class="sxs-lookup"><span data-stu-id="62fba-121">Example</span></span>  
 <span data-ttu-id="62fba-122">次の例は、<xref:System.Windows.Ink.StrokeCollection> に対してカスタム データの追加および取得を行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="62fba-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="62fba-123">次の例では、<xref:System.Windows.Controls.InkCanvas> と 2 つのボタンを表示するアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="62fba-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="62fba-124">ボタン `switchAuthor` により、2 人の別々の作成者が 2 つのペンを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="62fba-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="62fba-125">ボタン `changePenColors` により、<xref:System.Windows.Controls.InkCanvas> 上の各ストロークの色が作成者に応じて変更されます。</span><span class="sxs-lookup"><span data-stu-id="62fba-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="62fba-126">このアプリケーションでは、2 つの <xref:System.Windows.Ink.DrawingAttributes> オブジェクトが定義され、<xref:System.Windows.Ink.Stroke> を描画した作成者を示すカスタム プロパティがそれぞれに追加されます。</span><span class="sxs-lookup"><span data-stu-id="62fba-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="62fba-127">ユーザーが `changePenColors` をクリックすると、アプリケーションによって、ストロークの外観がカスタム プロパティの値に従って変更されます。</span><span class="sxs-lookup"><span data-stu-id="62fba-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]

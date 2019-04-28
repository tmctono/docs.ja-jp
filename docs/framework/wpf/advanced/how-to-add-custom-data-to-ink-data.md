---
title: '方法: インク データにカスタム データを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: c524e30943a21426e2e5e8fe6ae009999924fead
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777053"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="4b0fa-102">方法: インク データにカスタム データを追加する</span><span class="sxs-lookup"><span data-stu-id="4b0fa-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="4b0fa-103">カスタム データは、インクはインクがシリアル化された形式 (ISF) として保存するときに保存されるインクを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="4b0fa-104">カスタム データを保存することができます、 <xref:System.Windows.Ink.DrawingAttributes>、 <xref:System.Windows.Ink.StrokeCollection>、または<xref:System.Windows.Ink.Stroke>します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4b0fa-105">次の 3 つのオブジェクトに対するカスタム データを保存することを使用するデータを保存する最適な場所を決定できます。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="4b0fa-106">次の 3 つのすべてのクラスは、カスタム データを格納し、アクセスのようなメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="4b0fa-107">カスタム データとしては、次の種類のみを保存できます。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="4b0fa-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="4b0fa-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="4b0fa-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="4b0fa-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="4b0fa-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="4b0fa-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="4b0fa-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="4b0fa-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="4b0fa-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="4b0fa-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="4b0fa-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="4b0fa-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="4b0fa-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="4b0fa-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b0fa-121">例</span><span class="sxs-lookup"><span data-stu-id="4b0fa-121">Example</span></span>  
 <span data-ttu-id="4b0fa-122">次の例では、追加し、カスタム データを取得する方法、<xref:System.Windows.Ink.StrokeCollection>します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="4b0fa-123">次の例を表示するアプリケーションの作成、<xref:System.Windows.Controls.InkCanvas>と 2 つのボタン。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="4b0fa-124">ボタン、 `switchAuthor`、2 人の作成者によって使用される 2 つのペンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="4b0fa-125">ボタン`changePenColors`で各ストロークの色を変更、<xref:System.Windows.Controls.InkCanvas>作成者に従ってします。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="4b0fa-126">2 つのアプリケーション定義<xref:System.Windows.Ink.DrawingAttributes>オブジェクトし、著者の描画を示す 1 つずつにカスタム プロパティを追加、<xref:System.Windows.Ink.Stroke>します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4b0fa-127">ユーザーがクリックすると`changePenColors`アプリケーションがカスタム プロパティの値に従ってストロークの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="4b0fa-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]

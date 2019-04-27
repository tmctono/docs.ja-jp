---
title: '方法: GridViewRowPresenter を使用してデータを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910456"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="bff03-102">方法: GridViewRowPresenter を使用してデータを表示する</span><span class="sxs-lookup"><span data-stu-id="bff03-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="bff03-103">この例は、使用する方法を示します、<xref:System.Windows.Controls.GridViewRowPresenter>と<xref:System.Windows.Controls.GridViewHeaderRowPresenter>列にデータを表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bff03-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bff03-104">例</span><span class="sxs-lookup"><span data-stu-id="bff03-104">Example</span></span>  
 <span data-ttu-id="bff03-105">次の例は、指定する方法を示します、<xref:System.Windows.Controls.GridViewColumnCollection>を表示する、<xref:System.DateTime.DayOfWeek%2A>と<xref:System.DateTime.Year%2A>の<xref:System.DateTime>オブジェクトを使用して<xref:System.Windows.Controls.GridViewRowPresenter>と<xref:System.Windows.Controls.GridViewHeaderRowPresenter>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bff03-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="bff03-106">また、<xref:System.Windows.Style>の<xref:System.Windows.Controls.GridViewColumn.Header%2A>の<xref:System.Windows.Controls.GridViewColumn>します。</span><span class="sxs-lookup"><span data-stu-id="bff03-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="bff03-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="bff03-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="bff03-108">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="bff03-108">GridView Overview</span></span>](gridview-overview.md)

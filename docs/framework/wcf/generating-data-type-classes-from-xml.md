---
title: XML からのデータ型クラスの生成
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c1b5dfda8aa5370dbc202ab90c75ab5677970467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929572"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="c8e0f-102">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="c8e0f-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="c8e0f-103">には、XML からデータ型クラスを生成するための新しい機能があります。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-103">includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="c8e0f-104">このトピックでは、.NET ブログ RSS フィードのデータ型を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="c8e0f-105">フィードから .NET ブログの RSS XML を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="c8e0f-106">Internet Explorer に移動します。、 [.NET ブログの RSS フィード](https://devblogs.microsoft.com/dotnet/feed/)します。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="c8e0f-107">ページを右クリックして**ソースの表示**します。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="c8e0f-108">キーを押してフィードのテキストをコピー **Ctrl + A**すべてのテキストを選択して**Ctrl + C**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="c8e0f-109">データ型の作成</span><span class="sxs-lookup"><span data-stu-id="c8e0f-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="c8e0f-110">プロキシが使用されるコード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="c8e0f-111">このファイルは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] プロジェクトの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2. <span data-ttu-id="c8e0f-112">既存のクラスの外部にあるファイルの場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="c8e0f-113">選択**編集**、**ペースト**、 **XML をクラスとして貼り付ける**します。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="c8e0f-114">クラスと呼ばれる`link`、 `rss`、 `rssChannel`、 `rssChannelImage`、`rssChannelItem`と`rssChannelItemGuid`RSS フィード内の要素にアクセスするために必要なメンバーで作成されます。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="c8e0f-115">生成されたクラスの使用</span><span class="sxs-lookup"><span data-stu-id="c8e0f-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="c8e0f-116">クラスが生成されると、他のクラスのコードなどで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="c8e0f-117">次のコード例では、`rssChannelImage` クラスの新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="c8e0f-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```

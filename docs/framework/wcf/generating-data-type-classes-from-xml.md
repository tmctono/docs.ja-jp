---
title: XML からのデータ型クラスの生成
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a6666f1ba23dd563bd7a005d458cd7fe8253c3af
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679087"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="8accb-102">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="8accb-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="8accb-103">には、XML からデータ型クラスを生成するための新しい機能があります。</span><span class="sxs-lookup"><span data-stu-id="8accb-103">includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="8accb-104">このトピックでは、.NET ブログ RSS フィードのデータ型を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8accb-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="8accb-105">フィードから .NET ブログの RSS XML を取得します。</span><span class="sxs-lookup"><span data-stu-id="8accb-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="8accb-106">Internet Explorer に移動します。、 [.NET ブログの RSS フィード](https://devblogs.microsoft.com/dotnet/feed/)します。</span><span class="sxs-lookup"><span data-stu-id="8accb-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="8accb-107">ページを右クリックして**ソースの表示**します。</span><span class="sxs-lookup"><span data-stu-id="8accb-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="8accb-108">キーを押してフィードのテキストをコピー **Ctrl + A**すべてのテキストを選択して**Ctrl + C**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8accb-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="8accb-109">データ型の作成</span><span class="sxs-lookup"><span data-stu-id="8accb-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="8accb-110">プロキシが使用されるコード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8accb-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="8accb-111">このファイルは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] プロジェクトの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8accb-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="8accb-112">既存のクラスの外部にあるファイルの場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="8accb-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="8accb-113">選択**編集**、**ペースト**、 **XML をクラスとして貼り付ける**します。</span><span class="sxs-lookup"><span data-stu-id="8accb-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="8accb-114">クラスと呼ばれる`link`、 `rss`、 `rssChannel`、 `rssChannelImage`、`rssChannelItem`と`rssChannelItemGuid`RSS フィード内の要素にアクセスするために必要なメンバーで作成されます。</span><span class="sxs-lookup"><span data-stu-id="8accb-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="8accb-115">生成されたクラスの使用</span><span class="sxs-lookup"><span data-stu-id="8accb-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="8accb-116">クラスが生成されると、他のクラスのコードなどで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8accb-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="8accb-117">次のコード例では、`rssChannelImage` クラスの新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="8accb-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```

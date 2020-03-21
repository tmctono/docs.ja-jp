---
title: XML からのデータ型クラスの生成
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184130"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="cdd0e-102">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="cdd0e-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="cdd0e-103">.NET Framework 4.5 には、XML からデータ型クラスを生成する新しい機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="cdd0e-104">このトピックでは、.NET ブログ RSS フィードのデータ型を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="cdd0e-105">.NET ブログ RSS フィードからの XML の取得</span><span class="sxs-lookup"><span data-stu-id="cdd0e-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="cdd0e-106">インターネット エクスプローラで[、.NET ブログ RSS フィード](https://devblogs.microsoft.com/dotnet/feed/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="cdd0e-107">ページを右クリックし、[**ソースの表示 ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="cdd0e-108">**Ctrl キーを押しながら A キー**を押してすべてのテキストを選択し **、Ctrl + C キーを押**してコピーしてフィードのテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="cdd0e-109">データ型の作成</span><span class="sxs-lookup"><span data-stu-id="cdd0e-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="cdd0e-110">プロキシが使用されるコード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="cdd0e-111">このファイルは.NET Framework 4.5 プロジェクトの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="cdd0e-112">既存のクラスの外部にあるファイルの場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="cdd0e-113">[**編集]、[\*\*\*\*形式の貼り付け\*\*\*\*]、[XML をクラスとして貼り付け] を選択**します。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="cdd0e-114">、 `link`、 `rss` `rssChannel`、`rssChannelImage``rssChannelItem`と`rssChannelItemGuid`呼ばれるクラスは、RSS フィード内の要素にアクセスするために必要なメンバーを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="cdd0e-115">生成されたクラスの使用</span><span class="sxs-lookup"><span data-stu-id="cdd0e-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="cdd0e-116">クラスが生成されると、他のクラスのコードなどで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="cdd0e-117">次のコード例では、`rssChannelImage` クラスの新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="cdd0e-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```

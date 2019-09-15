---
title: XML からのデータ型クラスの生成
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: bf5596211e78842153b7406273626a7fa3c3aeea
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990287"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="91bdd-102">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="91bdd-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="91bdd-103">.NET Framework 4.5 には、XML からデータ型クラスを生成するための新しい機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91bdd-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="91bdd-104">このトピックでは、.NET ブログ RSS フィードのデータ型を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91bdd-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="91bdd-105">.NET ブログの RSS フィードから XML を取得する</span><span class="sxs-lookup"><span data-stu-id="91bdd-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="91bdd-106">Internet Explorer で、 [.Net ブログの RSS フィード](https://devblogs.microsoft.com/dotnet/feed/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="91bdd-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="91bdd-107">ページを右クリックし、 **[ソースの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91bdd-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="91bdd-108">Ctrl キーを押し**ながら A**キーを押してすべてのテキストを選択し、 **ctrl + C**キーを押してコピーすることで、フィードのテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="91bdd-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="91bdd-109">データ型の作成</span><span class="sxs-lookup"><span data-stu-id="91bdd-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="91bdd-110">プロキシが使用されるコード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="91bdd-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="91bdd-111">このファイルは、.NET Framework 4.5 プロジェクトの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bdd-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="91bdd-112">既存のクラスの外部にあるファイルの場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="91bdd-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="91bdd-113">**[編集]** 、 **[特殊な貼り付け]** 、 **[XML をクラスとして貼り付ける]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91bdd-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="91bdd-114">`link` `rss` 、、`rssChannelImage`、 、`rssChannelItem`およびと`rssChannelItemGuid`いうクラスは、RSS フィード内の要素にアクセスするために必要なメンバーと共に作成されます。 `rssChannel`</span><span class="sxs-lookup"><span data-stu-id="91bdd-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="91bdd-115">生成されたクラスの使用</span><span class="sxs-lookup"><span data-stu-id="91bdd-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="91bdd-116">クラスが生成されると、他のクラスのコードなどで使用できます。</span><span class="sxs-lookup"><span data-stu-id="91bdd-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="91bdd-117">次のコード例では、`rssChannelImage` クラスの新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="91bdd-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```

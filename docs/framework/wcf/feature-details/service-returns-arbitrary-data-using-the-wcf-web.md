---
title: '方法 : WCF Web HTTP プログラミング モデルを使用して任意のデータを返すサービスを作成する'
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: 41d9f0e53401bcd6b57b04a38e76af5ddb9fb4cc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976101"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="e6fe6-102">方法 : WCF Web HTTP プログラミング モデルを使用して任意のデータを返すサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="e6fe6-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="e6fe6-103">開発者は、データがサービス操作から返される流れを完全に制御する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="e6fe6-104">これは、サービス操作が WCF でサポートされていない形式でデータを返す必要がある場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-104">This is the case when a service operation must return data in a format not supported by WCF.</span></span> <span data-ttu-id="e6fe6-105">このトピックでは、WCF WEB HTTP プログラミングモデルを使用してこのようなサービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-105">This topic discusses using the WCF WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="e6fe6-106">ストリームを返す操作を 1 つ持つサービスを例に取ります。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="e6fe6-107">サービス コントラクトを実装するには</span><span class="sxs-lookup"><span data-stu-id="e6fe6-107">To implement the service contract</span></span>  
  
1. <span data-ttu-id="e6fe6-108">サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-108">Define the service contract.</span></span> <span data-ttu-id="e6fe6-109">コントラクトは `IImageServer` と呼ばれ、`GetImage` を返す <xref:System.IO.Stream> というメソッドが入っています。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="e6fe6-110">メソッドは <xref:System.IO.Stream>を返すため、WCF は、操作がサービス操作から返されたバイトを完全に制御し、返されるデータに書式設定を適用しないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-110">Because the method returns a <xref:System.IO.Stream>, WCF assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2. <span data-ttu-id="e6fe6-111">サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-111">Implement the service contract.</span></span> <span data-ttu-id="e6fe6-112">コントラクトには 1 つの操作 (`GetImage`) しかありません。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="e6fe6-113">このメソッドはビットマップを生成して、それを <xref:System.IO.MemoryStream> に .jpg 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="e6fe6-114">操作はそのストリームを呼び出し元に戻します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-114">The operation then returns that stream to the caller.</span></span>  
  
    ```csharp
    public class Service : IImageServer
    {
        public Stream GetImage(int width, int height)
        {
            Bitmap bitmap = new Bitmap(width, height);
            for (int i = 0; i < bitmap.Width; i++)
            {
                for (int j = 0; j < bitmap.Height; j++)
                {
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);
                }
            }
            MemoryStream ms = new MemoryStream();
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);
            ms.Position = 0;
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";
            return ms;
        }
    }
    ```  
  
     <span data-ttu-id="e6fe6-115">コードの最後から 2 番目の行にある `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";` に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="e6fe6-116">これにより、コンテンツタイプのヘッダーが `"image/jpeg"`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="e6fe6-117">この例では .jpg ファイルを戻す方法を示していますが、必要に応じて、任意の種類のデータを任意の形式で戻すように変更できます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="e6fe6-118">操作はデータを生成または取得してそれをストリームに書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="e6fe6-119">サービスをホストするには</span><span class="sxs-lookup"><span data-stu-id="e6fe6-119">To host the service</span></span>  
  
1. <span data-ttu-id="e6fe6-120">コンソール アプリケーションを作成し、サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-120">Create a console application to host the service.</span></span>  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2. <span data-ttu-id="e6fe6-121">変数を作成し、`Main` メソッド内のサービスに使用するベース アドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="e6fe6-122">サービス クラスとベース アドレスを指定するサービスの <xref:System.ServiceModel.ServiceHost> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="e6fe6-123"><xref:System.ServiceModel.WebHttpBinding> と <xref:System.ServiceModel.Description.WebHttpBehavior> を使用して、エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="e6fe6-124">サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-124">Open the service host.</span></span>  
  
    ```csharp  
    host.Open();  
    ```  
  
6. <span data-ttu-id="e6fe6-125">サービスを終了するためにユーザーが Enter キーを押すのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="e6fe6-126">Internet Explorer を使用して生のサービスを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="e6fe6-126">To call the raw service using Internet Explorer</span></span>  
  
1. <span data-ttu-id="e6fe6-127">サービスを実行します。サービスからの次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2. <span data-ttu-id="e6fe6-128">Internet Explorer を開き「`http://localhost:8000/Service/GetImage?width=50&height=40`」と入力します。黄色い長方形とその中心を通る青い斜線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6fe6-129">例</span><span class="sxs-lookup"><span data-stu-id="e6fe6-129">Example</span></span>  
 <span data-ttu-id="e6fe6-130">この例で使用されているコードの全容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-130">The following is a complete listing of the code for this topic.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e6fe6-131">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e6fe6-131">Compiling the Code</span></span>  
  
- <span data-ttu-id="e6fe6-132">コード例のコンパイル時には、System.ServiceModel.dll と System.ServiceModel.Web.dll を参照します。</span><span class="sxs-lookup"><span data-stu-id="e6fe6-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6fe6-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6fe6-133">See also</span></span>

- [<span data-ttu-id="e6fe6-134">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="e6fe6-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)

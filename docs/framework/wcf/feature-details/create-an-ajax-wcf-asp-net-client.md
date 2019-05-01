---
title: Visual Studio で、AJAX 対応 WCF サービスと ASP.NET クライアントを作成します。
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 06fa3a9d0151f3b4b865c421f9960854ef471377
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807886"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="7325f-102">方法: サービスにアクセスする、AJAX 対応 WCF サービスと ASP.NET クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7325f-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="7325f-103">このトピックでは、Visual Studio を使用して、AJAX 対応の Windows Communication Foundation (WCF) サービスと、サービスにアクセスする ASP.NET クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7325f-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="7325f-104">ASP.NET Web アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="7325f-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="7325f-105">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="7325f-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="7325f-106">**ファイル**メニューの **新規** > **プロジェクト**</span><span class="sxs-lookup"><span data-stu-id="7325f-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="7325f-107">**新しいプロジェクト**ダイアログ ボックスで、展開、**インストール済み** > **Visual c#** > **Web**カテゴリ、し、選択**ASP.NET Web アプリケーション (.NET Framework)** します。</span><span class="sxs-lookup"><span data-stu-id="7325f-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="7325f-108">プロジェクトに名前を**SandwichServices**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="7325f-109">**新しい ASP.NET Web アプリケーション**ダイアログ ボックスで、**空**選び**OK**。</span><span class="sxs-lookup"><span data-stu-id="7325f-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Visual Studio で ASP.NET web アプリの種類のダイアログ](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="7325f-111">Web フォームを追加します。</span><span class="sxs-lookup"><span data-stu-id="7325f-111">Add a web form</span></span>

1. <span data-ttu-id="7325f-112">SandwichServices プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="7325f-113">**新しい項目の追加**ダイアログ ボックスで、展開、**インストール済み** > **Visual c#** > **Web**カテゴリ、し、選択、 **Web フォーム**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="7325f-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="7325f-114">既定の名前 (**WebForm1**)、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="7325f-115">*WebForm1.aspx*で開きます**ソース**ビュー。</span><span class="sxs-lookup"><span data-stu-id="7325f-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="7325f-116">内で次のマークアップを追加、 **\<本文 >** タグ。</span><span class="sxs-lookup"><span data-stu-id="7325f-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="7325f-117">AJAX 対応 WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7325f-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="7325f-118">SandwichServices プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="7325f-119">**新しい項目の追加**ダイアログ ボックスで、展開、**インストール済み** > **Visual c#** > **Web**カテゴリ、し、選択、 **(AJAX 対応) WCF サービス**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="7325f-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Visual Studio での WCF サービス (AJAX 対応) の項目テンプレート](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="7325f-121">サービスの名前を付けます**CostService**選び**追加**。</span><span class="sxs-lookup"><span data-stu-id="7325f-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="7325f-122">*CostService.svc.cs*エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="7325f-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="7325f-123">サービスの操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="7325f-123">Implement the operation in the service.</span></span> <span data-ttu-id="7325f-124">サンドイッチの量のコストを計算する CostService クラスには、次のメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="7325f-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="7325f-125">サービスにアクセスするクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="7325f-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="7325f-126">開く、 *WebForm1.aspx*選択ファイルを開き、**デザイン**ビュー。</span><span class="sxs-lookup"><span data-stu-id="7325f-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="7325f-127">**ビュー**メニューの **ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="7325f-128">展開、 **AJAX Extensions**ノードやドラッグ アンド ドロップ、 **ScriptManager**フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="7325f-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="7325f-129">戻り、**ソース**間に次のコードを追加、表示、  **\<ScriptManager >** WCF サービスへのパスを指定するタグ。</span><span class="sxs-lookup"><span data-stu-id="7325f-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="7325f-130">Javascript 関数のコードを追加`Calculate()`します。</span><span class="sxs-lookup"><span data-stu-id="7325f-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="7325f-131">次のコードを配置、**ヘッド**web フォームのセクション。</span><span class="sxs-lookup"><span data-stu-id="7325f-131">Place the following code in the **head** section of the web form:</span></span>

    ```html
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="7325f-132">このコードの 3 つのサンドイッチの価格を計算する CostService メソッドを呼び出すしと呼ばれる範囲内に結果を表示**しくみが**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="7325f-133">プログラムを実行する</span><span class="sxs-lookup"><span data-stu-id="7325f-133">Run the program</span></span>

<span data-ttu-id="7325f-134">確認します*WebForm1.aspx*にフォーカスがあり、キーを押します**開始**web クライアントを起動するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7325f-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="7325f-135">ボタンが緑色の三角形とような**IIS Express (Microsoft Edge)** します。</span><span class="sxs-lookup"><span data-stu-id="7325f-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="7325f-136">または、キーを押して**F5**します。</span><span class="sxs-lookup"><span data-stu-id="7325f-136">Or, you can press **F5**.</span></span> <span data-ttu-id="7325f-137">をクリックして、 **3 sandwiches の価格**ある「3.75」想定される出力を生成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7325f-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="7325f-138">コード例</span><span class="sxs-lookup"><span data-stu-id="7325f-138">Example code</span></span>

<span data-ttu-id="7325f-139">完全なコードを次に、 *CostService.svc.cs*ファイル。</span><span class="sxs-lookup"><span data-stu-id="7325f-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="7325f-140">すべての内容を次に、 *WebForm1.aspx*ページ。</span><span class="sxs-lookup"><span data-stu-id="7325f-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```

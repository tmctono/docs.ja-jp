---
title: 発行者名レジストリの検証パッケージのダウンロード
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 5684844f1db33b075df099b3026d9d0c1061199f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631846"
---
# <a name="download-the-validating-issuer-name-registry-package"></a><span data-ttu-id="d668b-102">発行者名レジストリの検証パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d668b-102">Download the Validating Issuer Name Registry Package</span></span>

<span data-ttu-id="d668b-103">このトピックでは、Validating Issuer Name Registry (VINR) をダウンロードしてプロジェクトで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d668b-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>

<span data-ttu-id="d668b-104">VINR は、プロジェクトに必要なアセンブリと参照を追加する NuGet パッケージとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="d668b-104">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="d668b-105">まだ NuGet がインストールされていない場合は、[nuget.org](https://nuget.org) にアクセスしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d668b-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="d668b-106">ページ NuGet にアクセスして、拡張機能のバージョン履歴を確認できます。[Microsoft が NuGet で発行者名レジストリの検証](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="d668b-106">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="d668b-107">パッケージ マネージャー GUI を使用します。</span><span class="sxs-lookup"><span data-stu-id="d668b-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="d668b-108">Visual Studio の**ソリューション エクスプローラー**でプロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d668b-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="d668b-109">**[NuGet パッケージの管理]** ウィンドウで、検索ボックスをクリックし、「`ValidatingIssuerNameRegistry`」と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d668b-109">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>

3. <span data-ttu-id="d668b-110">結果ペインから、最初の結果の **[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d668b-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="d668b-111">パッケージのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-111">The package will begin downloading.</span></span> <span data-ttu-id="d668b-112">プロジェクトに追加される前に、[License Acceptance] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="d668b-113">ライセンス条項に同意する場合は、**[I Accept]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d668b-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="d668b-114">最新の VINR アセンブリがダウンロードされ、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-114">The latest VINR assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="d668b-115">パッケージ マネージャー コンソールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d668b-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="d668b-116">Visual Studio で、次のようにクリックします。**ツール** > **NuGet パッケージ マネージャー** > **パッケージ マネージャー コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="d668b-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="d668b-117">**[パッケージ マネージャー コンソール]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="d668b-118">次のテキストを入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d668b-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. <span data-ttu-id="d668b-119">最新の VINR アセンブリがダウンロードされ、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-119">The latest VINR assemblies will be downloaded and added to your project.</span></span>

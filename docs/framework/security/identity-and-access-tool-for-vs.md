---
title: Identity and Access Tool for Visual Studio 2012
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
ms.openlocfilehash: 65d771b87cd3198848ffac387446abb17df18250
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940414"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a><span data-ttu-id="ec761-102">Identity and Access Tool for Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="ec761-102">Identity and Access Tool for Visual Studio 2012</span></span>
<span data-ttu-id="ec761-103">このトピックでは、新しい Identity and Access Tool for Visual Studio 11 について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec761-103">This topic describes the new Identity and Access Tool for Visual Studio 11.</span></span> <span data-ttu-id="ec761-104">このツールは、次の URL からダウンロードできます:<https://go.microsoft.com/fwlink/?LinkID=245849>またはから直接、拡張機能マネージャーで直接"id"を検索して、Visual Studio 11。</span><span class="sxs-lookup"><span data-stu-id="ec761-104">You can download this tool from the following URL: <https://go.microsoft.com/fwlink/?LinkID=245849> or directly from within Visual Studio 11 by searching for "identity" directly in the Extensions Manager.</span></span>  
  
 <span data-ttu-id="ec761-105">Identity and Access Tool for Visual Studio 11 の特長を次に示します。これにより、開発時の操作性が大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="ec761-105">The Identity and Access Tool for Visual Studio 11 delivers a dramatically simplified development-time experience with the following highlights:</span></span>  
  
- <span data-ttu-id="ec761-106">新しいツールを使用すると、Web アプリケーション プロジェクトの種類およびターゲット IIS Express を使用して開発できます。</span><span class="sxs-lookup"><span data-stu-id="ec761-106">Using the new tool, you can develop using web applications project types and target IIS express.</span></span>  
  
- <span data-ttu-id="ec761-107">ブランケット保護のみの認証とは異なり、新しいツールによって、ローカルのホーム レルム探索ページ/コントローラー (または、アプリケーション内で認証によって実行されるその他のエンドポイント処理) を指定できます。WIF は要求の構成を変更して、認証されていないすべての要求が、STS ではなくその場所にリダイレクトされるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec761-107">Unlike with the blanket protection-only authentication, with the new tool, you can specify your local home realm discovery page/controller (or any other endpoint handling the authentication experience within your application) and WIF will configure all unauthenticated requests to go there, instead of redirecting them to the STS.</span></span>  
  
- <span data-ttu-id="ec761-108">ツールには、テスト セキュリティ トークン サービス (STS) が含まれています。この STS は、デバッグ セッションの起動時にローカル コンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ec761-108">The tool includes a test Security Token Service (STS) which runs on your local machine when you launch a debug session.</span></span> <span data-ttu-id="ec761-109">したがって、アプリケーションのテストに必要なクレームを取得する目的で、カスタム STS プロジェクトを作成して調整する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ec761-109">Therefore, you no longer need to create custom STS projects and tweak them in order to get the claims you need to test your applications.</span></span> <span data-ttu-id="ec761-110">クレームの種類と値は完全にカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ec761-110">The claim types and values are fully customizable.</span></span>  
  
- <span data-ttu-id="ec761-111">ツールの UI を使用して共通の設定を直接変更できます。web.config を編集する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ec761-111">You can modify common settings directly via the tool’s UI, without the need to edit web.config.</span></span>  
  
- <span data-ttu-id="ec761-112">Active Directory フェデレーション サービス (AD FS) 2.0 (または、他の WS-Federation プロバイダー) を使用して、1 つの画面でフェデレーションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="ec761-112">You can establish federation with Active Directory Federation Services (AD FS) 2.0 (or other WS-Federation providers) in a single screen.</span></span>  
  
- <span data-ttu-id="ec761-113">ツールを使用するすべての id プロバイダーの簡単なチェック ボックスの一覧を Windows Azure の Access Control Service (ACS) 機能を活用します。Facebook、Google、Live ID、yahoo!、OpenID プロバイダー、および任意の Ws-federation プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="ec761-113">The tool leverages Windows Azure Access Control Service (ACS) capabilities with a simple list of checkboxes for all the identity providers that you want to use: Facebook, Google, Live ID, Yahoo!, any OpenID provider, and any WS-Federation provider.</span></span> <span data-ttu-id="ec761-114">ID プロバイダーのチェック ボックスをオンにして、[OK] をクリックし、F5 キーを押すと、アプリケーションと ACS の両方が自動的に構成され、テスト アプリケーションが ACS 対応になります。</span><span class="sxs-lookup"><span data-stu-id="ec761-114">Select your identity providers, click OK, then F5, and both your application and ACS will be automatically configured and your test application will be ACS-aware.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec761-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec761-115">See also</span></span>

- [<span data-ttu-id="ec761-116">WIF の機能</span><span class="sxs-lookup"><span data-stu-id="ec761-116">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)

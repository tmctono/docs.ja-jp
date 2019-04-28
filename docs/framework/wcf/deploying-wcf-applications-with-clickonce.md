---
title: ClickOnce を使用して WCF アプリケーションを展開する
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: 1820b00aa903633750f74f319f9cf8038ba2b043
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785094"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="d9fe2-102">ClickOnce を使用して WCF アプリケーションを展開する</span><span class="sxs-lookup"><span data-stu-id="d9fe2-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="d9fe2-103">Windows Communication Foundation (WCF) を使用するクライアント アプリケーションは、ClickOnce テクノロジを使用してデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="d9fe2-104">このテクノロジを使用すると、クライアント アプリケーションが、信頼できる証明書でデジタル署名されている場合、コード アクセス セキュリティによって提供されるランタイム セキュリティ保護を受けられます。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="d9fe2-105">ClickOnce アプリケーションの署名に使用される証明書は、信頼された発行者のストアに存在する必要があり、またそのクライアント コンピューターのローカル セキュリティ ポリシーでは、発行者の証明書で署名されたアプリケーションに対して、完全信頼のアクセス許可が構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="d9fe2-106">ClickOnce アプリケーションと信頼された発行元を構成する方法の詳細については、次を参照してください。 [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774)します。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fe2-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9fe2-107">See also</span></span>

- [<span data-ttu-id="d9fe2-108">信頼されたアプリケーションの配置の概要</span><span class="sxs-lookup"><span data-stu-id="d9fe2-108">Trusted Application Deployment Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=94775)
- [<span data-ttu-id="d9fe2-109">ClickOnce 配置の Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d9fe2-109">ClickOnce Deployment for Windows Forms Applications</span></span>](https://go.microsoft.com/fwlink/?LinkId=94776)

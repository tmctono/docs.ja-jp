---
title: クライアントでのデバッグ
ms.date: 03/30/2017
ms.assetid: 56f9ad05-ea1b-4ef6-85f2-890f7ed71567
ms.openlocfilehash: 0330e0954969fbaf798fe3be029b443f0fa219cd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589358"
---
# <a name="debugging-on-the-client"></a><span data-ttu-id="4492d-102">クライアントでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="4492d-102">Debugging on the Client</span></span>
<span data-ttu-id="4492d-103">ユーザーが WCF サービスのクライアントアプリケーションを簡単に作成できるようにするには、サービス [\<serviceDebug>](../../../configure-apps/file-schema/wcf/servicedebug.md) の構成ファイルにサービスの動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="4492d-103">To make it easier for users to write client applications for your WCF service, you can add the [\<serviceDebug>](../../../configure-apps/file-schema/wcf/servicedebug.md) service behavior to the configuration file of your service.</span></span> <span data-ttu-id="4492d-104">この動作は、ヘルプ ページを公開し、クライアントに返される SOAP エラーの詳細にマネージド例外情報を表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4492d-104">This behavior can be used to publish help pages, and return managed exception information in the details of SOAP faults returned to the client.</span></span>

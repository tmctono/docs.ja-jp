---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "61704363"
---
# \<commonBehaviors>
<span data-ttu-id="2b59e-101">`commonBehaviors` セクションは、machine.config ファイルでだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="2b59e-101">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="2b59e-102">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="2b59e-102">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2b59e-103">各コレクションは、コンピューター上のすべての WCF エンドポイントとサービスによって使用される動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b59e-103">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="2b59e-104">`endpointBehaviors` で定義される動作はクライアントだけに適用され、`serviceBehaviors` で定義される動作はサービスだけに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b59e-104">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="2b59e-105">ある動作が `commonBehaviors` と `behaviors` の両方のセクションで定義されている場合は、`behaviors` セクション内の動作が優先されます。</span><span class="sxs-lookup"><span data-stu-id="2b59e-105">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>

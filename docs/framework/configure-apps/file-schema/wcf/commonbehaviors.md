---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704363"
---
# <a name="commonbehaviors"></a><span data-ttu-id="c99df-101">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="c99df-101">\<commonBehaviors></span></span>
<span data-ttu-id="c99df-102">`commonBehaviors` セクションは、machine.config ファイルでだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="c99df-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="c99df-103">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="c99df-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="c99df-104">各コレクションは、それぞれのすべての WCF エンドポイントと、コンピューター上のサービスで使用された動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="c99df-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="c99df-105">`endpointBehaviors` で定義される動作はクライアントだけに適用され、`serviceBehaviors` で定義される動作はサービスだけに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c99df-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="c99df-106">ある動作が `commonBehaviors` と `behaviors` の両方のセクションで定義されている場合は、`behaviors` セクション内の動作が優先されます。</span><span class="sxs-lookup"><span data-stu-id="c99df-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>

---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794525"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="a485f-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="a485f-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="a485f-103">インスタンスを作成、 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)クラス。</span><span class="sxs-lookup"><span data-stu-id="a485f-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a485f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a485f-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a485f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a485f-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="a485f-106">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="a485f-106">Parameter Values</span></span>  
 <span data-ttu-id="a485f-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="a485f-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="a485f-108">操作名、戻り値の型、パラメーター情報など、生成されるワークフロー アクティビティで実行される操作を記述します。</span><span class="sxs-lookup"><span data-stu-id="a485f-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="a485f-109">このパラメーターの値がある必要がありますいない**null**します。</span><span class="sxs-lookup"><span data-stu-id="a485f-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="a485f-110">これは、メッセージ コントラクトを使用し、1 つのメッセージと共に引数を受け取る同期操作を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a485f-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="a485f-111">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="a485f-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="a485f-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="a485f-112">*configurationName*</span></span>  
  
 <span data-ttu-id="a485f-113">エンドポイント構成名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a485f-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="a485f-114">このパラメーターの値かする必要がありますいない**null**または空です。</span><span class="sxs-lookup"><span data-stu-id="a485f-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="a485f-115">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="a485f-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="a485f-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="a485f-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="a485f-117">操作のサービスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a485f-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="a485f-118">このパラメーターの値かする必要がありますいない**null**または空です。</span><span class="sxs-lookup"><span data-stu-id="a485f-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="a485f-119">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="a485f-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a485f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a485f-120">See also</span></span>

- [<span data-ttu-id="a485f-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="a485f-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

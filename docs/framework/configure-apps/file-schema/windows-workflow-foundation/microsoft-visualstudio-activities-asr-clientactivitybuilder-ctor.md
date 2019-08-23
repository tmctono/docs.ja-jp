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
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947627"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="f10d1-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="f10d1-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="f10d1-103">[VisualStudio](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)クラスのインスタンスを作成します。このクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f10d1-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f10d1-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f10d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f10d1-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="f10d1-106">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="f10d1-106">Parameter Values</span></span>  
 <span data-ttu-id="f10d1-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="f10d1-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="f10d1-108">操作名、戻り値の型、パラメーター情報など、生成されるワークフロー アクティビティで実行される操作を記述します。</span><span class="sxs-lookup"><span data-stu-id="f10d1-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="f10d1-109">このパラメーターの値を**null**にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f10d1-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="f10d1-110">これは、メッセージ コントラクトを使用し、1 つのメッセージと共に引数を受け取る同期操作を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f10d1-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="f10d1-111">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="f10d1-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="f10d1-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="f10d1-112">*configurationName*</span></span>  
  
 <span data-ttu-id="f10d1-113">エンドポイント構成名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f10d1-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="f10d1-114">このパラメーターの値を**null**または空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f10d1-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="f10d1-115">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="f10d1-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="f10d1-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="f10d1-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="f10d1-117">操作のサービスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f10d1-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="f10d1-118">このパラメーターの値を**null**または空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f10d1-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="f10d1-119">これらの条件が満たされていない場合、このクラスのコンストラクターと他のメソッドを使用したランタイムの結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="f10d1-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10d1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f10d1-120">See also</span></span>

- [<span data-ttu-id="f10d1-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="f10d1-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

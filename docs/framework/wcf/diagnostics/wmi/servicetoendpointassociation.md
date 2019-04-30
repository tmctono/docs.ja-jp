---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048232"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="8e37b-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="8e37b-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="8e37b-103">エンドポイントにサービスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8e37b-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e37b-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e37b-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8e37b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e37b-105">Methods</span></span>  
 <span data-ttu-id="8e37b-106">ServiceToEndpointAssociation クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="8e37b-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8e37b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8e37b-107">Properties</span></span>  
 <span data-ttu-id="8e37b-108">ServiceToEndpointAssociation クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8e37b-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8e37b-109">ref</span><span class="sxs-lookup"><span data-stu-id="8e37b-109">ref</span></span>  
 <span data-ttu-id="8e37b-110">データの種類:サービス</span><span class="sxs-lookup"><span data-stu-id="8e37b-110">Data type: Service</span></span>  
  
 <span data-ttu-id="8e37b-111">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="8e37b-111">Access type: Read-only</span></span>  
<span data-ttu-id="8e37b-112">修飾子:キー</span><span class="sxs-lookup"><span data-stu-id="8e37b-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="8e37b-113">エンドポイントに関連付けられるサービス。</span><span class="sxs-lookup"><span data-stu-id="8e37b-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8e37b-114">ref</span><span class="sxs-lookup"><span data-stu-id="8e37b-114">ref</span></span>  
 <span data-ttu-id="8e37b-115">データの種類:エンドポイント</span><span class="sxs-lookup"><span data-stu-id="8e37b-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="8e37b-116">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="8e37b-116">Access type: Read-only</span></span>  
<span data-ttu-id="8e37b-117">修飾子:キー</span><span class="sxs-lookup"><span data-stu-id="8e37b-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="8e37b-118">サービスに関連付けられるエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="8e37b-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e37b-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e37b-119">Requirements</span></span>  
  
|<span data-ttu-id="8e37b-120">MOF</span><span class="sxs-lookup"><span data-stu-id="8e37b-120">MOF</span></span>|<span data-ttu-id="8e37b-121">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="8e37b-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8e37b-122">名前空間</span><span class="sxs-lookup"><span data-stu-id="8e37b-122">Namespace</span></span>|<span data-ttu-id="8e37b-123">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="8e37b-123">Defined in root\ServiceModel</span></span>|

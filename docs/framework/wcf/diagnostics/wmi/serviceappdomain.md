---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957074"
---
# <a name="serviceappdomain"></a><span data-ttu-id="6f4db-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="6f4db-102">ServiceAppDomain</span></span>
<span data-ttu-id="6f4db-103">アプリケーション ドメインにサービスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6f4db-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4db-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f4db-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6f4db-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6f4db-105">Methods</span></span>  
 <span data-ttu-id="6f4db-106">ServiceAppDomain クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="6f4db-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6f4db-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6f4db-107">Properties</span></span>  
 <span data-ttu-id="6f4db-108">ServiceAppDomain クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6f4db-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6f4db-109">ref</span><span class="sxs-lookup"><span data-stu-id="6f4db-109">ref</span></span>  
 <span data-ttu-id="6f4db-110">データの種類:サービス</span><span class="sxs-lookup"><span data-stu-id="6f4db-110">Data type: Service</span></span>  
<span data-ttu-id="6f4db-111">修飾子:キー</span><span class="sxs-lookup"><span data-stu-id="6f4db-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6f4db-112">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="6f4db-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4db-113">このアプリケーション ドメインのサービスです。</span><span class="sxs-lookup"><span data-stu-id="6f4db-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6f4db-114">ref</span><span class="sxs-lookup"><span data-stu-id="6f4db-114">ref</span></span>  
 <span data-ttu-id="6f4db-115">データの種類:AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="6f4db-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="6f4db-116">修飾子:キー</span><span class="sxs-lookup"><span data-stu-id="6f4db-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6f4db-117">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="6f4db-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4db-118">アプリケーション ドメインのプロパティが格納されています。</span><span class="sxs-lookup"><span data-stu-id="6f4db-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f4db-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f4db-119">Requirements</span></span>  
  
|<span data-ttu-id="6f4db-120">MOF</span><span class="sxs-lookup"><span data-stu-id="6f4db-120">MOF</span></span>|<span data-ttu-id="6f4db-121">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="6f4db-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6f4db-122">名前空間</span><span class="sxs-lookup"><span data-stu-id="6f4db-122">Namespace</span></span>|<span data-ttu-id="6f4db-123">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="6f4db-123">Defined in root\ServiceModel</span></span>|

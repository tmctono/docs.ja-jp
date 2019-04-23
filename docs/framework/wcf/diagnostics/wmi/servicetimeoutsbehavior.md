---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59972811"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="f19b9-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="f19b9-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="f19b9-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="f19b9-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f19b9-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f19b9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f19b9-105">Methods</span></span>  
 <span data-ttu-id="f19b9-106">ServiceTimeoutsBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="f19b9-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f19b9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f19b9-107">Properties</span></span>  
 <span data-ttu-id="f19b9-108">ServiceTimeoutsBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f19b9-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="f19b9-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="f19b9-109">TransactionTimeout</span></span>  
 <span data-ttu-id="f19b9-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="f19b9-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="f19b9-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="f19b9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f19b9-112">トランザクションを完了しなければならない期間。</span><span class="sxs-lookup"><span data-stu-id="f19b9-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19b9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f19b9-113">Requirements</span></span>  
  
|<span data-ttu-id="f19b9-114">MOF</span><span class="sxs-lookup"><span data-stu-id="f19b9-114">MOF</span></span>|<span data-ttu-id="f19b9-115">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="f19b9-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f19b9-116">名前空間</span><span class="sxs-lookup"><span data-stu-id="f19b9-116">Namespace</span></span>|<span data-ttu-id="f19b9-117">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="f19b9-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f19b9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f19b9-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

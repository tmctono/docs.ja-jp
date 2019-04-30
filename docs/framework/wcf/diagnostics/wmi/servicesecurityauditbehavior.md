---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956898"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="3f007-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="3f007-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="3f007-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="3f007-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f007-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f007-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3f007-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3f007-105">Methods</span></span>  
 <span data-ttu-id="3f007-106">ServiceSecurityAuditBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="3f007-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3f007-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f007-107">Properties</span></span>  
 <span data-ttu-id="3f007-108">ServiceSecurityAuditBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="3f007-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="3f007-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="3f007-109">AuditLogLocation</span></span>  
 <span data-ttu-id="3f007-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="3f007-110">Data type: string</span></span>  
  
 <span data-ttu-id="3f007-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="3f007-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f007-112">監査ログの場所。</span><span class="sxs-lookup"><span data-stu-id="3f007-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="3f007-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3f007-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="3f007-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="3f007-114">Data type: string</span></span>  
  
 <span data-ttu-id="3f007-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="3f007-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f007-116">監査イベントをログに記録するために使用されるメッセージ認証レベルの種類。</span><span class="sxs-lookup"><span data-stu-id="3f007-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="3f007-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3f007-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="3f007-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="3f007-118">Data type: string</span></span>  
  
 <span data-ttu-id="3f007-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="3f007-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f007-120">監査ログに記録される承認イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="3f007-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="3f007-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="3f007-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="3f007-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="3f007-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f007-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="3f007-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f007-124">監査ログへの書き込みエラーを非表示にする動作を指定するブール型の値。</span><span class="sxs-lookup"><span data-stu-id="3f007-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f007-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f007-125">Requirements</span></span>  
  
|<span data-ttu-id="3f007-126">MOF</span><span class="sxs-lookup"><span data-stu-id="3f007-126">MOF</span></span>|<span data-ttu-id="3f007-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="3f007-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3f007-128">名前空間</span><span class="sxs-lookup"><span data-stu-id="3f007-128">Namespace</span></span>|<span data-ttu-id="3f007-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="3f007-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f007-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f007-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>

---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641685"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="25352-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="25352-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="25352-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="25352-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25352-104">構文</span><span class="sxs-lookup"><span data-stu-id="25352-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="25352-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="25352-105">Methods</span></span>  
 <span data-ttu-id="25352-106">TransactionFlowBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="25352-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="25352-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="25352-107">Properties</span></span>  
 <span data-ttu-id="25352-108">TransactionFlowBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="25352-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="25352-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="25352-109">IssuedTokens</span></span>  
 <span data-ttu-id="25352-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="25352-110">Data type: string</span></span>  
  
 <span data-ttu-id="25352-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="25352-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25352-112">発行されるセキュリティ トークン ヘッダー (WS-Trust からの IssuedTokens) の要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="25352-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="25352-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="25352-113">TransactionProtocol</span></span>  
 <span data-ttu-id="25352-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="25352-114">Data type: string</span></span>  
  
 <span data-ttu-id="25352-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="25352-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25352-116">トランザクションをフローさせるためにサービスによって使用されるトランザクション プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="25352-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="25352-117">トランザクション</span><span class="sxs-lookup"><span data-stu-id="25352-117">Transactions</span></span>  
 <span data-ttu-id="25352-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="25352-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="25352-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="25352-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25352-120">受信トランザクションをサポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="25352-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25352-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="25352-121">Requirements</span></span>  
  
|<span data-ttu-id="25352-122">MOF</span><span class="sxs-lookup"><span data-stu-id="25352-122">MOF</span></span>|<span data-ttu-id="25352-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="25352-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="25352-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="25352-124">Namespace</span></span>|<span data-ttu-id="25352-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="25352-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25352-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="25352-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

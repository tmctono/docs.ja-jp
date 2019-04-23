---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 6fa68eed241edaea40b66c31240a4201e05779f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975351"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="88dcc-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="88dcc-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="88dcc-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="88dcc-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88dcc-104">構文</span><span class="sxs-lookup"><span data-stu-id="88dcc-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="88dcc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="88dcc-105">Methods</span></span>  
 <span data-ttu-id="88dcc-106">TcpConnectionPoolSettings クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="88dcc-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="88dcc-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="88dcc-107">Properties</span></span>  
 <span data-ttu-id="88dcc-108">TcpConnectionPoolSettings クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="88dcc-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="88dcc-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="88dcc-109">GroupName</span></span>  
 <span data-ttu-id="88dcc-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="88dcc-110">Data type: string</span></span>  
  
 <span data-ttu-id="88dcc-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="88dcc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88dcc-112">バインド要素により使用される接続プールのグループ名。</span><span class="sxs-lookup"><span data-stu-id="88dcc-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="88dcc-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="88dcc-113">IdleTimeout</span></span>  
 <span data-ttu-id="88dcc-114">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="88dcc-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="88dcc-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="88dcc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88dcc-116">接続が切断されるまでの最大アイドル時間。</span><span class="sxs-lookup"><span data-stu-id="88dcc-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="88dcc-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="88dcc-117">LeaseTimeout</span></span>  
 <span data-ttu-id="88dcc-118">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="88dcc-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="88dcc-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="88dcc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88dcc-120">リース操作を完了する必要がある、タイムアウトまでの最大時間。</span><span class="sxs-lookup"><span data-stu-id="88dcc-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="88dcc-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="88dcc-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="88dcc-122">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="88dcc-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="88dcc-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="88dcc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88dcc-124">各エンドポイントの発信接続の最大数。</span><span class="sxs-lookup"><span data-stu-id="88dcc-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88dcc-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="88dcc-125">Requirements</span></span>  
  
|<span data-ttu-id="88dcc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="88dcc-126">MOF</span></span>|<span data-ttu-id="88dcc-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="88dcc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="88dcc-128">名前空間</span><span class="sxs-lookup"><span data-stu-id="88dcc-128">Namespace</span></span>|<span data-ttu-id="88dcc-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="88dcc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88dcc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="88dcc-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>

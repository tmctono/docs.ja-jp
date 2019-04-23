---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773702"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="f1fb7-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f1fb7-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="f1fb7-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f1fb7-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fb7-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1fb7-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f1fb7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1fb7-105">Methods</span></span>  
 <span data-ttu-id="f1fb7-106">NamedPipeConnectionPoolSettings クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f1fb7-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1fb7-107">Properties</span></span>  
 <span data-ttu-id="f1fb7-108">NamedPipeConnectionPoolSettings クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="f1fb7-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="f1fb7-109">GroupName</span></span>  
 <span data-ttu-id="f1fb7-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="f1fb7-110">Data type: string</span></span>  
  
 <span data-ttu-id="f1fb7-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="f1fb7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f1fb7-112">バインド要素により使用される接続プールのグループ名。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f1fb7-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f1fb7-113">IdleTimeout</span></span>  
 <span data-ttu-id="f1fb7-114">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="f1fb7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f1fb7-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="f1fb7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f1fb7-116">接続が切断されるまでの最大アイドル時間。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="f1fb7-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f1fb7-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="f1fb7-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="f1fb7-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f1fb7-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="f1fb7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f1fb7-120">クライアント上の各エンドポイントでの発信接続の最大数。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1fb7-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1fb7-121">Requirements</span></span>  
  
|<span data-ttu-id="f1fb7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f1fb7-122">MOF</span></span>|<span data-ttu-id="f1fb7-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="f1fb7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f1fb7-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="f1fb7-124">Namespace</span></span>|<span data-ttu-id="f1fb7-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="f1fb7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1fb7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1fb7-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>

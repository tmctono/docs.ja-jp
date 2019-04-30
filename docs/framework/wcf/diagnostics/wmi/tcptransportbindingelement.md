---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956547"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="0d7a1-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0d7a1-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="0d7a1-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0d7a1-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d7a1-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0d7a1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d7a1-105">Methods</span></span>  
 <span data-ttu-id="0d7a1-106">TcpTransportBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0d7a1-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d7a1-107">Properties</span></span>  
 <span data-ttu-id="0d7a1-108">TcpTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="0d7a1-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0d7a1-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="0d7a1-110">データの種類:TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0d7a1-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="0d7a1-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0d7a1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d7a1-112">接続プールの設定。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="0d7a1-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="0d7a1-113">ListenBacklog</span></span>  
 <span data-ttu-id="0d7a1-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="0d7a1-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="0d7a1-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0d7a1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d7a1-116">保留可能なキュー内の接続要求の最大数です。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="0d7a1-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="0d7a1-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="0d7a1-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="0d7a1-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="0d7a1-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0d7a1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d7a1-120">TCP ポート共有をこの接続で有効にするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="0d7a1-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="0d7a1-121">TeredoEnabled</span></span>  
 <span data-ttu-id="0d7a1-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="0d7a1-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="0d7a1-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0d7a1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d7a1-124">Teredo (ファイアウォールの内側にあるクライアントをアドレス指定するためのテクノロジ) を有効にするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7a1-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d7a1-125">Requirements</span></span>  
  
|<span data-ttu-id="0d7a1-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0d7a1-126">MOF</span></span>|<span data-ttu-id="0d7a1-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="0d7a1-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0d7a1-128">名前空間</span><span class="sxs-lookup"><span data-stu-id="0d7a1-128">Namespace</span></span>|<span data-ttu-id="0d7a1-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="0d7a1-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d7a1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7a1-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

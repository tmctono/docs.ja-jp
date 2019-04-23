---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770751"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="1ab0a-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1ab0a-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="1ab0a-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1ab0a-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab0a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ab0a-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1ab0a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1ab0a-105">Methods</span></span>  
 <span data-ttu-id="1ab0a-106">MsmqTransportBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1ab0a-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1ab0a-107">Properties</span></span>  
 <span data-ttu-id="1ab0a-108">MsmqTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="1ab0a-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="1ab0a-109">MaxPoolSize</span></span>  
 <span data-ttu-id="1ab0a-110">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="1ab0a-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="1ab0a-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1ab0a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ab0a-112">内部 MSMQ メッセージ オブジェクトを含むプールの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="1ab0a-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="1ab0a-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="1ab0a-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1ab0a-114">Data type: string</span></span>  
  
 <span data-ttu-id="1ab0a-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1ab0a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ab0a-116">このバインディングが使用するキューに置かれた通信チャネルのトランスポートを示す列挙値です。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="1ab0a-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="1ab0a-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="1ab0a-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="1ab0a-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="1ab0a-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1ab0a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ab0a-120">キューのアドレスを Active Directory を使用して変換する必要があるかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab0a-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ab0a-121">Requirements</span></span>  
  
|<span data-ttu-id="1ab0a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1ab0a-122">MOF</span></span>|<span data-ttu-id="1ab0a-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="1ab0a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1ab0a-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="1ab0a-124">Namespace</span></span>|<span data-ttu-id="1ab0a-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="1ab0a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ab0a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ab0a-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

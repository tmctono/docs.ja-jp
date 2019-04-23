---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976899"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="229e9-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="229e9-102">PeerSecuritySettings</span></span>
<span data-ttu-id="229e9-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="229e9-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="229e9-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="229e9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="229e9-105">Methods</span></span>  
 <span data-ttu-id="229e9-106">PeerSecuritySettings クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="229e9-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="229e9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="229e9-107">Properties</span></span>  
 <span data-ttu-id="229e9-108">PeerSecuritySettings クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="229e9-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="229e9-109">モード</span><span class="sxs-lookup"><span data-stu-id="229e9-109">Mode</span></span>  
 <span data-ttu-id="229e9-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="229e9-110">Data type: string</span></span>  
  
 <span data-ttu-id="229e9-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="229e9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="229e9-112">このバインディングで構成されたエンドポイントによって、メッセージ レベルおよびトランスポート レベルのセキュリティが使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="229e9-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="229e9-113">Transport</span><span class="sxs-lookup"><span data-stu-id="229e9-113">Transport</span></span>  
 <span data-ttu-id="229e9-114">データの種類:PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="229e9-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="229e9-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="229e9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="229e9-116">トランスポートのセキュリティ設定です。</span><span class="sxs-lookup"><span data-stu-id="229e9-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="229e9-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="229e9-117">Requirements</span></span>  
  
|<span data-ttu-id="229e9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="229e9-118">MOF</span></span>|<span data-ttu-id="229e9-119">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="229e9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="229e9-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="229e9-120">Namespace</span></span>|<span data-ttu-id="229e9-121">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="229e9-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="229e9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="229e9-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>

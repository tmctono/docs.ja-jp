---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770413"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="505d9-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="505d9-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="505d9-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="505d9-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="505d9-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="505d9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="505d9-105">Methods</span></span>  
 <span data-ttu-id="505d9-106">SymmetricSecurityBindingElement クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="505d9-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="505d9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="505d9-107">Properties</span></span>  
 <span data-ttu-id="505d9-108">SymmetricSecurityBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="505d9-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="505d9-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="505d9-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="505d9-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="505d9-110">Data type: string</span></span>  
  
 <span data-ttu-id="505d9-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="505d9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="505d9-112">このバインディングのメッセージの暗号化と署名の命令。</span><span class="sxs-lookup"><span data-stu-id="505d9-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="505d9-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="505d9-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="505d9-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="505d9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="505d9-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="505d9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="505d9-116">バインディングで署名の確認が必要かどうか。</span><span class="sxs-lookup"><span data-stu-id="505d9-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="505d9-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="505d9-117">Requirements</span></span>  
  
|<span data-ttu-id="505d9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="505d9-118">MOF</span></span>|<span data-ttu-id="505d9-119">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="505d9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="505d9-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="505d9-120">Namespace</span></span>|<span data-ttu-id="505d9-121">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="505d9-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="505d9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="505d9-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196048"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="ff28f-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff28f-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="ff28f-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff28f-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff28f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ff28f-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ff28f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff28f-105">Methods</span></span>  
 <span data-ttu-id="ff28f-106">AsymmetricSecurityBindingElement クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="ff28f-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ff28f-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ff28f-107">Properties</span></span>  
 <span data-ttu-id="ff28f-108">AsymmetricSecurityBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ff28f-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="ff28f-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="ff28f-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="ff28f-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="ff28f-110">Data type: string</span></span>  
  
 <span data-ttu-id="ff28f-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="ff28f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff28f-112">このバインディングのメッセージの暗号化と署名の命令。</span><span class="sxs-lookup"><span data-stu-id="ff28f-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="ff28f-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="ff28f-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="ff28f-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="ff28f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ff28f-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="ff28f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff28f-116">バインディングで署名の確認が必要かどうか。</span><span class="sxs-lookup"><span data-stu-id="ff28f-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff28f-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="ff28f-117">Requirements</span></span>  
  
|<span data-ttu-id="ff28f-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ff28f-118">MOF</span></span>|<span data-ttu-id="ff28f-119">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="ff28f-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ff28f-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="ff28f-120">Namespace</span></span>|<span data-ttu-id="ff28f-121">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="ff28f-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff28f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff28f-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

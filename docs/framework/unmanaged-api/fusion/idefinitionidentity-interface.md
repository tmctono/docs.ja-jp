---
title: IDefinitionIdentity インターフェイス
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108039"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="963d8-102">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="963d8-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="963d8-103">現在のスコープ内のアプリケーションを定義するコードの一意の署名を表します。</span><span class="sxs-lookup"><span data-stu-id="963d8-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="963d8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="963d8-104">Methods</span></span>  
  
|<span data-ttu-id="963d8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="963d8-105">Method</span></span>|<span data-ttu-id="963d8-106">説明</span><span class="sxs-lookup"><span data-stu-id="963d8-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="963d8-107">指定した属性の変更を除き、この `IDefinitionIdentity`と同一の新しい `IDefinitionIdentity` オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="963d8-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="963d8-108">この `IDefinitionIdentity`に関連付けられている属性を格納している[IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="963d8-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="963d8-109">指定した名前空間内の指定した名前の属性の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="963d8-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="963d8-110">指定した名前空間の指定した名前を持つ属性を、指定した値に設定します。</span><span class="sxs-lookup"><span data-stu-id="963d8-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="963d8-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="963d8-111">Requirements</span></span>  
 <span data-ttu-id="963d8-112">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="963d8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963d8-113">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="963d8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="963d8-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="963d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963d8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="963d8-115">See also</span></span>

- [<span data-ttu-id="963d8-116">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="963d8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)

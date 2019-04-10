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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192668"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="4f474-102">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f474-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="4f474-103">現在のスコープ内でアプリケーションを定義するコードの一意のシグネチャを表します。</span><span class="sxs-lookup"><span data-stu-id="4f474-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f474-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4f474-104">Methods</span></span>  
  
|<span data-ttu-id="4f474-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4f474-105">Method</span></span>|<span data-ttu-id="4f474-106">説明</span><span class="sxs-lookup"><span data-stu-id="4f474-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="4f474-107">新しいインターフェイス ポインターを取得`IDefinitionIdentity`これと同じであるオブジェクト`IDefinitionIdentity`、指定した属性の変更を除く。</span><span class="sxs-lookup"><span data-stu-id="4f474-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="4f474-108">インターフェイス ポインターを取得、 [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)オブジェクトに関連付けられた属性を含む`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="4f474-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="4f474-109">指定した名前空間には、指定した名前の属性の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f474-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="4f474-110">指定した値を指定した名前空間で指定した名前を持つ属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f474-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f474-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f474-111">Requirements</span></span>  
 <span data-ttu-id="4f474-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f474-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f474-113">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="4f474-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="4f474-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4f474-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f474-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f474-115">See also</span></span>

- [<span data-ttu-id="4f474-116">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f474-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

---
title: IAssemblyName::Finalize メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4db24977d46277bc16a8800b0c4f7a550747cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206526"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="b69c2-102">IAssemblyName::Finalize メソッド</span><span class="sxs-lookup"><span data-stu-id="b69c2-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="b69c2-103">これにより、 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト リソースを解放し、そのデストラクターが呼び出される前に、他のクリーンアップ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b69c2-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b69c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="b69c2-104">Syntax</span></span>  
  
```  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="b69c2-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="b69c2-105">Requirements</span></span>  
 <span data-ttu-id="b69c2-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69c2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b69c2-107">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b69c2-107">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="b69c2-108">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b69c2-108">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b69c2-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b69c2-109">See also</span></span>

- [<span data-ttu-id="b69c2-110">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b69c2-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)

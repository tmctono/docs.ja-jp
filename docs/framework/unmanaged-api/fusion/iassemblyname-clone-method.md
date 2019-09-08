---
title: IAssemblyName::Clone メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c71616d261f145574d580b68793ec91bb4ea3f42
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796645"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="92139-102">IAssemblyName::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="92139-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="92139-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトの簡易コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="92139-103">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92139-104">構文</span><span class="sxs-lookup"><span data-stu-id="92139-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92139-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92139-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="92139-106">入出力この`IAssemblyName`オブジェクトの返されたコピー。</span><span class="sxs-lookup"><span data-stu-id="92139-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92139-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="92139-107">Requirements</span></span>  
 <span data-ttu-id="92139-108">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92139-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92139-109">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="92139-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="92139-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92139-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92139-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="92139-111">See also</span></span>

- [<span data-ttu-id="92139-112">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92139-112">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

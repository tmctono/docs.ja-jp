---
title: IAssemblyName::IsEqual メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 926bdcee3a3c3974c8546f3a6dfe98f0b62c93c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796563"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="73a0e-102">IAssemblyName::IsEqual メソッド</span><span class="sxs-lookup"><span data-stu-id="73a0e-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="73a0e-103">指定した比較フラグに基づいて、指定`IAssemblyName`した [IAssemblyName](iassemblyname-interface.md) オブジェクトがこのと等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="73a0e-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="73a0e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73a0e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73a0e-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="73a0e-106">から`IAssemblyName` この`IAssemblyName`と比較するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="73a0e-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="73a0e-107">から比較に影響を与える[ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="73a0e-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73a0e-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="73a0e-108">Requirements</span></span>  
 <span data-ttu-id="73a0e-109">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73a0e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a0e-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="73a0e-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="73a0e-111">**.Net Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73a0e-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a0e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="73a0e-112">See also</span></span>

- [<span data-ttu-id="73a0e-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a0e-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="73a0e-114">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="73a0e-114">Fusion Enumerations</span></span>](fusion-enumerations.md)

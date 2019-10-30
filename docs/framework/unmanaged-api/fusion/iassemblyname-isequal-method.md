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
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134306"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="e42bd-102">IAssemblyName::IsEqual メソッド</span><span class="sxs-lookup"><span data-stu-id="e42bd-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="e42bd-103">指定した比較フラグに基づいて、指定した[IAssemblyName](iassemblyname-interface.md)オブジェクトがこの `IAssemblyName`と等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e42bd-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e42bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="e42bd-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e42bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e42bd-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="e42bd-106">からこの `IAssemblyName`と比較する `IAssemblyName` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e42bd-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="e42bd-107">から比較に影響を与える[ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e42bd-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e42bd-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="e42bd-108">Requirements</span></span>  
 <span data-ttu-id="e42bd-109">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e42bd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e42bd-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e42bd-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e42bd-111">**.Net Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e42bd-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42bd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e42bd-112">See also</span></span>

- [<span data-ttu-id="e42bd-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e42bd-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="e42bd-114">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="e42bd-114">Fusion Enumerations</span></span>](fusion-enumerations.md)

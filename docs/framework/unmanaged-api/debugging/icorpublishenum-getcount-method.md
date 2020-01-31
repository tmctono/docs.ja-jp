---
title: ICorPublishEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: 0b3754fbcca50b52039dc358aed7070b8a152ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790636"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="4ce46-102">ICorPublishEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="4ce46-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="4ce46-103">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ce46-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce46-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ce46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ce46-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ce46-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="4ce46-106">入出力列挙体に含まれる項目の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4ce46-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ce46-107">要件</span><span class="sxs-lookup"><span data-stu-id="4ce46-107">Requirements</span></span>  
 <span data-ttu-id="4ce46-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ce46-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ce46-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="4ce46-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4ce46-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ce46-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ce46-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce46-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce46-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ce46-112">See also</span></span>

- [<span data-ttu-id="4ce46-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ce46-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)

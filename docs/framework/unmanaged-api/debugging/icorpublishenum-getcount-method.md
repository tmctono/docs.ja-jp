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
ms.openlocfilehash: 7ed4236187fab1c1e81be9ddcdff1f1852e38f70
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421190"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="df7ca-102">ICorPublishEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="df7ca-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="df7ca-103">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="df7ca-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="df7ca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df7ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df7ca-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="df7ca-106">入出力列挙体に含まれる項目の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="df7ca-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7ca-107">要件</span><span class="sxs-lookup"><span data-stu-id="df7ca-107">Requirements</span></span>  
 <span data-ttu-id="df7ca-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df7ca-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7ca-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="df7ca-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="df7ca-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df7ca-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df7ca-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7ca-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7ca-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="df7ca-112">See also</span></span>

- [<span data-ttu-id="df7ca-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df7ca-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)

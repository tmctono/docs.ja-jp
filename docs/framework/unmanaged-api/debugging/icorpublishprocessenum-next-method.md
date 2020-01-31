---
title: ICorPublishProcessEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790513"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="81528-102">ICorPublishProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="81528-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="81528-103">現在のカーソル位置から開始して、指定した数のプロセスをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="81528-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81528-104">構文</span><span class="sxs-lookup"><span data-stu-id="81528-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81528-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81528-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="81528-106">から取得するプロセスの数。</span><span class="sxs-lookup"><span data-stu-id="81528-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="81528-107">入出力取得された[ICorPublishProcess](icorpublishprocess-interface.md)オブジェクトの配列へのポインター。それぞれがプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="81528-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="81528-108">入出力実際に返されたプロセスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="81528-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="81528-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="81528-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81528-110">要件</span><span class="sxs-lookup"><span data-stu-id="81528-110">Requirements</span></span>  
 <span data-ttu-id="81528-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81528-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81528-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="81528-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="81528-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81528-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81528-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81528-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81528-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="81528-115">See also</span></span>

- [<span data-ttu-id="81528-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81528-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)

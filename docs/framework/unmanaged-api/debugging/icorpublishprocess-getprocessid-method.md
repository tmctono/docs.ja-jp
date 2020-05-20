---
title: ICorPublishProcess::GetProcessID メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 95a4ef3ab77b33c67c63be2c22647075f2f95ce8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421112"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="c3059-102">ICorPublishProcess::GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="c3059-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="c3059-103">このプロセスのオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c3059-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3059-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3059-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3059-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3059-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="c3059-106">入出力この[ICorPublishProcess](icorpublishprocess-interface.md)オブジェクトによって表されるプロセスの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c3059-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3059-107">要件</span><span class="sxs-lookup"><span data-stu-id="c3059-107">Requirements</span></span>  
 <span data-ttu-id="c3059-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3059-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3059-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="c3059-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c3059-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3059-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3059-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3059-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3059-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3059-112">See also</span></span>

- [<span data-ttu-id="c3059-113">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3059-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)

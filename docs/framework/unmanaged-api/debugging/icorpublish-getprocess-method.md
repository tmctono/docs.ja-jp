---
title: ICorPublish::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178418"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="5ca62-102">ICorPublish::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="5ca62-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="5ca62-103">指定した識別子を持つプロセスを表す[ICorPublishProcess](icorpublishprocess-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ca62-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca62-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ca62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ca62-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5ca62-106">[in]プロセスの識別子。</span><span class="sxs-lookup"><span data-stu-id="5ca62-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="5ca62-107">[アウト]プロセスを表す`ICorPublishProcess`インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5ca62-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ca62-108">解説</span><span class="sxs-lookup"><span data-stu-id="5ca62-108">Remarks</span></span>  
 <span data-ttu-id="5ca62-109">`GetProcess`プロセスが存在しない場合、または現在のユーザーがデバッグできるマネージ プロセスでない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5ca62-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ca62-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ca62-110">Requirements</span></span>  
 <span data-ttu-id="5ca62-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ca62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca62-112">**ヘッダー:** コルパブ.idl,コルパブ.h</span><span class="sxs-lookup"><span data-stu-id="5ca62-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5ca62-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ca62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ca62-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca62-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ca62-115">See also</span></span>

- [<span data-ttu-id="5ca62-116">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ca62-116">ICorPublish Interface</span></span>](icorpublish-interface.md)

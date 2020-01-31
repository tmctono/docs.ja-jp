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
ms.openlocfilehash: 0368349e6c6a566cb569738bf3bda40eb9f5de96
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790731"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="03775-102">ICorPublish::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="03775-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="03775-103">指定した識別子を持つプロセスを表す[ICorPublishProcess](icorpublishprocess-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="03775-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03775-104">構文</span><span class="sxs-lookup"><span data-stu-id="03775-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03775-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03775-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="03775-106">からプロセスの識別子。</span><span class="sxs-lookup"><span data-stu-id="03775-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="03775-107">入出力プロセスを表す `ICorPublishProcess` インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="03775-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03775-108">コメント</span><span class="sxs-lookup"><span data-stu-id="03775-108">Remarks</span></span>  
 <span data-ttu-id="03775-109">プロセスが存在しない場合、または現在のユーザーがデバッグできるマネージプロセスでない場合、`GetProcess` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="03775-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03775-110">要件</span><span class="sxs-lookup"><span data-stu-id="03775-110">Requirements</span></span>  
 <span data-ttu-id="03775-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03775-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03775-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="03775-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="03775-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03775-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03775-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03775-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03775-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="03775-115">See also</span></span>

- [<span data-ttu-id="03775-116">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03775-116">ICorPublish Interface</span></span>](icorpublish-interface.md)

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
ms.openlocfilehash: 2cd2238ac67713564922be440ce64a2ebc4bbf44
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396330"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="a1c67-102">ICorPublish::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="a1c67-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="a1c67-103">指定した識別子を持つプロセスを表す[ICorPublishProcess](icorpublishprocess-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1c67-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c67-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1c67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1c67-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1c67-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="a1c67-106">からプロセスの識別子。</span><span class="sxs-lookup"><span data-stu-id="a1c67-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a1c67-107">入出力プロセスを表すインスタンスのアドレスへのポインター `ICorPublishProcess` 。</span><span class="sxs-lookup"><span data-stu-id="a1c67-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c67-108">解説</span><span class="sxs-lookup"><span data-stu-id="a1c67-108">Remarks</span></span>  
 <span data-ttu-id="a1c67-109">`GetProcess`プロセスが存在しない場合、または現在のユーザーがデバッグできるマネージプロセスでない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a1c67-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c67-110">要件</span><span class="sxs-lookup"><span data-stu-id="a1c67-110">Requirements</span></span>  
 <span data-ttu-id="a1c67-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1c67-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c67-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="a1c67-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a1c67-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1c67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1c67-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1c67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c67-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1c67-115">See also</span></span>

- [<span data-ttu-id="a1c67-116">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1c67-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
